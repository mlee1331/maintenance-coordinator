# Owner Approval Rules

When to get owner (or PM) approval before authorizing a repair, and when to proceed without it. The goal is to fix things fast without surprising the owner with unexpected costs.

## The NTE Threshold

Every company sets a not-to-exceed (NTE) threshold during onboarding. This is the maximum dollar amount the coordinator can authorize per work order without getting explicit owner approval. Common ranges are per-work-order, but some companies set per-month or per-property limits.

If no NTE was configured during onboarding, default to a conservative approach: get approval for anything that looks like it could be a significant expense. Flag for PM.

## When Approval Is NOT Needed

Dispatch without owner approval when:

- The issue is classified as Emergency or Critical severity (dispatch immediately, notify PM/owner after)
- The issue is High severity (habitability) with a tight response window and the expected cost is within NTE
- The expected repair cost is clearly within the NTE threshold (routine service calls, standard repairs)
- The company's onboarding config explicitly grants blanket approval for certain categories (some companies pre-approve all plumbing calls under a set amount, for example)

## When Approval IS Needed

Get owner or PM approval before dispatching when:

- The expected cost will exceed the NTE threshold
- The vendor is recommending replacement instead of repair (appliances, water heaters, HVAC systems, windows)
- The repair requires a permit (water heater replacement, electrical panel work, some plumbing)
- The issue is cosmetic and non-urgent (painting, drywall patching, flooring)
- The vendor has found additional issues during a repair and wants to expand scope
- The work involves a capital improvement rather than a repair (new exhaust fan installation, window replacement, insulation upgrade)
- After-hours or emergency rates apply and the total will be significant (flag the premium in the approval request)

## The Approval Workflow

1. **Prepare the request**: summarize the issue, what was tried, the vendor's recommendation, and the expected cost range. Include photos if available.
2. **Send to PM/owner**: use the company's configured communication channel (email, text, app, whatever was set up during onboarding).
3. **Set a deadline**: for habitability issues, note the response window. "Need approval by [time] to meet the [X]-hour habitability window."
4. **If no response within a reasonable time**:
   - For habitability or urgent issues: escalate. Try an alternate contact. If still no response and the habitability clock is running, dispatch and document that approval was attempted.
   - For standard issues: follow up once. If still no response after 24 hours, flag as "pending owner approval" and inform the tenant of the delay.
5. **Document**: note when approval was requested, when it was received, and what was approved. This protects the company if there's a dispute later.

## Replacement vs. Repair Decisions

When a vendor recommends replacement over repair:

- Always flag for owner approval regardless of NTE (replacements are capital expenditures)
- Provide the owner with both options if the vendor offers them (repair cost vs. replacement cost, expected lifespan of repair vs. new unit)
- Note the age of the existing equipment. If it's past its expected lifespan, the vendor's replacement recommendation carries more weight.
- For habitability items (water heater, furnace): if the owner takes too long to decide and the habitability clock is running, escalate. The tenant can't wait for a cost debate.

## Emergency Overrides

In Emergency or Critical severity situations, the coordinator is authorized to:

- Dispatch any available emergency vendor without owner approval
- Authorize reasonable emergency repairs without NTE check
- Authorize emergency board-up, lockout resolution, or temporary measures
- Notify the PM/owner after the fact

This applies to both life-safety (Critical) and active property damage situations (Emergency). See `severity-classification.md` for the full definitions and examples.

The coordinator should still document the cost and notify the owner as soon as possible after the emergency is handled.

## Tenant Communication During Approval Delays

If a repair is delayed pending owner approval:

- Tell the tenant: "The repair needs the property owner's approval before we can move forward. I've sent the request and I'm waiting to hear back. I'll update you as soon as I have an answer."
- Don't blame the owner or make it sound like the owner doesn't care. Keep it neutral and professional.
- Don't share the cost with the tenant (that's between the owner and vendor, not the tenant's concern).
- If the delay extends past the habitability window, tell the tenant: "I'm escalating this because I know you need this resolved. I'm doing everything I can to speed it up."

## Configuration

During onboarding, the agent captures:

- NTE threshold (per work order, per month, per property, or global)
- Pre-approved categories (if any)
- Approval contact (PM, owner, or both)
- Approval channel (email, text, phone, app)
- Escalation contact if primary doesn't respond
