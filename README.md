# Maintenance Coordinator Skill

An open source [Agent Skill](https://agentskills.io) that turns any LLM-based agent into a residential property management maintenance coordinator. Bring your own agent harness. Point it at this skill. Done.

## What This Is

A portable bundle of expertise: SKILL.md plus a knowledge base, decision logic, communication patterns, schemas, and example configs. When an agent loads this skill, it gains the procedural knowledge to handle the full maintenance coordination workflow:

- Tenant work order intake
- Work order categorization (which trade the issue belongs to)
- Severity triage (5 levels) with US habitability response windows
- Tenant vs. owner responsibility classification
- Tenant-side troubleshooting before dispatch (configurable aggressiveness 0-5)
- Vendor routing and selection
- Owner approval (NTE) checks
- Dispatch and scheduling coordination
- Follow-up and loop closure

## Who This Is For

Property management companies that want to automate maintenance coordination using their own AI agent stack and don't want to be locked into a vendor platform.

Works with any agent harness: Claude Desktop, Claude Code, Codex CLI, OpenClaw, custom Python agents, n8n flows, LangGraph, CrewAI, AutoGen, or anything else that can read a SKILL.md and reference its bundled files.

## Scope

- US-only in v0.1. Habitability rules and response windows reference US state and local law.
- Residential property management (single-family, small multifamily). Not commercial, not HOA, not short-term rentals.
- Reactive work orders. Preventative maintenance, make-readies, capital improvements, and insurance claims are out of scope for v0.1.

## Quick Start

1. Clone this repo or download as a folder.
2. Install the skill in your agent harness:
   - **Claude Code**: place the folder at `~/.claude/skills/maintenance-coordinator/`
   - **Codex CLI**: place the folder at `~/.codex/skills/maintenance-coordinator/`
   - **Other harnesses**: point your agent at `SKILL.md` as part of its system context, give it read access to the folder
3. Start using it. The agent works immediately with sensible defaults (NTE $500, troubleshooting level 3, warm tone, industry-standard tenant responsibility). No onboarding required. The agent should follow the **"How to Use This Skill"** contract at the top of `SKILL.md` — above all, loading the matching `references/knowledge-base/` entry for tenant-side troubleshooting before recommending any dispatch.
4. Customize when you're ready. Tell the agent to run setup, edit `assets/config.yaml` directly, or just change settings mid-conversation ("add Mike's Plumbing as a vendor", "set my NTE to 750"). The agent adapts on the fly.
5. Wire your agent to your PM software, SMS provider, and vendor dispatch system using their tooling. The skill defines what data the agent works with in `references/schemas/`.
6. Run the eval cases in `evals/` to verify behavior before going live.

## Customization: Config + Overlay

Two ways to make the skill yours, both safe across updates.

**Config (`assets/config.yaml`)** handles structured settings only: NTE thresholds, vendor list, lockout policy, troubleshooting aggressiveness, tone. Copy `config.template.yaml` to `config.yaml` and edit, or just tell the agent ("set my NTE to 750", "add Mike's Plumbing as a vendor").

**The `custom/` overlay** handles everything else. The test is *modify vs. create*:

- **Modify existing behavior → a rule in `custom/rules.md`.** A plain-English file for tweaks to an existing knowledge base article or decision ("for toilet clogs, always handyman; not an emergency"), general house rules ("never dispatch on Sundays"), and custom emergency rules ("any water on the floor is an emergency"). It's additive — layered on the always-current base files — and **agent-writable**, so you can just say "remember: never dispatch on Sundays" and it sticks. Modifications to existing KB content must be rules here, not file copies.
- **Add knowledge that doesn't exist → a new file.** For an issue the backend doesn't cover, add `custom/knowledge-base/general/pool-maintenance.md` (with a `KB-LOCAL-` id); it shows up alongside the base entries.

Both `config.yaml` and `custom/` are gitignored, so `git pull` updates the shared backend (knowledge base, decision logic, evals) without touching your customizations. No merge conflicts. The base is the common, community-maintained layer. Your overrides stay yours.

See `docs/architecture.md` for the full overlay design.

## Project Structure

```
maintenance-coordinator-skill/
├── SKILL.md                    # Required entry point (Agent Skills spec)
├── README.md                   # This file
├── AGENTS.md                   # Guidance for coding agents working in this repo
├── LICENSE                     # AGPL-3.0
├── references/                 # Loaded on demand by the agent
│   ├── knowledge-base/         # Categorized troubleshooting entries
│   ├── decision-logic/         # Categorization, severity, responsibility, vendor, escalation rules
│   ├── communication/          # Intake questions, templates, tone, photo guides
│   └── schemas/                # Data structure definitions
├── custom/                     # Your overrides (gitignored, mirrors references/)
├── assets/                     # User-customizable templates
│   ├── config.defaults.yaml    # Shipped defaults (do not edit; copy to config.yaml)
│   └── config.template.yaml    # Annotated starting point for your config.yaml
├── evals/                      # Test cases for validation
└── docs/                       # Adoption, contributing, architecture
```

## Configurable Troubleshooting Aggressiveness (0-5)

How hard the agent tries to resolve issues with the tenant before dispatching a vendor:

- **Level 0**: Never troubleshoot. Dispatch immediately.
- **Level 1**: One or two yes/no questions, then dispatch.
- **Level 2**: Light troubleshooting (resets, simple checks).
- **Level 3**: Balanced (default). Full standard decision tree.
- **Level 4**: Thorough. Extended diagnostics, video, multi-condition tests.
- **Level 5**: Maximum. Guided repairs with shipped parts where appropriate.

Full definitions, expected dispatch rates, and tradeoffs are in `SKILL.md`. Dynamic override rules apply at every level (tenant frustration, repeat issues, accessibility needs, time budget exceeded).

## License

AGPL-3.0. If you modify this skill and offer it as a hosted service, your modifications must be open sourced under the same license. See `LICENSE`.

## Roadmap

### v0.1 (current)

Core skill bundle: knowledge base, decision logic, communication patterns, schemas, evals. Works with any agent harness. You wire the integrations yourself.

### v0.2

- Python utilities for deterministic logic (NTE checks, habitability deadline math, vendor ranking)
- More KB entries for less common issue types
- More jurisdiction coverage with statute references
- Sample configs for common operator profiles

### Future: PM Software Plugins

Right now, the skill tells the agent what to do but doesn't know how to talk to any specific PM platform. The harness owner wires that up. Long-term, we want companion plugins for the major PM systems so the skill can create work orders, dispatch vendors, and pull property/tenant data natively. On the list:

- AppFolio
- Buildium
- DoorLoop
- Propertyware
- RentVine

Each plugin would handle authentication, API mapping, and data translation for that platform. The skill stays platform-agnostic. The plugins bridge the gap. If you use one of these systems and want to help build the plugin, open an issue.

## Status

v0.1 (early). Active development. Not yet production-tested at scale. Use the eval cases to validate before deploying. File issues for missing knowledge base entries, jurisdiction gaps, or unclear instructions.

## Contributing

Knowledge base entries, jurisdiction rules, and decision logic improvements are welcome. See `docs/contributing.md` for the authoring template and PR process. The bar: real operator experience, cited sources for legal claims, plain English, no fluff.

## Why Open Source

Maintenance coordination is a problem every PM company solves badly and independently. Sharing the playbook makes the whole industry better. This skill is the playbook.
