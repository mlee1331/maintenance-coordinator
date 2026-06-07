# Architecture

How this skill is structured, how the pieces connect, and why it's built this way.

## Design Principle

This skill is a bundle of expertise, not a software application. There's no server, no database, no runtime. Just files. An agent harness loads SKILL.md, gains access to the reference files, and uses them to make decisions. The harness handles communication, storage, and integration. The skill handles knowledge.

This is deliberate. Property management companies use dozens of different PM software platforms, agent frameworks, and communication tools. Building an application would lock the skill into one stack. Building a file bundle makes it portable. Any agent that can read markdown can use this skill.

## File Structure

```
maintenance-coordinator/
├── SKILL.md                          # Entry point. The agent's core instructions.
├── references/
│   ├── onboarding/
│   │   └── setup-interview.md        # First-run configuration interview
│   ├── knowledge-base/
│   │   ├── TEMPLATE.md               # Authoring template for new entries
│   │   ├── plumbing/                 # KB-PLUMB-xxx entries
│   │   ├── electrical/               # KB-ELEC-xxx entries
│   │   ├── hvac/                     # KB-HVAC-xxx entries
│   │   ├── appliances/               # KB-APPL-xxx entries
│   │   └── general/                  # KB-GEN-xxx entries
│   ├── decision-logic/
│   │   ├── severity-classification.md
│   │   ├── emergency-classification.md  # Legacy, retained for life-safety details
│   │   ├── tenant-responsibility-matrix.md
│   │   ├── habitability-response-windows.md
│   │   ├── vendor-selection-rules.md
│   │   ├── owner-approval-rules.md
│   │   └── escalation-criteria.md
│   ├── communication/
│   │   ├── tenant-intake-questions.md
│   │   ├── message-templates.md
│   │   ├── tone-and-voice.md
│   │   └── photo-request-guide.md
│   └── schemas/
│       ├── work-order.md
│       ├── property.md
│       ├── tenant.md
│       ├── vendor.md
│       └── owner.md
├── custom/                           # USER CUSTOMIZATIONS (gitignored)
│   ├── knowledge-base/               # Overrides or additions to base KB
│   ├── decision-logic/               # Overrides to base decision logic
│   ├── communication/                # Overrides to base communication files
│   └── rules.md                      # House, emergency & existing-KB-modification rules (agent-writable)
├── assets/
│   ├── config.template.yaml          # Template, copy to config.yaml
│   ├── config.defaults.yaml          # Shipped defaults
│   └── examples/                     # Sample configs (future)
├── evals/
│   ├── README.md
│   ├── life-safety.md
│   ├── habitability.md
│   ├── triage-and-troubleshooting.md
│   ├── vendor-selection.md
│   ├── escalation.md
│   ├── tenant-responsibility.md
│   └── edge-cases.md
├── docs/
│   ├── adoption-guide.md
│   ├── contributing.md
│   └── architecture.md               # This file
└── scripts/                          # Optional utilities (v0.2+)
```

## How the Pieces Connect

### SKILL.md is the Entry Point

SKILL.md is the only file the agent harness needs to load directly. Everything else is referenced from within SKILL.md and loaded on demand. The agent reads SKILL.md, learns its role and decision flow, and then pulls in specific reference files as needed during a work order.

This keeps the agent's initial context small. A 23-entry knowledge base loaded all at once would waste context window. Instead, the agent loads the relevant KB entry only when it's identified the issue category.

### The Decision Flow Drives Everything

SKILL.md defines a 7-stage decision flow:

```
Intake -> Severity Classification -> Tenant Responsibility Check ->
Triage Attempt -> Routing and Vendor Selection -> Dispatch -> Follow-up
```

Each stage references specific files:

| Stage | Primary Reference |
|---|---|
| Intake | `communication/tenant-intake-questions.md` |
| Severity Classification | `decision-logic/severity-classification.md` |
| Responsibility Check | `decision-logic/tenant-responsibility-matrix.md` |
| Triage | `knowledge-base/[category]/[issue].md` |
| Vendor Selection | `decision-logic/vendor-selection-rules.md` |
| Dispatch | `decision-logic/owner-approval-rules.md`, `schemas/work-order.md` |
| Escalation (any stage) | `decision-logic/escalation-criteria.md` |
| All communication | `communication/tone-and-voice.md`, `communication/message-templates.md` |

### Knowledge Base Entries Are Self-Contained

Each KB entry is a complete decision unit. It has everything the agent needs to handle one specific issue type: how to recognize it, how to diagnose it, how to fix it, when to dispatch, who to dispatch, what to tell the tenant, and what to capture in the work order.

KB entries don't reference each other except for related cross-links (e.g., "if you find X during diagnosis, see KB-PLUMB-007 instead"). They reference decision-logic files for jurisdiction lookups and escalation rules.

### Decision Logic Files Are Prescriptive

The files in `decision-logic/` are not guidelines. They're rules. The agent follows them as written. When the severity classification file says "classify as Critical when the tenant reports a gas smell," the agent classifies as Critical. It doesn't weigh options.

This is intentional. Maintenance coordination involves legal obligations (habitability deadlines), safety decisions (gas leaks), and financial boundaries (NTE). These decisions should not be left to LLM judgment. They're codified here so the agent follows them consistently.

### Config Drives Customization

The config file (`assets/config.yaml`) is where company-specific decisions live. NTE thresholds, vendor lists, lockout policies, troubleshooting aggressiveness, communication tone, tenant responsibility assignments. The decision-logic files reference the config when they need company-specific values.

The split is: decision-logic files define the rules. The config provides the parameters. For example, the owner-approval-rules file says "get approval when cost exceeds NTE." The config says what NTE is.

### The Overlay Pattern: `custom/` Over `references/`

Config handles scalar settings (NTE, vendor list, tone). But what about overriding entire reference files, like the severity classification system or a knowledge base entry? That's what the `custom/` directory is for.

The `custom/` directory mirrors the structure of `references/`. When the agent needs a reference file, it checks `custom/` first. If a matching file exists at the same relative path, the agent uses the custom version instead of the base. If no match exists, it falls back to `references/`.

This is the same pattern as Linux's `/etc/default` vs `/etc/conf.d`, or Helm values overrides. The base files ship with the skill and get updated on `git pull`. The custom files are gitignored and belong to the user. No merge conflicts.

The test is **modify vs. create**: are you changing knowledge that already exists, or adding knowledge that doesn't?

1. **`custom/rules.md` = modify existing behavior.** A freeform, plain-English file for every *additive* change: tweaks to an existing knowledge base article or decision ("for toilet clogs, always handyman; not an emergency"), general house rules ("never dispatch on Sundays"), and custom emergency rules ("any water on the floor is an emergency"). Read once at startup, applied on top of everything. Because it is additive, the base files stay current — a rule never freezes a copy. **This is the required path for modifying existing knowledge base content; you do not copy a backend KB entry into `custom/` to edit it.**

2. **New path = add knowledge that doesn't exist.** `custom/knowledge-base/general/pool-maintenance.md` (with a `KB-LOCAL-` id) is a brand-new entry for an issue the backend doesn't cover. The agent finds it alongside the base entries when scanning the knowledge base.

3. **Same path = full replacement (non-KB, rare).** Copying a non-KB reference file (e.g. a decision-logic or communication file) to the same path under `custom/` fully replaces the base. This freezes the file from upstream updates, so it is reserved for genuine wholesale replacement — prefer a rule for anything smaller.

`custom/rules.md` is **agent-writable** (along with `config.yaml`): when a PM states a durable rule in conversation, or answers the onboarding "quirks" question, the agent writes it here. The agent does not create file overrides or new KB entries on its own — those are deliberate edits the PM makes.

Full replacement (not partial merge) is deliberate. Partial merge would require the agent to diff markdown sections and reconcile conflicts. That's fragile and model-dependent. Copying a whole file and editing it is simple, visible, and unambiguous.

The tradeoff: when an upstream update changes a base file the user has overridden, the user needs to manually review and incorporate those changes into their custom version. For v0.1 this is acceptable. A future version could add a script that flags which overridden files have upstream changes.

### Schemas Are Recommendations, Not Requirements

The schema files in `references/schemas/` describe the ideal data model. But the skill is runtime-agnostic. Some harnesses will have full PM software integration with rich data models. Others will be a simple SMS bot with nothing but a conversation history. The schemas describe what fields are useful and which subset is actually required for the agent to function.

### Communication Files Set the Voice

The four files in `references/communication/` define how the agent talks. Tone and voice is the style guide. Intake questions are the triage toolkit. Message templates are reusable patterns. The photo request guide covers when and how to ask for photos.

These are referenced by KB entries (each entry has a "suggested tenant communication" section that follows these guidelines) and by SKILL.md's communication guidelines section.

## What the Skill Does NOT Do

The skill provides expertise. It does not provide infrastructure. Specifically:

- **No server.** The skill is files. The harness runs the agent.
- **No database.** Work order storage is the harness's job. The skill defines what data to capture (schemas), not where to put it.
- **No communication transport.** The skill tells the agent what to say. The harness figures out how to send it (SMS, email, portal, etc.).
- **No PM software integration.** The skill doesn't know AppFolio from Buildium. It defines work order fields and vendor dispatch requirements. The harness maps those to whatever software the company uses.
- **No authentication or multi-tenancy.** One skill instance, one property management company. The config file is that company's configuration.

This is the Agent Skills spec philosophy: skills provide expertise, harnesses provide infrastructure. Mixing them creates lock-in.

## Why Not MCP?

MCP (Model Context Protocol) servers are great for giving agents access to tools and data sources. But this skill isn't a tool or a data source. It's a set of instructions and reference material. Making it an MCP server would mean running a process, managing connections, and tying the skill to a specific protocol. Making it a file bundle means it works everywhere, costs nothing to run, and is easy to inspect, modify, and contribute to.

If a company wants to expose their PM software data to the agent, they should build (or use) an MCP server for that. The skill and the MCP server complement each other. The MCP server provides access to data. The skill provides the knowledge of what to do with it.

## Future (v0.2+)

Planned additions that don't change the core architecture:

- **Python utilities** in `scripts/` for deterministic calculations: NTE checks, habitability deadline computation, vendor ranking algorithms. These are optional helpers, not required to use the skill.
- **More KB entries** covering less common issue types.
- **More jurisdictions** with statute references.
- **Example configs** in `assets/examples/` for common operator profiles (small portfolio, mid-size, luxury).
- **Preventative maintenance** scheduling guidance (expanding beyond reactive work orders).
