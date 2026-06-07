---
id: KB-PLUMB-005
category: plumbing
subcategory: leaks
title: Water Leak from Ceiling or Upstairs Unit
severity: high
tenant_fixable: false
tenant_responsible: never
required_photos: true
required_videos: false
typical_resolution_minutes: 5
response_target_hours: 4
jurisdictions: all
last_reviewed: 2026-05-05
---

# Water Leak from Ceiling or Upstairs Unit

## Symptoms covered

- Water dripping or flowing from ceiling
- Water stain growing on ceiling (active or recent)
- Bulging or bubbling paint on ceiling from water behind it
- Water coming through a light fixture (dangerous)
- Water running down a wall from above

Does NOT cover: condensation on ceiling (humidity issue, not a leak), old water stain that is dry and not growing (cosmetic, Cosmetic severity), roof leak during rain (see KB-GEN-002 when created).

## Intake questions for tenant

1. Where exactly is the water coming from? (Which room, where on the ceiling?)
2. How much water? A slow drip, a steady drip, or actively flowing/streaming?
3. Is it near a light fixture, outlet, or smoke detector? [PHOTO]
4. Is the ceiling bulging or bubbling?
5. Do you have an upstairs neighbor? If so, can you hear water running up there?
6. Did this start suddenly or have you noticed a growing stain?

**Classification check**: If water is coming through or near a light fixture or electrical outlet, classify as Critical (water + electricity). Tell the tenant to turn off that circuit at the breaker and do not use the fixture. Dispatch immediately.

If water is actively flowing (not just dripping), classify as urgent minimum. Risk of significant property damage escalates fast.

## Diagnostic decision tree

```
START
│
├─ Is water coming through or near a LIGHT FIXTURE or OUTLET?
│   └─ Yes → CRITICAL. Tell tenant to turn off that circuit at the
│       breaker. Do NOT use the fixture. DISPATCH immediately.
│
├─ Is the ceiling BULGING or BUBBLING?
│   └─ Yes → water is pooling above the drywall. Risk of ceiling collapse.
│       [PHOTO] Tell tenant to stay clear of the area. Place towels/bucket.
│       DISPATCH immediately.
│       (Note: some coordinators recommend poking a small hole to relieve
│       pressure. Do NOT advise this -- tenant could damage wiring or
│       release a large volume of water. Leave it for the vendor.)
│
├─ Is there an UPSTAIRS UNIT?
│   ├─ Attempt to contact the upstairs tenant (if you have access to
│   │   tenant contact info in the system).
│   │   └─ Ask upstairs tenant: is anything running? Toilet overflowing?
│   │       Tub left on? Washing machine running?
│   │       └─ If identifiable source above → ask upstairs tenant to
│   │           stop the water (turn off fixture, mop up).
│   │       └─ If upstairs tenant is not home → DISPATCH immediately.
│   │           May need access to upstairs unit to find/stop the source.
│   └─ If no upstairs unit → possible pipe leak in ceiling/wall cavity.
│       DISPATCH.
│
├─ Can the tenant identify the general SOURCE?
│   ├─ Directly below a bathroom above → likely toilet, tub, or supply line
│   ├─ Below a kitchen above → likely sink, dishwasher, or supply line
│   ├─ Below a laundry area → likely washing machine supply or drain
│   ├─ No clear room above / middle of ceiling → likely pipe in cavity
│   └─ All of these → DISPATCH. Source info helps the vendor prep.
│
├─ Can the tenant turn off water to reduce damage?
│   ├─ If leak is clearly from a specific fixture above that the tenant
│   │   has access to → shut off supply valve at that fixture.
│   ├─ If the source is unknown or in a wall → do NOT ask tenant to
│   │   shut off the main. Just place towels/buckets and dispatch.
│   │   (Exception: if water is actively flooding, then guide tenant to
│   │   the main shutoff if they know where it is.)
│
└─ DISPATCH in all cases. This is never tenant-fixable for the
    reporting tenant. The fix is above their ceiling.
```

## Tenant-fixable resolution steps

This issue is not tenant-fixable. The reporting tenant cannot access the source (it's above their ceiling). Tenant actions are limited to damage mitigation:

1. Place buckets or towels under the drip to protect flooring.
2. Move furniture and belongings away from the affected area.
3. If water is near electronics or electrical outlets, unplug devices and stay clear.
4. Do NOT poke holes in the ceiling.

## When to dispatch

Always. This is never a triage-and-resolve situation. Dispatch immediately for active leaks, within 4 hours for slow drips with growing stains.

## Vendor category to dispatch

Plumber. If the ceiling is damaged (bulging, collapsed, stained), a secondary dispatch for drywall/paint repair will follow after the leak is fixed. Do not dispatch drywall repair until the plumber confirms the source is fixed and dry.

## Temporary mitigation while awaiting dispatch

- Buckets and towels under the drip point
- Move furniture, electronics, and personal items away from the area
- If near electrical fixtures, turn off that circuit at the breaker
- If upstairs unit is the source and upstairs tenant is cooperative, have them stop using the fixture causing it
- If water volume is high and main shutoff is known, the tenant can shut off the main (but only in active flooding situations)

## Tenant responsibility notes

Never tenant-responsible for the reporting tenant (the one with water coming through their ceiling). If the upstairs tenant caused it (overflowed tub, left water running), the upstairs tenant may be responsible for damages, but that's a property manager decision, not something the coordinator agent determines. Flag for PM review.

## Work order fields to capture at dispatch

- Location of leak (which room, where on ceiling)
- Volume/rate (drip vs. flow)
- Proximity to electrical fixtures
- Whether upstairs tenant was contacted and what was found
- Photos of the leak and any ceiling damage
- Whether water was stopped or is still active
- Tenant availability (note: for active leaks, vendor may need access even if tenant is not home)
- Access instructions for BOTH the reporting unit and the upstairs unit if applicable

## Suggested tenant communication

**Acknowledging the issue**: "That's not something that can wait. Let me get a plumber out to you as quickly as possible. In the meantime, can you put a bucket or some towels under the drip and move anything valuable away from the area?"

**If near electrical**: "Because the water is near a light fixture, I need you to go to your breaker panel and turn off that circuit right now. Don't use that light or outlet until the plumber says it's safe."

**If upstairs tenant not reachable**: "I wasn't able to reach your upstairs neighbor yet, but I'm dispatching a plumber who can access both units. They should be there within [window]."

## Notes for coordinator agent

- Always ask about proximity to electrical. Water through a light fixture is Critical severity that tenants often underestimate.
- In multifamily, this is a two-unit coordination problem. The vendor needs access to the reporting unit AND the unit above. Make sure access instructions and contact info for both units are in the work order.
- If the upstairs unit's tenant is not home and the property has no lockbox/key access, escalate to the property manager for emergency access authorization.
- Ceiling leaks get worse fast. A "slow drip" can become a stream in hours if the source isn't stopped. Err toward faster dispatch.
- After the leak is fixed, there will likely be a follow-up for drywall and paint repair. Create a separate standard-priority work order for that once the plumber confirms the source is resolved and the area is dry (usually 3-7 days of drying time before repair).
- Leak detection + repair plus ceiling repair afterward can add up. Flag for NTE if both together exceed threshold.
