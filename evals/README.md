# Evals

Test scenarios for the maintenance coordinator skill. Each file contains a set of scenarios that test a specific aspect of the decision flow. Run these before going live to verify the agent handles common and edge cases correctly.

## How to Use

Each scenario has:

- **Setup**: any config assumptions (jurisdiction, NTE, vendor list, etc.)
- **Tenant message**: what the tenant says
- **Expected behavior**: what the coordinator should do, step by step
- **Red flags**: things the coordinator should definitely NOT do

Feed the tenant message to the agent and compare its behavior against the expected behavior. If it does something listed under red flags, that's a failure.

These are not automated tests. They're conversation scenarios you walk through manually with the agent. Think of them as a checklist for acceptance testing.

## Files

- `life-safety.md` — Critical severity (life-safety) (gas, fire, flooding, CO)
- `habitability.md` — habitability emergencies (no heat, no hot water, no toilet, security)
- `triage-and-troubleshooting.md` — tenant troubleshooting at various aggressiveness levels
- `vendor-selection.md` — handyman vs. specialist routing, owner preferences, NTE
- `escalation.md` — when to escalate to PM, how to communicate it
- `tenant-responsibility.md` — responsibility classification, disputes, grey areas
- `edge-cases.md` — compound issues, repeat calls, after-hours, vulnerable tenants, jurisdiction quirks
