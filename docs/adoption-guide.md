# Adoption Guide

How to take this skill and put it to work in your property management operation. This guide assumes you already have an agent harness (Claude Code, Codex CLI, OpenClaw, a custom Python agent, whatever). If you don't have one yet, pick one. This skill works with any of them.

## What You Need Before Starting

1. **An agent harness** that can read markdown files and use them as instructions. Most LLM agent frameworks can do this. The harness loads SKILL.md as system context and gives the agent read access to the rest of the folder.

2. **A way for tenants to reach the agent.** SMS, email, a tenant portal, a phone line with speech-to-text. The skill doesn't prescribe a channel. It just needs tenant messages to come in and agent messages to go out.

3. **A way for the agent to dispatch vendors.** At minimum, the agent needs to be able to send a message to a vendor (text, email, whatever the vendor uses). More sophisticated setups integrate with PM software to create work orders, schedule appointments, and track status.

4. **Your company's configuration.** NTE thresholds, vendor list, jurisdiction(s), lockout policy, troubleshooting aggressiveness, communication preferences. This all goes in `assets/config.yaml`.

## Step-by-Step Setup

### 1. Get the Skill Files

Clone the repo or download the folder. The whole thing is self-contained. No external dependencies, no API keys, no hosted services.

### 2. Configure

Copy `assets/config.template.yaml` to `assets/config.yaml`. You have two options for filling it out:

**Option A: Manual.** Open the template, read the comments, fill in your values. The template explains every field.

**Option B: Run the onboarding interview.** Point your agent at the skill and start a conversation. If `config.yaml` is missing or incomplete, the agent will walk you through the setup interview from `references/onboarding/setup-interview.md`. It asks the questions conversationally and writes the answers to `config.yaml` at the end.

Either way, you need at minimum:
- Default jurisdiction (state)
- Emergency contact (who the agent escalates to)
- At least one plumber, one electrician, one HVAC tech, and one locksmith
- NTE default threshold
- Lockout policy

The agent works without any of these (it uses defaults from `config.defaults.yaml` and asks on the fly for anything missing), but configuring them upfront reduces friction on every work order.

### 3. Install in Your Harness

How you install depends on your harness:

**Claude Code**: Place the folder at `~/.claude/skills/maintenance-coordinator/`. Claude Code will detect the SKILL.md and load it.

**Codex CLI**: Place the folder at `~/.codex/skills/maintenance-coordinator/`.

**OpenClaw**: Add the folder path to your agent's skill configuration.

**Custom agent (Python, Node, etc.)**: Load SKILL.md into your agent's system prompt or instruction context. Give the agent file-read access to the entire `maintenance-coordinator/` folder so it can load knowledge base entries, decision logic, and other references on demand.

**Workflow tools (n8n, LangGraph, etc.)**: Load SKILL.md as the system message in your LLM node. Attach the references as retrievable context or give the agent a file-read tool pointed at the folder.

The key principle: the agent needs SKILL.md in its instruction context and read access to the rest of the folder. How you achieve that depends on your stack.

### 4. Wire Up Communication

The skill defines what the agent should say but not how it sends messages. You need to connect:

**Inbound** (tenant to agent):
- SMS gateway (Twilio, Vonage, etc.)
- Email inbox monitor
- Tenant portal webhook
- Phone line with transcription

**Outbound** (agent to tenant, agent to vendor, agent to PM):
- Same channels, reverse direction
- The agent needs a way to send a text, email, or message through whatever system you use

**PM software integration** (optional but recommended):
- Work order creation and updates
- Vendor dispatch through the software's API
- Tenant and property data lookup

The skill doesn't prescribe any of these integrations. It tells the agent what to do. Your harness and tools handle how.

### 5. Run the Evals

Before going live, run the scenarios in `evals/`. Feed the tenant messages to your agent and compare its behavior against the expected behavior in each scenario. Pay special attention to:

- **Life-safety scenarios**: Does the agent dispatch immediately? Does it give correct safety advice? Does it avoid troubleshooting?
- **Habitability scenarios**: Does the agent look up the correct response window? Does it dispatch within that window?
- **Vendor selection**: Does the agent prefer handyman for routine work? Does it respect owner vendor preferences?
- **Escalation**: Does the agent escalate when it should? Does it provide the PM with enough context?
- **Edge cases**: Does the agent handle compound issues, after-hours timing, vulnerable tenants, and jurisdiction differences correctly?

If something fails, check whether it's a config issue (wrong jurisdiction, missing vendor) or a behavior issue (the agent isn't following the decision logic correctly). Config issues are easy to fix. Behavior issues might mean the agent isn't loading the right reference files at the right time.

### 6. Go Live (Gradually)

Don't flip the switch on your entire portfolio at once. Start with a few properties or a subset of issue types. Monitor the agent's behavior. Review its work orders. Check its escalation decisions. Once you're confident, expand.

The config has a `go_live_immediately` flag (default: false). Set it to true when you're ready.

## Common Integration Patterns

### Pattern 1: SMS-Only, No PM Software

Simplest setup. Tenant texts in, agent responds via SMS, agent texts the vendor to dispatch, agent texts the PM to escalate. Work order tracking is in the conversation history. Works for small operators with a handful of properties.

### Pattern 2: SMS + PM Software

Tenant texts in. Agent creates a work order in the PM software (AppFolio, Buildium, RentManager, etc.) via API. Agent dispatches through the software. Work order status is tracked in the software. Agent still communicates with the tenant via SMS. This is the most common pattern for mid-size operators.

### Pattern 3: Tenant Portal Integration

Tenant submits a request through a web portal. The portal triggers the agent via webhook. Agent handles triage and dispatch through the PM software's API. All communication goes through the portal. The agent just reads and writes messages in the portal thread.

### Pattern 4: Full Automation

Agent handles the entire workflow end-to-end: intake, triage, vendor selection, dispatch, scheduling, follow-up, work order closure. PM only gets involved when the agent escalates. This requires solid PM software integration and a well-tested configuration. Don't start here. Get comfortable with patterns 1-3 first.

## Customizing the Skill

The skill ships with sensible defaults, but every operation is different. There are two layers of customization:

**Settings** go in `assets/config.yaml`. NTE thresholds, vendor list, troubleshooting aggressiveness, tone, jurisdiction, lockout policy, tenant responsibility assignments. These are key-value settings that override the defaults in `config.defaults.yaml`.

**Reference overrides** go in the `custom/` directory. If you need to change a knowledge base entry, swap out the severity classification system, add jurisdiction-specific decision logic, or tweak communication templates, copy the file from `references/` to the same path under `custom/` and edit the copy. The agent checks `custom/` first and falls back to `references/`. You can also add entirely new files (like custom KB entries for issues specific to your portfolio) using the `KB-LOCAL-` ID prefix.

For any plain-English change to existing behavior, add a rule to `custom/rules.md`: tweaks to an existing knowledge base article ("for toilet clogs, always handyman; not an emergency"), general house rules ("never dispatch on Sundays"), and custom emergency rules ("any water on the floor is an emergency"). The agent reads this file at startup and applies it on top of everything, and it's agent-writable, so you can just tell the agent a rule and it saves it there. Rules are additive — they layer on the always-current base files, so you keep getting upstream updates. Modifying existing KB content must be a rule here, not a file copy. Only create a new file under `custom/` when you're adding knowledge the backend doesn't have at all.

The `custom/` directory is gitignored, so pulling upstream updates never touches your customizations.

## Updating the Skill

Pull the latest version from GitHub. Your `config.yaml` and everything in `custom/` are gitignored, so updates won't overwrite your settings or customizations.

If a new version changes a base file you've overridden in `custom/`, review the upstream changes and decide whether to incorporate them into your custom version. Run the evals again to verify nothing breaks with your configuration.

## Getting Help

File an issue on the repo if you hit something the docs don't cover. Include your harness type, what you expected, and what happened. If it's a jurisdiction question (your state's habitability law isn't represented correctly), include the statute reference and we'll fix it.
