---
id: KB-APPL-001
category: appliances
subcategory: general
title: Appliance Not Starting or Not Responding
severity: low
tenant_fixable: true
required_photos: false
required_videos: false
typical_resolution_minutes: 10
jurisdictions: all
last_reviewed: 2026-05-05
---

# Appliance Not Starting or Not Responding

## Symptoms covered

- Owner-provided appliance will not turn on at all (refrigerator, dishwasher, oven/stove, microwave, washer, dryer)
- Appliance has no power (display blank, no lights, no response to buttons)
- Appliance turns on but immediately shuts off

Does NOT cover: appliance works but performs poorly (separate entries per appliance type), appliance making unusual noises while running, appliance leaking, refrigerator not cooling (see KB-APPL-002 when created), tenant-owned appliances (not a maintenance issue).

## Intake questions for tenant

1. Which appliance? Is it owner-provided (came with the unit) or did you bring it?
2. What happens when you try to turn it on? Nothing at all, lights flash briefly, display shows an error, or it starts then stops?
3. Did anything happen before it stopped working? Power outage, storm, strange noise, burning smell?
4. Is anything else in the kitchen/laundry area also not working? (Helps identify if it's a circuit issue vs. appliance issue.)

**If tenant-owned appliance**: This is not a maintenance issue. Politely let the tenant know that tenant-owned appliances are their responsibility to repair or replace. Offer to help troubleshoot if configured aggressiveness level allows, but no dispatch.

**If burning smell**: Do not troubleshoot. Classify per `severity-classification.md`. Advise tenant to unplug the appliance and not use it.

## Diagnostic decision tree

```
START
│
├─ Is there a BURNING SMELL from the appliance?
│   └─ Yes → STOP. Tell tenant to unplug it (if safe to reach the plug)
│       and not use it. DISPATCH. Note potential fire hazard in work order.
│
├─ Are OTHER things in the same area also dead?
│   └─ Yes → this is likely a breaker or GFCI issue, not an appliance issue.
│       → Follow KB-ELEC-001 (breaker tripped) first.
│       → If power is restored and appliance works → RESOLVED
│
├─ Is the appliance PLUGGED IN?
│   ├─ Can the tenant see and reach the plug?
│   │   (Refrigerators: pull gently away from wall or check behind.
│   │   Dishwashers: usually hardwired, skip this step.
│   │   Washers/dryers: check behind.)
│   ├─ If unplugged → plug in. Test.
│   │   └─ If it works → RESOLVED
│   ├─ If plugged in → unplug, wait 30 seconds, plug back in (power cycle).
│   │   └─ If it starts → RESOLVED (electronics reset)
│   │   └─ If still dead → continue
│   └─ If tenant cannot reach the plug → skip, continue
│
├─ Check the OUTLET
│   ├─ Plug something else into the same outlet (phone charger, lamp).
│   │   Does the outlet work?
│   │   └─ No → outlet is dead. See KB-ELEC-001. Resolve the power issue
│   │       first, then retest the appliance.
│   │   └─ Yes → outlet is fine. Problem is the appliance. Continue.
│
├─ Is there a GFCI outlet nearby?
│   ├─ Some kitchen and laundry appliances are on GFCI-protected circuits.
│   │   Check for a GFCI outlet with TEST/RESET buttons near the appliance.
│   │   Press RESET.
│   │   └─ If appliance powers on → RESOLVED
│   │   └─ If GFCI won't stay reset → KB-ELEC-001 for GFCI issues
│
├─ Does the appliance have a DISPLAY or ERROR CODE?
│   ├─ If display shows an error code → note the code. Check if the
│   │   appliance manual is accessible (often inside the door or in a
│   │   drawer under the unit).
│   │   └─ At Level 3+: look up common error codes for the brand/model
│   │       if identifiable. Some codes are simple resets.
│   │   └─ If error code indicates a specific part failure → DISPATCH
│   │       with the error code included in the work order.
│   └─ If display is blank and power cycle didn't help → DISPATCH
│
├─ Specific appliance checks:
│   │
│   ├─ REFRIGERATOR
│   │   ├─ Check if the temperature dial inside got bumped to OFF.
│   │   ├─ Listen: any humming or clicking from the back/bottom?
│   │   │   └─ Clicking = compressor trying to start, failing. DISPATCH.
│   │   │   └─ Humming = compressor running. If not cooling, that's a
│   │   │       different issue (KB-APPL-002). Still running = not "dead."
│   │   │   └─ Silence = no power reaching compressor. Double-check outlet.
│   │   └─ If completely silent and outlet is confirmed working → DISPATCH
│   │
│   ├─ DISHWASHER
│   │   ├─ Is the door latching fully? Most won't start with the door ajar.
│   │   ├─ Is there a delay start or child lock activated? (Check display.)
│   │   ├─ Try: hold the start/reset button for 3-5 seconds (cancels
│   │       previous cycle). Then start a new cycle.
│   │   └─ If still nothing → DISPATCH
│   │
│   ├─ OVEN / STOVE
│   │   ├─ Electric: check breaker (ovens are usually on a dedicated 240V
│   │       double breaker). Reset if tripped.
│   │   ├─ Gas: are the burners clicking but not lighting?
│   │       └─ Clean the igniter area with a dry cloth or toothbrush.
│   │           Sometimes food debris blocks the spark.
│   │       └─ If still not lighting → is there gas flow? (Turn on
│   │           burner, listen for hiss.)
│   │           └─ No hiss → gas may be off. Check gas shutoff valve.
│   │           └─ Hiss but no ignition → DISPATCH
│   │   ├─ Is it just the oven that won't work but burners are fine?
│   │       → Likely igniter or control board failure. DISPATCH.
│   │   └─ If gas smell is present without burners on → CRITICAL.
│   │       Stop troubleshooting. Evacuate.
│   │
│   ├─ WASHER
│   │   ├─ Is the door/lid locking? (Front-loaders won't start with an
│   │       unlocked door.)
│   │   ├─ Is there water supply? Check that the hot and cold valves behind
│   │       the washer are open (handles parallel to hoses = open).
│   │   ├─ Power cycle: unplug or turn off at breaker for 60 seconds. Restart.
│   │   └─ If still dead → DISPATCH
│   │
│   └─ DRYER
│       ├─ Electric dryers use a 240V outlet (large plug). Is it fully
│       │   seated? Sometimes they work loose.
│       ├─ Check the dedicated dryer breaker (usually double breaker).
│       ├─ Is the lint trap full? Clean it and test.
│       ├─ FIRE HAZARD CHECK: if the dryer gets very hot on the outside,
│       │   exhaust at the vent termination is weak or absent, or clothes
│       │   take 2+ cycles to dry, the vent is likely blocked. This is a
│       │   fire hazard. DISPATCH with urgency regardless of whether the
│       │   dryer "starts." Do not continue troubleshooting.
│       └─ If still dead after plug/breaker/lint check → DISPATCH
│
└─ If none of the above resolve → DISPATCH
```

## Tenant-fixable resolution steps

1. **Power cycle**: Unplug the appliance (or turn off at breaker), wait 30-60 seconds, plug back in or reset breaker. Many modern appliances have electronic controls that need a hard reset.

2. **Check the outlet**: Plug something else in. If the outlet is dead, it's an electrical issue (KB-ELEC-001), not an appliance issue.

3. **GFCI reset**: Find and press the RESET button on any GFCI outlet protecting the appliance's circuit.

4. **Check controls**: Make sure the appliance isn't on a delay start, child lock, or turned to OFF. Dishwasher doors must be fully latched. Washer lids must be locked.

5. **Gas appliance valve check**: Make sure the gas shutoff valve for the appliance is in the ON position (handle parallel to pipe).

## When to dispatch

- Burning smell from the appliance
- Appliance completely unresponsive after power cycle and outlet is confirmed working
- Error code indicating part failure
- Refrigerator clicking repeatedly (compressor failure)
- Gas smell from a gas appliance (Critical)
- Appliance starts then immediately shuts off repeatedly
- Tenant unable or unwilling to perform steps

## Vendor category to dispatch

Handyman for simple appliance issues (door latches, power supply problems, outlet/breaker troubleshooting, disposal replacement, dryer vent cleaning). Appliance repair technician for mechanical or internal failures (compressor, motor, control board, sealed system, gas valve solenoid). A capable handyman is cheaper and can handle a lot of routine appliance calls. Check the vendor list for appliance repair capability and whether they service the specific brand.

For gas appliance issues, some overlap with plumber (gas line) or HVAC tech. If the issue is clearly the appliance and not the gas supply, appliance repair is correct.

## Notes for coordinator agent

- Always confirm the appliance is owner-provided before dispatching. Tenant-owned appliance repairs are not a maintenance issue.
- Power cycles fix a surprising number of modern appliance issues. Electronic control boards lock up just like computers. Always try this first at Level 2+.
- Refrigerator failure with food loss risk is a High severity (habitability) issue (see severity-classification.md). If the fridge is dead and confirmed not a power issue, classify appropriately and dispatch within the required window.
- Appliance repair vs. replacement: if the appliance is old and the repair estimate approaches 50% of replacement cost, flag for owner decision. The vendor will usually advise on this. Flag for NTE review either way.
- For washer/dryer issues, confirm whether they're owner-provided. In many units, especially single-family, washers and dryers are owner-provided. In some multifamily units, they're shared laundry room units (different maintenance path) or tenant-provided hookups only.
- Error codes are gold for the technician. Always capture them in the work order if the tenant can read them off the display.
