# Escalation Criteria

When the coordinator agent should stop handling an issue independently and escalate to the property manager or a human decision-maker. Escalation is not failure. It's the right call when the issue exceeds the coordinator's scope.

## Always Escalate

These situations require PM involvement regardless of other factors:

### Safety and Legal

- Tenant reports a break-in or attempted break-in (police involvement, insurance claim)
- Tenant reports feeling unsafe due to a maintenance condition
- Tenant threatens legal action or mentions "habitability," "code violation," "health department," or "lawyer"
- Tenant mentions a disability or accommodation need related to the maintenance issue
- Any issue that may involve an insurance claim (flood damage, fire damage, break-in damage)
- Any mold or suspected-mold report. Mold is liability-sensitive, the underlying cause is often something else (a leak, condensation, poor ventilation), and what the tenant reports may not even be mold. A human reviews every mold work order before dispatch — do not auto-dispatch. (Large coverage, over ~10 square feet, is especially urgent: professional remediation and clear liability.)
- Any issue where a tenant reports health symptoms they attribute to a maintenance condition
- ADA/accessibility-related maintenance requests
- A custom rule or override (from `custom/rules.md` or a `custom/` file) would conflict with a backend life-safety instruction — the Critical/Emergency life-safety cases defined in `severity-classification.md` / `emergency-classification.md` (gas, carbon monoxide, fire, electrical hazard, major flooding, evacuate/escalate). Custom normally wins, but never silently for life safety: double-check with the property manager (or human maintenance coordinator) that the downgrade is intended. If they confirm, follow the custom version; if you cannot confirm, follow the backend's life-safety behavior and escalate.

### Financial

- Expected repair cost exceeds the NTE threshold and owner hasn't responded to approval request
- Vendor recommends equipment replacement (water heater, HVAC, appliance) regardless of NTE
- Habitability deadline is approaching and no vendor is available (potential rent abatement or temporary accommodation)
- Tenant disputes responsibility for a chargeable repair

### Operational

- No vendor available within the required response window for a High severity (habitability) issue
- Vendor no-shows or cancels on a Medium or High severity job
- Same issue reported three or more times at the same unit within 90 days (recurring problem, root cause needs investigation)
- Multiple tenants in the same building reporting the same issue simultaneously (building-wide problem)
- Issue requires access to a unit where the tenant is unresponsive and the repair is urgent
- **The coordinator cannot route the work order to a trade AND cannot identify a single clarifying question to the tenant that would unblock it.** The original report is incoherent, internally contradictory, empty of actionable content, or outside the coordinator's competence to route. This is distinct from the askable "Needs More Information" case: if one clear tenant question would resolve the ambiguity (e.g., "is the expansion tank on your water heater or your boiler?"), ask it and stay in the automated loop — do not escalate. Escalate only when you genuinely cannot tell what to ask.

## Escalate with Context

When escalating, provide the PM with:

1. **Summary**: what happened, what was tried, where things stand
2. **Urgency**: is there a habitability clock running? What's the deadline?
3. **Recommendation**: what the coordinator thinks should happen next (dispatch a different vendor, authorize the replacement, contact the tenant directly, etc.)
4. **Documentation**: photos, work order details, communication history with the tenant
5. **Tenant status**: is the tenant waiting? Are they upset? Are they in a safe situation?

Don't just toss the problem over the fence. Give the PM everything they need to make a decision quickly.

## When NOT to Escalate

Don't escalate routine issues that are within the coordinator's scope:

- Standard dispatch within NTE
- Tenant triage that leads to a resolution
- Scheduling and coordination with vendors
- Following up with tenants on completion
- Documenting completed work orders

The coordinator should handle the full lifecycle of routine work orders without PM involvement. Escalation is for exceptions, not for every decision.

## Escalation Channels

Use whatever channel the company configured during onboarding:

- **Urgent escalations**: use the fastest channel (phone, text, or whatever the PM designated for emergencies)
- **Non-urgent escalations**: email or the company's work order system
- **After-hours escalations**: use the after-hours escalation contact from config. If none is configured, use the primary PM contact for anything classified as Medium severity or higher (Critical).

## Escalation Follow-Up

After escalating:

1. Note in the work order that escalation occurred, when, and to whom
2. Continue managing any temporary mitigation (the tenant still needs guidance even while waiting for PM)
3. Follow up with the PM if no response within a reasonable time (1 hour for urgent, 4 hours for standard)
4. Keep the tenant informed: "I've flagged this for the property manager. They'll be in touch shortly." Don't leave the tenant in silence.

## Tenant Communication During Escalation

- Don't use the word "escalation" with the tenant (sounds corporate and alarming)
- Instead: "I'm bringing in the property manager on this one because [reason]."
- If the reason is legal or liability-related, don't explain why. Just say: "This one needs the property manager's direct involvement. They'll reach out to you."
- Never promise the tenant a specific outcome from the PM ("they'll definitely approve the replacement"). Promise action, not results.
