---
id: KB-HVAC-002
category: hvac
subcategory: cooling
title: AC Not Cooling / No Air Conditioning
severity: medium
tenant_fixable: true
required_photos: true
required_videos: false
typical_resolution_minutes: 15
jurisdictions: all
last_reviewed: 2026-05-05
---

# AC Not Cooling / No Air Conditioning

## Symptoms covered

- AC unit not turning on at all
- AC runs but blows warm or room-temperature air
- AC runs constantly but unit never reaches set temperature
- AC turns on and off rapidly (short cycling)
- AC blows cold briefly then stops

Does NOT cover: AC making loud banging/grinding noises while running (dispatch directly), AC leaking water inside the unit (see condensate line section, or dispatch), AC unit frozen solid with ice (specific condition, see diagnostic tree below).

## Intake questions for tenant

1. What's happening? Not turning on at all, blowing warm air, or running but not cooling?
2. What's the thermostat set to? What temperature is showing in the unit?
3. What's the outdoor temperature right now?
4. When did it last work correctly?
5. Is the outdoor unit (condenser) running? Can you safely look at it?
6. When was the filter last changed?

**Classification check**: AC failure classification depends on jurisdiction and temperature. Check `severity-classification.md` and `habitability-response-windows.md`. Some jurisdictions (Arizona, Texas, Nevada, and others) treat AC as a habitability requirement when outdoor temperatures exceed a statutory threshold. If the jurisdiction has an AC habitability statute and the temperature meets the threshold, classify as High and dispatch immediately without triage.

If no AC habitability statute applies, classify as Medium when outdoor temperature exceeds 95F or tenant reports indoor temperature above 85F.

## Diagnostic decision tree

```
START
│
├─ Does the jurisdiction treat AC as habitability at current temps?
│   └─ Yes → DISPATCH immediately. Do not triage.
│
├─ Thermostat check
│   ├─ Is it set to COOL (not heat, not off)?
│   ├─ Is temperature set below current room temperature?
│   ├─ Is the fan set to AUTO (not just ON)? If set to ON only, the fan
│   │   blows continuously regardless of cooling.
│   │   └─ Set to AUTO. Wait 5 minutes.
│   │       └─ If cool air starts → RESOLVED (it was just the fan setting)
│   ├─ Is the display on? If blank → check batteries or breaker.
│   └─ Try lowering the set temperature 5 degrees below current room temp.
│       Wait 5 minutes. Any change?
│
├─ Breaker check
│   ├─ AC systems often have TWO breakers: one for the air handler (inside)
│   │   and one for the condenser (outside). Check both.
│   ├─ If either is tripped → reset. Wait 5 minutes.
│   │   └─ If AC starts cooling → RESOLVED (monitor for repeat trip)
│   │   └─ If trips again immediately → DISPATCH (do not reset again)
│   └─ If breakers look fine → continue
│
├─ Filter check
│   ├─ Where is the filter? (Return vent on wall/ceiling, or in the air
│   │   handler unit itself.)
│   ├─ Pull it out. Is it visibly clogged? (Solid gray/brown, cannot see
│   │   light through it.)
│   │   └─ Yes → replace with a new filter if available. Or run without
│   │       the filter temporarily to test.
│   │       └─ If AC starts cooling effectively → filter was restricting
│   │           airflow. Replace filter. RESOLVED.
│   │       └─ If still not cooling → continue
│   ├─ A clogged filter is the #1 cause of AC not cooling and of frozen
│   │   evaporator coils. Always check this.
│
├─ Is the outdoor unit running?
│   ├─ Can the tenant safely look at the condenser unit outside?
│   ├─ Is the fan spinning? Is there a humming sound?
│   │   └─ Fan spinning and humming → outdoor unit is running. Problem is
│   │       likely inside (frozen coil, refrigerant, blower).
│   │       → Check for ice (below). If no ice → DISPATCH.
│   │   └─ Not running at all → check the outdoor disconnect (gray box
│   │       near the unit). Is it switched on / fuse intact?
│   │       └─ If disconnect was off → turn on. Wait 5 minutes.
│   │           └─ If unit starts → RESOLVED
│   │       └─ If disconnect is fine and unit still won't run → DISPATCH
│   ├─ Is there debris around/on top of the outdoor unit? (Leaves, grass
│   │   clippings, furniture blocking airflow.)
│   │   └─ Clear debris, ensure 2 feet of clearance on all sides.
│   │       Wait 15 minutes. Any improvement?
│   │       └─ If cooling improves → RESOLVED. Advise keeping area clear.
│   │       └─ If no change → DISPATCH
│
├─ Is the system FROZEN? (Ice on pipes, ice visible on coil, AC blows
│   then stops, water dripping when it shouldn't be.)
│   ├─ If tenant sees ice on the refrigerant lines or coil:
│   │   └─ Turn system to FAN ONLY (not off, not cool) for 2-4 hours
│   │       to defrost. Check the filter during this time (dirty filter
│   │       is the most common cause of freezing).
│   │   └─ After defrost: replace filter if dirty. Switch back to COOL.
│   │       └─ If it cools normally → RESOLVED (caused by airflow
│   │           restriction from dirty filter)
│   │       └─ If it freezes again → DISPATCH (likely low refrigerant
│   │           or blower motor issue)
│
├─ SHORT CYCLING (turns on and off every few minutes)
│   └─ This is almost never tenant-fixable. DISPATCH.
│       (Possible causes: low refrigerant, oversized system, failing
│       compressor, electrical issue. All need a tech.)
│
└─ If none of the above resolve → DISPATCH
```

## Tenant-fixable resolution steps

1. **Thermostat settings**: Set to COOL, fan to AUTO, temperature 5 degrees below current room temp. Wait 5 minutes.

2. **Breaker reset**: Check both the indoor air handler breaker and the outdoor condenser breaker. Reset any that are tripped.

3. **Filter replacement**: Pull the filter, check if clogged. Replace or remove temporarily to test. A clogged filter is the most common cause of AC problems.

4. **Outdoor unit clearance**: Clear any debris, furniture, or vegetation within 2 feet of the condenser. Make sure the fan on top is not obstructed.

5. **Outdoor disconnect**: Check the gray disconnect box near the outdoor unit. Make sure it's switched on or the fuse is in place.

6. **Defrost a frozen system**: Set thermostat to FAN ONLY for 2-4 hours. Replace the filter. Then try COOL again.

## When to dispatch

- Jurisdiction treats AC as habitability at current temperature (dispatch immediately)
- Breaker trips repeatedly
- Outdoor unit won't run and disconnect is fine
- System freezes repeatedly after defrost and filter change
- Short cycling
- System runs but never cools (likely refrigerant issue)
- Tenant reports hissing from refrigerant lines (leak)
- Tenant unable or unwilling to perform steps

## Vendor category to dispatch

HVAC technician. Same vendor category as heating issues. For emergencies (jurisdiction-triggered habitability), use the emergency HVAC vendor from config.

## Notes for coordinator agent

- AC classification is jurisdiction-dependent. Always check before deciding whether to triage or dispatch immediately. Do not assume AC is "just comfort." In hot-climate states, it can be a legal habitability requirement.
- Dirty filters cause the majority of AC issues tenants report. At Level 2+, always start here.
- Refrigerant issues (system runs but doesn't cool, ice buildup that recurs after filter change) are never tenant-fixable and always require a licensed tech. Don't waste the tenant's time troubleshooting further once filter and airflow are ruled out.
- AC repairs can be expensive. Always flag for NTE check when dispatching.
- If the unit is old (15+ years) and the repair is a compressor or major component, the vendor will likely recommend replacement. That's definitely an owner decision, not something to auto-approve.
- For window AC units that are owner-provided: troubleshooting is simpler (is it plugged in, is the filter dirty, is it set correctly). If a window unit fails, replacement is usually cheaper than repair.
