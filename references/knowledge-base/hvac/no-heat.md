---
id: KB-HVAC-001
category: hvac
subcategory: heating
title: No Heat
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

# No Heat

## Symptoms covered

- Thermostat is set to heat but nothing happens
- Furnace/heat pump does not turn on at all
- Furnace turns on briefly then shuts off
- Heat comes on but blows cold air
- Baseboard/radiator heat not working

Does NOT cover: heat works but is uneven (that's a distribution issue), heat pump making unusual noises while running (that's a mechanical issue, dispatch directly), gas smell (that's Critical, dispatch immediately and advise tenant to leave).

## Intake questions for tenant

1. What type of heating do you have? (Furnace, heat pump, baseboard electric, radiator/boiler, wall heater, space heater provided by owner.) If they don't know, that's fine.
2. What's your thermostat set to, and what temperature is it showing in the unit?
3. When did you last have working heat?
4. Is anything happening at all when the thermostat calls for heat? (Fan running, clicking sounds, nothing.)
5. What's the current outdoor temperature?

**Classification check**: If outdoor temperature is at or below 32F and there is no heat at all, classify as Critical per `severity-classification.md`. Do not triage. Dispatch immediately.

If outdoor temperature is below 55F during heating season (generally October through April), classify as High. Check `habitability-response-windows.md` for the jurisdiction's required response time.

Only proceed with triage if the temperature situation does not trigger emergency classification.

## Diagnostic decision tree

```
START
│
├─ Thermostat check
│   ├─ Is the thermostat set to HEAT (not cool, not off, not auto)?
│   ├─ Is the temperature set above the current room temperature?
│   ├─ Does the thermostat have a display? Is it on?
│   │   └─ If display is blank → check batteries (many thermostats use AA or AAA)
│   │       └─ Replace batteries → test
│   │           └─ If heat comes on → RESOLVED
│   │           └─ If still blank → DISPATCH
│   └─ Is the thermostat set to a program/schedule that might be overriding?
│       └─ Switch to manual/hold mode, set to 72F, wait 2-3 minutes
│
├─ Breaker check
│   ├─ Find the breaker panel. Look for a breaker labeled "furnace," "HVAC,"
│   │   "heat pump," or "air handler."
│   ├─ Is it tripped (middle position) or off?
│   │   └─ Flip fully off, then back on. Wait 5 minutes.
│   │       └─ If heat starts → RESOLVED (monitor for repeat trips)
│   │       └─ If breaker trips again immediately → DISPATCH (do not
│   │           reset again, possible electrical issue)
│   └─ If breaker looks fine → continue
│
├─ Filter check (forced air systems only)
│   ├─ When was the filter last changed?
│   ├─ Can the tenant locate and check the filter?
│   │   └─ If filter is visibly clogged (solid gray/brown, cannot see
│   │       through it) → replace if tenant has a replacement, or
│   │       remove and run without filter for a few hours to confirm
│   │       the filter was the issue (do not run without a filter for
│   │       more than a day -- it coats the coil and blower with dust)
│   │       └─ If heat works without filter → filter was the problem.
│   │           Advise tenant to buy a replacement immediately. RESOLVED.
│   │       └─ If still no heat → continue
│   └─ If tenant cannot find or access filter → continue
│
├─ Furnace switch check
│   ├─ Some furnaces have a power switch on or near the unit that looks
│   │   like a light switch. Is it on?
│   │   └─ If off → flip on, wait 5 minutes
│   │       └─ If heat starts → RESOLVED
│
├─ Gas furnace: is the pilot lit / is gas flowing?
│   ├─ SAFETY: do NOT ask tenant to light a pilot manually unless they
│   │   confirm they are comfortable doing so and there is NO gas smell.
│   ├─ Can the tenant see a flame through the furnace window?
│   │   └─ If no flame visible and this is a newer furnace (electronic
│   │       ignition) → this is not something the tenant can fix. DISPATCH.
│   │   └─ If no flame and older furnace with standing pilot → ask if
│   │       they want to try relighting per the instructions on the unit.
│   │       If not comfortable → DISPATCH.
│   └─ Is the gas valve in the ON position? (Handle parallel to pipe = on)
│       └─ If off → turn on, wait 5 minutes
│           └─ If heat starts → RESOLVED
│
├─ Heat pump: is the outdoor unit running?
│   ├─ Can the tenant safely look at the outdoor unit?
│   ├─ Is it running (fan spinning, humming)?
│   │   └─ If outdoor unit is covered in ice → it may be in defrost
│   │       mode. Wait 30 minutes and recheck.
│   │   └─ If outdoor unit is completely iced over and not defrosting
│   │       → DISPATCH
│   │   └─ If outdoor unit is not running at all → check breaker for
│   │       outdoor unit (may be separate from indoor). If breaker fine
│   │       → DISPATCH
│
└─ If none of the above resolve → DISPATCH
```

## Tenant-fixable resolution steps

1. **Thermostat batteries**: Replace with fresh AA or AAA batteries. Most thermostats have a battery compartment on the back or bottom that pops off.

2. **Thermostat settings**: Set to HEAT mode, set temperature to 72F, switch from program/schedule to HOLD or manual. Wait 3 minutes.

3. **Breaker reset**: Find the HVAC breaker in the panel. Flip fully off, wait 10 seconds, flip back on. Wait 5 minutes for the system to restart.

4. **Filter replacement**: Pull out the old filter, replace with same size. If no replacement available, run without a filter for a few hours to confirm the filter was the problem, then get a replacement as soon as possible. Don't run more than a day without a filter -- dust coats the evaporator coil and blower.

5. **Furnace switch**: Locate the power switch on or near the furnace. Flip it on.

6. **Gas valve**: Locate the gas valve on the supply line to the furnace. Turn handle parallel to the pipe (on position).

## When to dispatch

- Outdoor temperature triggers emergency classification (dispatch immediately, skip triage)
- Breaker trips repeatedly when reset
- Furnace makes no response to any troubleshooting
- Furnace starts then shuts down within seconds (short cycling)
- Heat pump outdoor unit completely iced over
- Tenant reports gas smell at any point (reclassify as Critical immediately)
- Furnace is making banging, popping, or screeching sounds
- Tenant unable or unwilling to perform steps

## Vendor category to dispatch

HVAC technician. For emergencies, use the emergency HVAC vendor from config. For standard dispatch, use the primary HVAC vendor with best performance score for the property's area.

If the issue turns out to be electrical (breaker keeps tripping), the HVAC tech may recommend an electrician. That's a callback/secondary dispatch, not something to figure out before the first visit.

## Temporary mitigation while awaiting dispatch

- Space heaters: if the tenant has one, it can keep one room livable. Advise keeping it away from curtains, bedding, and furniture. Don't use the oven for heat (carbon monoxide risk with gas ovens, fire risk with all).
- If the company provides emergency space heaters, coordinate delivery.
- Layer up, close off unused rooms, use blankets over windows for insulation.
- If outdoor temp is at or below freezing and dispatch is not same-day: escalate to PM. Tenant may need temporary accommodation. Pipes can freeze.
- Open cabinet doors under sinks on exterior walls to prevent pipe freezing.

## Tenant responsibility notes

Never tenant-responsible for heating system failure. Filter replacement responsibility varies by lease (some require tenant to replace filters monthly), but a clogged filter causing a system shutdown is still owner-coordinated for the repair. The tenant's failure to replace a filter doesn't shift the heating repair to them.

## Work order fields to capture at dispatch

- Type of heating system (furnace, heat pump, baseboard, radiator/boiler, wall heater)
- Gas or electric
- Symptoms (nothing happens, runs briefly then stops, blows cold air)
- What tenant tried (thermostat, breaker, filter, furnace switch, gas valve, pilot)
- Current indoor temperature
- Current outdoor temperature
- Whether there's a gas smell (Critical reclassification)
- Whether this is a repeat call for the same issue
- Tenant availability (for emergency heat issues, vendor may need to come regardless)

## Suggested tenant communication

**Emergency (freezing temps)**: "No heat when it's this cold is an emergency. I'm dispatching someone right now. In the meantime, if you have a space heater, use it in one room with the door closed. Don't use the oven for heat. Open the cabinet doors under your kitchen and bathroom sinks to keep the pipes from freezing. If it's going to be overnight before someone can get there, I'm going to talk to the property manager about options."

**Standard dispatch**: "I'll get an HVAC tech scheduled for you. It's most likely a quick fix. In the meantime, bundle up and close off any rooms you're not using to keep the warm air concentrated."

**After thermostat/filter fix**: "Glad that got it working. For the filter, those should be swapped out every 1-3 months depending on the type. A clean filter keeps the system running right and keeps your air cleaner too."

## Notes for coordinator agent

- No heat is one of the most jurisdiction-sensitive issues. Always check the outdoor temperature and classify per `severity-classification.md` before starting triage.
- Never ask a tenant to work on gas lines, light a pilot if they smell gas, or access the furnace interior.
- Thermostat batteries and dirty filters account for a surprisingly large percentage of "no heat" calls. At Level 2+, always ask about these.
- If this is a repeat call (same unit, same season), skip triage and dispatch. The issue is likely mechanical and the tenant has already tried the basics.
- For heat pump systems in cold weather: heat pumps are less effective below certain temperatures and some have auxiliary/emergency heat strips. If the tenant says "it's running but not warming up" in very cold weather, ask if there's an "AUX" or "EM HEAT" setting on the thermostat. Switching to emergency heat may restore warmth while waiting for a tech.
- If the furnace is 15+ years old and needs a major component, replacement may be more economical than repair. Always flag for NTE and owner decision on major repairs.
