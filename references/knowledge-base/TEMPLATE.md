---
id: KB-<CATEGORY>-<NUMBER>  # For custom entries in custom/, use KB-LOCAL-<CATEGORY>-<NUMBER>
category: <category>
subcategory: <subcategory>
title: <Title>
severity: low | medium | high
tenant_fixable: true | false
tenant_responsible: never | sometimes | often
required_photos: true | false
required_videos: true | false
typical_resolution_minutes: <number for tenant self-fix path>
response_target_hours: <number based on severity: high=4-24, medium=48, low=72-168>
jurisdictions: all | <list>
last_reviewed: YYYY-MM-DD
---

# Title

## Symptoms covered

What this entry covers. Be specific. List the variants. Then state what this entry does NOT cover and cross-reference the correct entry.

## Intake questions for tenant

Numbered list of questions to ask. Include a classification check note if certain answers change the severity level (e.g., "if there is standing water near electricity, reclassify as Critical").

## Diagnostic decision tree

ASCII flowchart the agent follows step by step. Mark decision points clearly. End every branch with either RESOLVED or DISPATCH. Note which steps apply at which aggressiveness levels (e.g., "at Level 4+: ..."). Include photo/video request triggers at specific points where visual confirmation would help (mark with [PHOTO] or [VIDEO]).

## Tenant-fixable resolution steps

Numbered plain-English steps. Write for a non-technical person. No jargon without explanation. Note any safety boundaries (what NOT to do).

## When to dispatch

Bullet list of conditions that end triage and trigger vendor dispatch.

## Vendor category to dispatch

Which trade/vendor type. Note any secondary dispatch scenarios. General principle: prefer a handyman for straightforward work (they're cheaper). Reserve licensed specialists (plumber, electrician, HVAC tech) for work that requires specialized tools, licensure, or deep expertise. Many routine plumbing tasks (faucet repair, toilet internals, drain snaking, wax ring replacement, disposal swap), electrical tasks (GFCI replacement, outlet swap, breaker diagnosis), and appliance tasks are well within a capable handyman's scope. The vendor-selection-rules decision-logic file governs this in detail.

## Temporary mitigation while awaiting dispatch

What should the tenant do in the meantime to prevent damage, stay safe, or reduce inconvenience? Examples: put towels down, use a different bathroom, put food in a cooler, use a space heater (with fire safety notes), turn off the water supply valve.

## Tenant responsibility notes

Is this ever tenant-responsible? Under what conditions? What lease clause typically governs? If tenant-responsible, does the agent still offer troubleshooting guidance (yes, always), and should it note that dispatch may result in a chargeback?

## Work order fields to capture at dispatch

Checklist of information that must be in the work order when dispatching:

- Symptom description (in tenant's words)
- What was tried during triage and outcome of each step
- Make/model/age of equipment if captured
- Error codes if applicable
- Photos/videos collected
- Access instructions for the unit
- Tenant availability windows
- Pet in unit (yes/no, type)
- Urgency level and any SLA clock running

## Suggested tenant communication

Short example messages for tricky moments in this issue type. What to say when:

- Informing the tenant this might be their responsibility
- Asking them to try a step they might resist
- Telling them a vendor is on the way
- Following up after resolution

Keep these warm, direct, and plain-spoken per the communication guidelines.

## Notes for coordinator agent

Anything else the agent should know: common misdiagnoses, cost ranges for the vendor visit, NTE flags, related issues to check for, after-hours considerations, recurring-issue handling, accessibility considerations for elderly or disabled tenants.
