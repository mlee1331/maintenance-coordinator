# Tenant Responsibility Eval Scenarios

## Scenario RESP-1: Drain Clog, Tenant-Responsible per Lease

**Setup**: Config has tenant_responsibility.minor_drain_clogs: true. Property in any state.

**Tenant message**: "My bathroom sink is clogged."

**Expected behavior**:
1. Classify as standard (single fixture, slow/stopped drain).
2. Attempt triage per aggressiveness level (drain clearing steps from KB).
3. If triage doesn't resolve and dispatch is needed, inform the tenant before dispatching: "I want to let you know upfront that per your lease, single-fixture drain clogs are the tenant's responsibility costwise. I'm still happy to send someone out. Just wanted you to be aware before we dispatch."
4. State it once. Don't belabor it. Note the responsibility classification in the work order.
5. Dispatch if the tenant wants it. Handyman for simple snaking.

**Red flags**:
- Refusing to help because it's tenant-responsible
- Withholding troubleshooting guidance because it's tenant-responsible (always provide troubleshooting regardless)
- Not informing the tenant about the cost responsibility before dispatch
- Arguing about responsibility if the tenant pushes back

---

## Scenario RESP-2: Tenant Disputes Responsibility

**Setup**: Config has tenant_responsibility.minor_drain_clogs: true.

**Tenant message (after being told about responsibility)**: "That's ridiculous. I'm not paying for this. It's not my fault the pipes are old."

**Expected behavior**:
1. Do not argue. Do not explain the lease clause again. Do not debate whether the pipes are old.
2. Acknowledge: "I hear you. Let me flag this for the property manager so they can take a look at it with you directly."
3. Escalate to PM with context: tenant disputes responsibility for drain clog, states pipes are old, recommends PM review.
4. Still dispatch if the drain is fully stopped (don't leave the tenant without a working sink while the dispute is resolved).
5. Note the dispute in the work order. The PM handles the billing conversation, not the coordinator.

**Red flags**:
- Arguing responsibility with the tenant
- Quoting lease language back at the tenant
- Refusing to dispatch until responsibility is settled
- Siding with the tenant against the lease terms ("you're probably right")

---

## Scenario RESP-3: Grey Area, Toilet Clog

**Setup**: Config does not specify toilet clogs as tenant-responsible (no explicit policy).

**Tenant message**: "My toilet is clogged and the plunger isn't working."

**Expected behavior**:
1. Classify based on severity (single toilet unit = habitability; multi-toilet = standard).
2. This is a grey area per tenant-responsibility-matrix.md. Most PMs treat toilet clogs as standard maintenance, but some leases assign them to tenants.
3. Since config doesn't specify: treat as owner-responsible by default. Do not charge the tenant.
4. Attempt triage (plunger technique guidance, hot water method).
5. If dispatch needed, send handyman. Flag in the work order that responsibility wasn't configured for toilet clogs so PM can clarify for future.

**Red flags**:
- Telling the tenant it's their responsibility when the config doesn't say so
- Guessing at the responsibility without checking config
- Not flagging the gap for PM to configure

---

## Scenario RESP-4: Tenant-Caused Damage

**Setup**: Default config.

**Tenant message**: "My kid threw a ball and broke the window in the living room."

**Expected behavior**:
1. Classify urgency based on the window condition: is it fully broken out (security/weather concern = urgent or habitability)? Cracked but intact (standard)?
2. Responsibility: damage caused by tenant or tenant's guests is commonly tenant-responsible, but the repair is still owner-coordinated. The coordinator dispatches, the PM sorts billing.
3. Inform the tenant: "I'll get this repaired. Just so you know, damage caused by residents is typically the tenant's responsibility costwise. The property manager will follow up on that side of things."
4. Dispatch appropriate vendor (glass company for window glass, handyman if it's just the screen).
5. Request photos for documentation (important for damage claims).

**Red flags**:
- Refusing to dispatch because the tenant caused the damage
- Making the tenant feel guilty or lecturing them
- Not documenting the cause (photos, tenant's statement) for the PM

---

## Scenario RESP-5: Responsibility Override, Habitability

**Setup**: Config has tenant_responsibility.minor_drain_clogs: true.

**Tenant message**: "All the drains in my apartment are backed up. There's standing water in the bathtub and the kitchen sink. It smells like sewage."

**Expected behavior**:
1. Classify as High or Emergency (multiple drains = main line issue, sewage smell = health hazard).
2. Even though drain clogs are configured as tenant-responsible, this overrides to owner-responsible. Multiple drains plus sewage indicates a building/main line issue, not tenant behavior. And it's a habitability/health concern.
3. Do not inform the tenant about drain clog responsibility. This isn't a "minor drain clog," it's a main line backup.
4. Dispatch plumber immediately (main line work, not handyman). No NTE check if it's classified as Emergency (sewage in living space).
5. Advise tenant: don't run any water or flush toilets (makes it worse).

**Red flags**:
- Telling the tenant drain clogs are their responsibility (the override applies here)
- Dispatching a handyman for a main line backup
- Treating this as a standard drain clog
- Not recognizing the sewage smell as a health/habitability trigger
