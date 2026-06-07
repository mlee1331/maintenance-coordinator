---
id: KB-PLUMB-001
category: plumbing
subcategory: garbage-disposal
title: Garbage Disposal Not Working
severity: low
tenant_fixable: true
tenant_responsible: never
required_photos: false
required_videos: false
typical_resolution_minutes: 10
response_target_hours: 72
jurisdictions: all
last_reviewed: 2026-05-05
---

# Garbage Disposal Not Working

## Symptoms covered

- Disposal makes no sound when switched on (completely dead)
- Disposal hums but does not spin
- Disposal trips the reset button repeatedly
- Disposal works intermittently

Does NOT cover: disposal leaking (see KB-PLUMB-010), disposal making grinding noises with nothing inside, disposal backing up into other sink (that's a drain issue, see KB-PLUMB-003).

## Intake questions for tenant

1. When you flip the switch, what happens? Nothing at all, a humming sound, or it works but sounds wrong?
2. Is there standing water in the sink right now?
3. Have you noticed any leaking under the sink?
4. Did you put anything unusual down the disposal recently? (Bones, fibrous vegetables, grease, non-food items.)

If there is standing water AND a humming sound, prioritize the jam resolution before addressing the water. If there is a leak, reclassify as KB-PLUMB-010.

## Diagnostic decision tree

```
START
│
├─ Disposal makes NO sound at all
│   ├─ Check: is it plugged in? (Some units have a plug under the sink.)
│   │   └─ If unplugged → plug in, test again
│   ├─ Check: press the red reset button on the bottom of the unit
│   │   └─ If it clicks and disposal now works → RESOLVED
│   ├─ Check: is the wall switch working? (Try turning on/off.)
│   │   └─ If switch seems dead → check breaker (see KB-ELEC-001)
│   └─ If none of the above resolve → DISPATCH
│
├─ Disposal HUMS but does not spin (jammed)
│   ├─ Turn OFF the switch. Do not put hands inside.
│   ├─ Check: do you have an Allen wrench (hex key)? Look for one attached
│   │   to the unit or a 1/4" hex key. (Most InSinkErator models use 1/4".
│   │   Some other brands differ.)
│   ├─ If the unit has a hex hole on the bottom center: insert hex key
│   │   and work back and forth until it moves freely.
│   ├─ If there is NO hex hole (some brands don't have one): insert a
│   │   wooden broom handle or thick wooden spoon handle into the top of
│   │   the disposal and push against the impeller blades to free the jam.
│   │   Work it back and forth.
│   ├─ Remove the hex key, press reset button, run cold water, flip switch
│   │   └─ If it spins freely → RESOLVED
│   │   └─ If still jammed → DISPATCH
│   └─ If tenant has no hex key and cannot locate one → DISPATCH
│       (Note: at Level 4-5, consider mailing a hex key to the tenant
│       if timeline allows and the unit is not urgent.)
│
├─ Disposal trips reset repeatedly
│   ├─ Turn off switch, wait 5 minutes, press reset, test
│   │   └─ If it holds → RESOLVED (likely thermal overload from overuse)
│   │   └─ If it trips again immediately → DISPATCH (electrical issue or
│   │       motor failure)
│
└─ Disposal works intermittently
    ├─ Check: is it the switch? (Toggle on/off several times.)
    │   └─ If switch feels loose or inconsistent → DISPATCH (switch replacement)
    ├─ Press reset, test again
    │   └─ If it works after reset → likely thermal overload, advise tenant
    │       to run shorter cycles and more cold water
    │   └─ If still intermittent → DISPATCH
```

## Tenant-fixable resolution steps

1. **Reset button fix**: Locate the red reset button on the bottom of the disposal unit (under the sink). Press it firmly until it clicks. Run cold water and flip the switch. If it works, you're done.

2. **Hex key fix for jams**: Turn off the disposal switch. If the unit has a hex key hole on the bottom center, use a 1/4" Allen wrench (often attached to the unit by a small clip, or in a kitchen junk drawer). Insert and work back and forth until it turns freely. If there's no hex hole, insert a wooden broom handle or thick wooden spoon handle into the top of the disposal and push against the blades to free the jam. Either way: remove tool, press reset, run cold water, flip the switch.

3. **Thermal overload**: If the disposal stopped after heavy use, wait 5 minutes for it to cool, press reset, try again. Advise running cold water for 15 seconds before and after using the disposal, and feeding waste in slowly.

## When to dispatch

- Tenant tried reset and hex key with no improvement
- Disposal is leaking (separate issue, different vendor scope)
- Disposal trips the breaker (not just its own reset button)
- Disposal is making a grinding noise with nothing inside (bearing failure)
- Switch appears faulty
- Tenant unable or unwilling to try the steps above

## Vendor category to dispatch

Handyman preferred. Disposal repair and replacement is straightforward work that most handymen handle. Plumber only if the issue involves supply lines or drain connections beyond the disposal itself. Not an electrician unless the issue is confirmed to be the switch or wiring.

## Temporary mitigation while awaiting dispatch

- If standing water in the sink: don't use that side of the sink. Use the other side if it's a double sink.
- If the disposal is jammed and humming: leave the switch OFF. A jammed disposal running continuously can burn out the motor or trip the breaker.
- Remind tenant not to pour grease or put fibrous food down the disposal side of the sink while waiting.

## Tenant responsibility notes

Never tenant-responsible for disposal mechanical failure. If the tenant jammed the disposal with a non-food item or misused it, the repair is still owner-coordinated. Some leases have language about disposal misuse, but that's a PM determination after the fact, not something the coordinator decides.

## Work order fields to capture at dispatch

- Symptom (dead, humming/jammed, tripping reset, intermittent)
- Whether tenant tried reset button and hex key
- Whether there's standing water in the sink
- Whether there's also a leak (reclassify to KB-PLUMB-010 if so)
- Owner-provided or tenant-owned
- Make/model if visible
- Tenant availability

## Suggested tenant communication

**After successful self-fix**: "Nice work getting that cleared. Going forward, run cold water for about 15 seconds before and after you use the disposal, and feed things in slowly. Avoid putting bones, celery, onion skins, or grease down there. That'll keep it running smoothly."

**Dispatching**: "It sounds like the disposal is beyond what we can fix remotely. I'll get someone out to take a look. In the meantime, just don't use that side of the sink."

## Notes for coordinator agent

- This is one of the most common calls and one of the most frequently tenant-resolvable. At Level 3+, push gently on the hex key fix before dispatching.
- Never ask the tenant to put their hand inside the disposal for any reason.
- If the disposal is old and the motor has failed, the vendor will likely recommend replacement. Flag for NTE check.
- If tenant reports a bad smell from the disposal, that's not a repair issue. Advise running cold water with ice cubes and a cut lemon, or suggest a disposal cleaning product. Not a dispatch situation unless the smell persists after cleaning.
