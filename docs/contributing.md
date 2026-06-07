# Contributing

How to contribute knowledge base entries, decision logic, jurisdiction rules, eval scenarios, and other improvements to this skill.

## What We're Looking For

The most valuable contributions come from people who actually coordinate maintenance. If you've dispatched a vendor, triaged a tenant call, or dealt with a habitability deadline, you know things that aren't in any textbook. That's what we want.

Specific areas where contributions make a big impact:

- **Knowledge base entries** for issue types not yet covered (see the list of what exists in `references/knowledge-base/`)
- **Jurisdiction-specific habitability rules** with statute references (the current coverage is incomplete)
- **Eval scenarios** for edge cases you've encountered in real operations
- **Decision logic refinements** based on operational experience
- **Corrections** to anything that's wrong (wrong vendor routing, bad triage guidance, incorrect legal references)

## Principles

This skill follows the [Agent Skills spec](https://agentskills.io/specification). When making changes:

- Frontmatter on `SKILL.md` contains only `name` and `description`. The description is phrased imperatively.
- Bundled resources live in `references/`, `assets/`, and `scripts/`. No server, no MCP, no hosted services. The skill is files.

**Safety first.** This skill affects real tenants in real homes. When in doubt about content, err toward safety. Don't recommend a shortcut a vendor would call dangerous, and don't ask tenants to do something risky to save a dispatch fee.

## Knowledge Base Entries

### Template

Every KB entry follows the template in `references/knowledge-base/TEMPLATE.md`. Read it before writing a new entry. The key sections are:

- Frontmatter (ID, category, severity, metadata)
- Symptoms covered
- Intake questions for tenant
- Diagnostic decision tree
- Tenant-fixable resolution steps
- When to dispatch
- Vendor category to dispatch
- Temporary mitigation while awaiting dispatch
- Tenant responsibility notes
- Work order fields to capture at dispatch
- Suggested tenant communication
- Notes for coordinator agent

### ID Scheme

IDs follow the pattern `KB-CATEGORY-NUMBER`:
- `KB-PLUMB-001` through `KB-PLUMB-xxx` for plumbing
- `KB-ELEC-001` through `KB-ELEC-xxx` for electrical
- `KB-HVAC-001` through `KB-HVAC-xxx` for HVAC
- `KB-APPL-001` through `KB-APPL-xxx` for appliances
- `KB-GEN-001` through `KB-GEN-xxx` for general/structural/pest/other

IDs are stable. Never renumber existing entries. When adding a new entry, use the next available number in that category. Check what exists first.

### Writing Style

Casual, warm, direct. No corporate-speak. No fluff. Write how you'd explain it to a competent new coordinator on their first day.

No em dashes. Use commas, periods, parentheses, or rewrite the sentence.

Short sentences and short paragraphs. Bullets only when they genuinely help. Prefer prose.

No specific dollar amounts. Costs vary drastically by region and change over time. Use relative terms ("cheap part", "significant expense", "typically within NTE for most companies").

### Vendor Dispatch Guidance

Prefer handyman for straightforward work. Reserve licensed specialists (plumber, electrician, HVAC tech) for work that requires specialized tools, licensure, or deep expertise. See `references/decision-logic/vendor-selection-rules.md` for the full hierarchy. Every KB entry's vendor dispatch section should reflect this principle.

### What Makes a Good Entry

- Covers a specific, identifiable issue (not "plumbing problems" but "toilet running continuously")
- Diagnostic tree is step-by-step and testable (not "check if it's broken" but "press the reset button on the bottom of the unit, it's a small red button")
- Tenant-fixable steps are realistic (don't ask tenants to use tools they probably don't have)
- Dispatch criteria are clear (when to stop trying and send a vendor)
- Communication examples sound like a real person, not a template

### What to Avoid

- Don't recommend chemical drain cleaners (liability, pipe damage, hazardous for vendors)
- Don't ask tenants to work with gas lines, main electrical panels, or anything on the roof
- Don't include mock data or filler text. If you don't know something, say so and flag it for research.
- Don't copy content from proprietary maintenance manuals or competitor products

## Decision Logic

Decision logic files live in `references/decision-logic/`. They're declarative and prescriptive. The agent follows them, it doesn't interpret them.

If you're updating a decision logic file:

- Be specific. "Escalate when appropriate" is useless. "Escalate when the same issue is reported three or more times at the same unit within 90 days" is useful.
- Cite state law when referencing habitability requirements. Include the statute number.
- Note when something is company-configurable vs. legally required. The agent needs to know the difference.
- Test your changes against the eval scenarios to make sure they don't break expected behavior.

## Jurisdiction Rules

Habitability response windows are in `references/decision-logic/habitability-response-windows.md`. If your state or city isn't covered, or if the existing entry is wrong:

- Include the statute reference (e.g., "Cal. Civ. Code 1941.1")
- Note the specific response timeframe from the statute
- Note any local overrides (city ordinances that are stricter than state law)
- If the statute says "reasonable time" without specifying hours, note that and include what "reasonable" typically means in practice

## Eval Scenarios

Eval scenarios live in `evals/`. Each scenario has setup, tenant message, expected behavior, and red flags. See the existing files for the format.

Good eval contributions:

- Edge cases you've actually encountered (not hypotheticals)
- Scenarios that test jurisdiction-specific behavior
- Scenarios that expose ambiguity in the decision logic (where the agent might reasonably go two different ways)
- Scenarios that test the interaction between multiple decision rules (responsibility + escalation + vendor selection)

## Pull Request Process

1. Fork the repo.
2. Make your changes on a branch.
3. Run the relevant eval scenarios against your changes. Note the results.
4. Submit a PR with a clear description of what you changed and why.
5. If you're adding a jurisdiction rule, include the statute reference in the PR description.
6. If you're adding a KB entry, include what real-world issue prompted it.

## Quality Bar

The bar for contributions: real operator experience, cited sources for legal claims, plain English, no fluff. If you wouldn't trust the guidance to handle a real tenant call, don't submit it.
