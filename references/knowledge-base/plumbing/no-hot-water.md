---
id: KB-PLUMB-004
category: plumbing
subcategory: water-heater
title: No Hot Water
severity: high
tenant_fixable: true
tenant_responsible: never
required_photos: false
required_videos: false
typical_resolution_minutes: 15
response_target_hours: 24
jurisdictions: all
last_reviewed: 2026-05-05
---

# No Hot Water

## Symptoms covered

- No hot water anywhere in the unit
- Hot water runs out quickly (was fine before, now only lasts a few minutes)
- Water is lukewarm but never gets hot
- Hot water works at some fixtures but not others

Does NOT cover: water heater leaking (dispatch directly, risk of water damage), water heater making popping/banging noises (dispatch, sediment buildup), gas smell near water heater (Critical severity, dispatch immediately and advise tenant to leave).

## Intake questions for tenant

1. Is the hot water out everywhere, or just at one fixture?
2. When did you last have hot water?
3. Do you know what type of water heater you have? (Tank, tankless, electric, gas.) If not, where is the water heater located?
4. Has anyone in the unit used a lot of hot water recently? (Long showers, laundry, dishwasher.)
5. Do you smell gas anywhere near the water heater?

**Classification check**: No hot water is a High severity (habitability) issue in all US jurisdictions. Check `habitability-response-windows.md` for the required response time. Most states require restoration within 24-48 hours. Some are shorter. If the response window is tight, dispatch immediately without triage.

If the tenant reports a gas smell near the water heater, reclassify as Critical immediately.

## Diagnostic decision tree

```
START
│
├─ Is there a GAS SMELL near the water heater?
│   └─ Yes → STOP. Critical. Do not troubleshoot. Tell tenant to
│       leave, do not flip switches. Dispatch immediately.
│
├─ Is it just ONE FIXTURE with no hot water?
│   └─ Yes → the water heater is probably fine. The issue is at that
│       fixture (cartridge, valve, or supply line).
│       ├─ Is it a single-handle faucet?
│       │   └─ The mixing cartridge may have failed. DISPATCH (plumber).
│       ├─ Is it a two-handle faucet?
│       │   └─ Is the hot side handle turning the valve? (Sometimes they
│       │       strip.) Try turning it further.
│       │       └─ If hot water appears → RESOLVED
│       │       └─ If handle spins freely → DISPATCH (plumber)
│       └─ If unclear → DISPATCH
│
├─ Did the hot water run out QUICKLY (was working, now cold)?
│   └─ How many people have used hot water in the last hour?
│       └─ If heavy recent use → the tank is simply depleted. Wait 30-45
│           minutes for recovery. Test again.
│           └─ If hot water returns → RESOLVED. Tank capacity issue.
│               Normal if multiple people showered back-to-back.
│           └─ If still no hot water after 45 minutes → continue below
│
├─ ELECTRIC water heater (no pilot light, plugged in or hardwired)
│   ├─ Check the breaker panel for a breaker labeled "water heater" or
│   │   "WH." Is it tripped?
│   │   └─ If tripped → reset (flip off, wait 10 seconds, flip on).
│   │       Wait 30-45 minutes. Test.
│   │       └─ If hot water returns → RESOLVED (monitor for repeat trip)
│   │       └─ If breaker trips again → DISPATCH (do not reset again)
│   │       └─ If breaker holds but still no hot water after 45 min
│   │           → DISPATCH (likely heating element failure)
│   ├─ Some electric water heaters have a reset button (red, on the unit
│   │   or behind a small panel on the upper thermostat).
│   │   └─ If accessible and tenant is comfortable → press reset.
│   │       Wait 30-45 minutes. Test.
│   │       └─ If hot water returns → RESOLVED
│   │       └─ If it trips again → DISPATCH
│   └─ If tenant cannot find breaker or reset → DISPATCH
│
├─ GAS water heater (has a pilot light or electronic ignition)
│   ├─ SAFETY: if tenant smells gas at any point, STOP and reclassify.
│   ├─ Is the gas valve in the ON position? (Usually a knob with OFF,
│   │   PILOT, and ON settings.)
│   │   └─ If set to OFF or PILOT → turn to ON. Wait 30-45 minutes.
│   │       └─ If hot water returns → RESOLVED
│   │       └─ If not → continue
│   ├─ Can the tenant see a pilot light or status indicator on the unit?
│   │   └─ Newer units: look for a blinking status light. Green = good.
│   │       Red or no light = fault.
│   │   └─ Older units: look through the small window at the bottom
│   │       for a blue flame.
│   │       └─ If no flame and tenant is comfortable relighting per the
│   │           instructions on the unit → they can try.
│   │       └─ If no flame and not comfortable → DISPATCH
│   │       └─ If flame is present but no hot water → DISPATCH
│   │           (thermostat or gas valve issue)
│   └─ If tenant cannot locate or identify the water heater type → DISPATCH
│
├─ TANKLESS water heater
│   ├─ Is there an error code on the display?
│   │   └─ If yes → note the code. DISPATCH with the error code.
│   │       (Tankless error codes are unit-specific and not tenant-fixable.)
│   ├─ Try power cycling: turn the unit off (switch or breaker), wait 30
│   │   seconds, turn back on. Run hot water and wait 30-60 seconds.
│   │   └─ If hot water flows → RESOLVED
│   │   └─ If error returns or no hot water → DISPATCH
│   └─ If tenant isn't sure how to power cycle it → DISPATCH
│
└─ If none of the above resolve → DISPATCH
```

## Tenant-fixable resolution steps

1. **Wait for tank recovery**: If hot water was used heavily in the last hour, wait 30-45 minutes and test again. Tank water heaters need time to reheat.

2. **Reset the breaker** (electric): Find the water heater breaker. Flip off, wait 10 seconds, flip on. Wait 30-45 minutes for the tank to heat.

3. **Press the reset button** (electric): Some units have a red reset button on the upper thermostat (behind a small access panel). Press it. Wait 30-45 minutes.

4. **Check the gas valve** (gas): Find the knob on the gas control. Make sure it's set to ON, not OFF or PILOT.

5. **Relight the pilot** (gas, older units): Follow the lighting instructions printed on the unit. Only if tenant is comfortable and there is NO gas smell.

6. **Power cycle** (tankless): Turn off at the switch or breaker. Wait 30 seconds. Turn back on. Run hot water for 30-60 seconds.

## When to dispatch

- Gas smell (Critical, immediate)
- Breaker trips repeatedly (electrical fault)
- No pilot and tenant uncomfortable relighting
- Pilot is lit but no hot water (thermostat/gas valve issue)
- Tankless showing error code
- Electric unit with breaker holding but no hot water after 45 minutes (element failure)
- Hot water only at some fixtures (mixing valve or cartridge issue)
- Water heater leaking (water damage risk, dispatch as urgent)
- Tenant unable or unwilling to perform steps

## Vendor category to dispatch

Plumber for most water heater issues. Some HVAC companies also service water heaters (especially if it's a combi unit or connected to the HVAC system). Check the vendor list for water heater capability. If the issue is electrical (breaker keeps tripping), an electrician may be needed as secondary dispatch.

## Temporary mitigation while awaiting dispatch

- Tenant will have no hot water until fixed. Boiling water on the stove for essential needs (dishes, sponge baths) is the only workaround.
- If gas was turned off or pilot was extinguished, don't keep trying to relight. Wait for the plumber.
- If the breaker was tripped and reset but heat hasn't returned after 45 minutes, leave the breaker on and wait for the tech. Don't keep cycling it.

## Tenant responsibility notes

Never tenant-responsible. Water heater maintenance and replacement are always owner responsibility. Even if the tenant hasn't reported a gradual decline (which would have triggered earlier maintenance), the failure is still on the owner.

## Work order fields to capture at dispatch

- Type of water heater (gas, electric, tankless, unknown)
- Whether it's total loss of hot water or partial (one fixture vs. all)
- What tenant tried (breaker, gas valve, pilot, power cycle)
- Any error codes (tankless)
- Whether there's a gas smell (Critical reclassification)
- Whether the heater is leaking (separate issue, see KB-PLUMB-009)
- Age of unit if visible
- Whether this is shared with other units
- Tenant availability

## Suggested tenant communication

**Dispatching**: "No hot water is something I take seriously. I'm getting a plumber out as quickly as I can. In the meantime, if you need hot water for dishes, boiling some on the stove is about the only option."

**After tenant resolves via breaker/pilot**: "Glad that got it going. If it happens again, let me know right away because a repeat trip usually means something mechanical is going on."

**If replacement likely**: "Given the age of the unit and what you're describing, the plumber may recommend replacing it. I'll flag that for the owner and keep you updated. Replacements usually take a few hours once approved."

## Notes for coordinator agent

- No hot water is High severity (habitability) in every US state. Always check the response window before deciding whether to triage or dispatch immediately. If the window is 24 hours or less and triage will take time, just dispatch.
- Never ask a tenant to access the interior of a water heater, touch electrical connections, or work on gas lines.
- Tank water heaters have a typical lifespan of 8-12 years. If the unit is old and the failure is total (element or thermostat), the vendor will likely recommend replacement. Flag for NTE and owner approval.
- Tankless water heaters are more complex and almost never tenant-fixable beyond a power cycle. Dispatch without extensive triage.
- "Hot water runs out faster than it used to" (gradual decline over months) is usually sediment buildup in the tank. Not an emergency. Schedule a flush. Some companies include this in preventative maintenance (out of scope for v0.1, but note it for the tenant).
- If the property has a shared water heater (small multifamily), multiple tenants may report no hot water simultaneously. That's one dispatch, not multiple. Check whether other units in the same building have reported the same issue.
