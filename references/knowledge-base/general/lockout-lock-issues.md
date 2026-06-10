---
id: KB-GEN-002
category: general
subcategory: locks-keys
title: Lockout and Lock/Key Issues
severity: medium
tenant_fixable: false
tenant_responsible: sometimes
required_photos: false
required_videos: false
typical_resolution_minutes: 5
response_target_hours: 4
jurisdictions: all
last_reviewed: 2026-05-05
---

# Lockout and Lock/Key Issues

## Symptoms covered

- Tenant locked out of unit (no key, key inside, key lost)
- Key broken off in lock
- Deadbolt won't turn (sticking, frozen, misaligned)
- Lock mechanism broken (knob spins freely, won't latch)
- Key doesn't work (wrong key, worn key, lock rekeyed without their knowledge)

Does NOT cover: tenant locked out of building common area (contact building management), tenant locked inside unit and cannot get out (call 911, this is a fire safety issue), mailbox lock issues (contact postal service or building management).

## Intake questions for tenant

1. Are you locked out of your unit right now, or is there a lock problem you're reporting?
2. If locked out: where are you right now? Are you safe? Is it daytime or nighttime?
3. Do you have another way in? (Roommate with a key, spare with a neighbor, back door, management office hours.)
4. For lock malfunction: which lock? (Front door deadbolt, front door knob, back door, bedroom.)
5. Is there a security concern? (Broken lock on exterior door means anyone could enter.)

**Classification check**: Check the company's configured lockout policy in `assets/config.yaml`. Classification depends on company policy and circumstances:
- After-hours lockout with no safe alternative → may be Emergency per company policy
- Daytime lockout → typically Medium
- Broken exterior lock that compromises security → Medium to High depending on time of day
- Lock malfunction but tenant is inside → standard

## Diagnostic decision tree

```
START
│
├─ Is the tenant LOCKED OUT right now?
│   ├─ Is it after hours / dark / unsafe area?
│   │   └─ Check company lockout policy in config.
│   │       └─ If policy classifies as emergency → DISPATCH locksmith
│   │           immediately. Do not triage.
│   │       └─ If policy classifies as urgent → DISPATCH locksmith
│   │           within 1-2 hours.
│   ├─ Is it during business hours?
│   │   ├─ Does the management office have a spare key?
│   │   │   └─ Yes → direct tenant to the office. RESOLVED.
│   │   ├─ Is there a lockbox at the property with a key?
│   │   │   └─ Yes → provide lockbox code if authorized. RESOLVED.
│   │   ├─ Does a roommate have a key and can come let them in?
│   │   │   └─ Yes → tenant waits for roommate. RESOLVED.
│   │   └─ No alternatives → DISPATCH locksmith.
│   ├─ Is a child, pet, or vulnerable person locked inside?
│   │   └─ Yes → URGENT dispatch regardless of time. If child is in
│   │       danger (hot car equivalent, very young child alone),
│   │       advise tenant to call 911 for immediate entry.
│   └─ Is tenant locked out due to a broken lock (not lost key)?
│       └─ Key broken in lock, lock jammed → DISPATCH locksmith.
│
├─ Is the DEADBOLT sticking or hard to turn?
│   ├─ At Level 3+: has the tenant tried lubricating the lock?
│   │   └─ Graphite powder or WD-40 sprayed into the keyhole.
│   │       Insert key, work back and forth.
│   │       └─ If it frees up → RESOLVED (note: WD-40 is a temporary
│   │           fix, graphite is better long-term)
│   │       └─ If still sticking → DISPATCH locksmith
│   ├─ Is the door itself warped or misaligned? (Does the bolt not
│   │   line up with the strike plate?)
│   │   └─ Yes → this is a door alignment issue, not a lock issue.
│   │       DISPATCH handyman.
│   └─ Is it frozen? (Cold weather, exterior door.)
│       └─ Warm the key with hands/lighter. Try de-icer if available.
│           DO NOT pour hot water (it refreezes).
│           └─ If it opens → RESOLVED (temporary, will refreeze)
│           └─ If not → DISPATCH locksmith
│
├─ Is the LOCK BROKEN (knob spins, won't latch, won't lock)?
│   ├─ Is this an EXTERIOR door?
│   │   └─ Yes → SECURITY CONCERN. Classify as urgent minimum.
│   │       If it's nighttime and the door cannot be secured at all,
���   │       classify per company lockout/security policy (may be
│   │       emergency). DISPATCH locksmith urgently.
│   │   └─ In the meantime: can the tenant use a chain lock, deadbolt
│   │       (if separate from broken knob), or prop something against
│   │       the door? Temporary measure only.
│   ├─ Is this an INTERIOR door?
│   │   └─ Standard priority. Not a security issue. DISPATCH handyman.
│
├─ KEY DOESN'T WORK (not broken, just won't turn)
│   ├─ Is this a new tenant? → possible previous tenant's locks weren't
│   │   rekeyed. Escalate to PM for rekeying authorization.
│   ├─ Has the key worked before? → may be worn. Try jiggling while
│   │   turning. If it works intermittently → DISPATCH locksmith for
│   │   lock replacement or rekeying.
│   └─ Did someone rekey without tenant knowledge? → escalate to PM.
│
└─ KEY BROKEN IN LOCK
    └─ DISPATCH locksmith. Tenant cannot resolve this. Do NOT ask them
        to try to extract it (pliers, tweezers, etc.) as this can push
        it further in and damage the cylinder.
```

## Tenant-fixable resolution steps

Most lock issues are not tenant-fixable. Limited options:

1. **Sticking deadbolt** (Level 3+): Apply graphite powder or a spray lubricant (WD-40) into the keyhole. Insert key, work back and forth several times. If it frees up, resolved.

2. **Frozen lock** (cold weather): Warm the key with your hands or a lighter. Insert and gently work back and forth. Do NOT pour hot water (refreezes worse). If de-icer spray is available, use that.

## When to dispatch

- Tenant locked out with no alternative access
- Broken exterior lock (security compromise)
- Key broken in lock
- Lock won't function after lubrication
- Door misalignment preventing deadbolt from engaging
- Any lockout where a child, pet, or vulnerable person is inside

## Vendor category to dispatch

Locksmith for lockouts, broken locks, rekeying, and key-in-lock extraction. Handyman for door alignment/warping issues. Check config for preferred locksmith and after-hours availability.

## Temporary mitigation while awaiting dispatch

- **Lockout**: If the tenant is outside and it's cold, direct them to a nearby warm location (lobby, neighbor's unit, car) if dispatch is more than 30 minutes away.
- **Broken exterior lock at night**: Chain lock or deadbolt if a secondary lock exists. Prop a chair under the door handle. This is temporary only. Do not suggest the tenant leave the door unsecured overnight.
- **Sticking lock**: Lubricate with graphite as a temporary measure until replacement.

## Tenant responsibility notes

- **Lost key**: often tenant-responsible for locksmith call. Check company policy. Many companies charge the tenant for lockouts caused by lost keys. Some cover the first occurrence.
- **Broken lock mechanism**: always owner-responsible. Locks wear out.
- **Key broken in lock**: usually owner-responsible (worn lock contributed). Grey area if tenant forced a wrong key.
- **Rekeying after move-in**: always owner-responsible.
- **Lockout due to lock malfunction**: always owner-responsible.

Check company policy in config for lockout cost allocation before communicating to the tenant.

## Work order fields to capture at dispatch

- Type of issue (lockout vs. malfunction vs. broken)
- Which door/lock
- Whether it's an exterior or interior door
- Whether there's a security concern right now
- Time of day and whether tenant is outside
- Whether tenant has ID (locksmith may require proof of residency)
- Property address and unit number
- Whether a spare key exists at the office/lockbox
- Tenant contact for locksmith to call when en route

## Suggested tenant communication

**Lockout, dispatching locksmith**: "I'm sending a locksmith to let you in. They should be there within [window]. Stay safe and warm. They'll need to see an ID to verify you live there, so have that ready."

**Lost key, company charges tenant**: "I'll get a locksmith out to you right now. I want to let you know upfront that per your lease, lockout calls for lost keys are the tenant's responsibility costwise. I wanted you to know before we dispatch."

**Broken lock, security concern**: "That's a security issue, so I'm treating this as a priority. I'll have a locksmith out today to replace the lock. In the meantime, if you have a chain lock or deadbolt that still works, use that."

## Notes for coordinator agent

- Lockout calls are extremely time-sensitive from the tenant's perspective. They're standing outside their home. Move quickly.
- Always verify the company's lockout policy before classifying. This is one of the few issues where classification is company-configured rather than universal.
- Locksmith fees for after-hours calls are typically 2-3x the daytime rate. Note this in the work order for cost tracking.
- If the tenant is locked out and there's a lockbox with a spare key, always try that before dispatching a locksmith. Saves a service call.
- After-hours lockouts are one of the most common after-hours calls. Make sure the vendor list has a 24/7 locksmith.
- If a lock is broken on an exterior door and cannot be secured, this may be a High severity issue (security of the dwelling). Treat with urgency regardless of time of day.
- For rekeying between tenants: this should happen at every turnover. If it didn't and a new tenant reports their key doesn't work, that's a management failure, not a tenant issue. Expedite.
- Some properties have smart locks or electronic access. Troubleshooting for those is different (battery replacement, code reset, app issues). If the property uses smart locks, check config for the specific system and its troubleshooting path.
