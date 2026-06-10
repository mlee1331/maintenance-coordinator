---
id: KB-ELEC-001
category: electrical
subcategory: breaker-panel
title: Breaker Tripped / Partial Power Loss
severity: low
tenant_fixable: true
tenant_responsible: never
required_photos: true
required_videos: false
typical_resolution_minutes: 10
response_target_hours: 72
jurisdictions: all
last_reviewed: 2026-05-05
---

# Breaker Tripped / Partial Power Loss

## Symptoms covered

- One room or area has no power
- A group of outlets stopped working
- A specific appliance trips the breaker when plugged in
- Breaker keeps tripping after being reset
- GFCI outlet tripped and won't reset

Does NOT cover: entire unit has no power (check with utility company first, then dispatch), sparking or burning smell from outlets or panel (Emergency severity, dispatch immediately), flickering lights throughout the unit (possible loose neutral, dispatch immediately), tenant needs something moved or added in the panel (always dispatch, never tenant work).

## Intake questions for tenant

1. What stopped working? One room, one set of outlets, one appliance, or everything?
2. Did something specific happen when it went out? (Plugged something in, turned something on, storm, nothing obvious.)
3. Do you have access to your breaker panel? Do you know where it is?
4. Are there any burning smells, scorch marks, or warmth around any outlets or the panel?

**Classification check**: If the tenant reports burning smell, scorch marks, warmth from outlets or the panel, sparking, or any smoke, this is Emergency severity. Do not triage. Dispatch immediately and advise tenant not to touch the panel.

If the entire unit is dark, ask the tenant to check whether neighbors also lost power (possible utility outage). If it's just their unit, dispatch an electrician.

## Diagnostic decision tree

```
START
│
├─ Is there a BURNING SMELL, scorch marks, or outlet warm to touch?
│   └─ Yes → STOP. Emergency. DISPATCH immediately. Tell tenant
│       not to use affected outlets and to stay away from the panel.
│
├─ Is the ENTIRE UNIT without power?
│   ├─ Check: do neighbors have power?
│   │   └─ No → likely utility outage. Tenant should contact utility.
│   │       NOT a maintenance dispatch (unless it persists after utility
│   │       confirms no outage on their end).
│   │   └─ Yes → check main breaker (large double breaker at top of panel)
│   │       └─ If tripped → reset it (flip fully off, then on)
│   │           └─ If power returns → RESOLVED (monitor for repeat)
│   │           └─ If trips again immediately → DISPATCH
│   │       └─ If main breaker looks fine → DISPATCH
│   └─ If tenant cannot access panel or isn't sure → DISPATCH
│
├─ Is it ONE ROOM or a GROUP OF OUTLETS?
│   ├─ Can the tenant access the breaker panel?
│   ├─ Look for a breaker in the middle position (not fully on, not fully
│   │   off). That's a tripped breaker.
│   │   └─ Found one → flip it fully OFF, wait 5 seconds, flip back ON.
│   │       └─ Power returns to affected area → RESOLVED
│   │       └─ Breaker trips again immediately → DISPATCH
│   │       └─ Breaker stays on but outlets still dead → check if the
│   │           outlets are on a GFCI circuit (see below)
│   └─ If no breaker appears tripped → check for a tripped GFCI outlet
│       (see GFCI section below)
│
├─ Is a SPECIFIC APPLIANCE tripping the breaker?
│   ├─ Unplug the appliance. Reset the breaker.
│   │   └─ Breaker holds without the appliance → the appliance is the
│   │       problem, not the electrical system.
│   │       - If it's an owner-provided appliance → DISPATCH (appliance
│   │         repair or replacement)
│   │       - If tenant-owned → inform tenant their appliance has a fault.
│   │         Not a maintenance issue.
│   │   └─ Breaker trips even without the appliance → DISPATCH
│   │       (circuit issue, not appliance issue)
│
├─ GFCI OUTLET check
│   ├─ Look for outlets in kitchens, bathrooms, garages, and exterior
│   │   walls that have TEST and RESET buttons on them.
│   ├─ Press the RESET button firmly.
│   │   └─ If it clicks and power returns to affected outlets → RESOLVED.
│   │       (Many regular outlets downstream are protected by one GFCI.)
│   │   └─ If it clicks but pops right back out → DISPATCH
│   │   └─ If it won't click at all → DISPATCH
│   └─ Note: the GFCI protecting a dead outlet might be in a completely
│       different room. Check all bathrooms, kitchen, garage, exterior,
│       and laundry areas.
│
└─ If none of the above resolve → DISPATCH
```

## Tenant-fixable resolution steps

1. **Reset a tripped breaker**: Open the panel. Find the breaker in the middle position. Flip it fully to OFF (you should feel it click), wait 5 seconds, then flip to ON. If it stays, you're good.

2. **Reset a GFCI outlet**: Find the outlet with TEST/RESET buttons (check bathrooms, kitchen, garage, exterior). Press RESET firmly. If it clicks and stays in, power should return to all outlets protected by that GFCI.

3. **Isolate a faulty appliance**: Unplug the appliance that seems to trigger the trip. Reset the breaker. If it holds, the appliance is the problem.

## When to dispatch

- Burning smell, scorch marks, or warmth from outlets or panel (Emergency)
- Breaker trips again immediately after reset (do not ask tenant to reset more than once)
- GFCI won't reset or keeps popping
- Entire unit without power and main breaker won't hold
- No visible tripped breaker and GFCI resets don't resolve
- Any situation involving the panel interior, wiring, or anything beyond flipping a breaker or pressing a GFCI button

## Vendor category to dispatch

Handyman for straightforward issues (GFCI replacement, outlet swap, breaker identification, isolating a faulty circuit). Licensed electrician for panel work, repeated breaker trips with no clear cause, any wiring repair, or anything that requires opening the dead front cover. Most breaker/GFCI calls are handyman-level work and don't need a licensed electrician.

## Temporary mitigation while awaiting dispatch

- If a breaker trips repeatedly: leave it OFF. Don't keep resetting. Use extension cords from a working circuit for essentials (phone charging, lamp) until the electrician arrives. Don't daisy-chain or overload the working circuit.
- If GFCI won't reset: the outlets downstream are dead. If this affects the kitchen, use a different outlet on another circuit for the fridge (extension cord temporarily).
- If the fridge is on the tripped circuit: move critical food to a cooler with ice if dispatch is next-day.

## Tenant responsibility notes

Never tenant-responsible for breaker or GFCI failures. If a tenant-owned appliance is causing the trip, the electrical system itself is fine and the issue is the tenant's appliance. Inform the tenant their device has a fault, but the building wiring is not a maintenance issue in that case.

## Work order fields to capture at dispatch

- What's affected (one room, group of outlets, one appliance, whole unit)
- What triggered it (plugging something in, storm, nothing obvious)
- Whether breaker was reset and result (holds, trips again)
- Whether GFCI outlets were checked and result
- Whether there are any safety indicators (smell, heat, scorch marks)
- Whether an appliance was isolated as the cause
- Photo of breaker panel if tenant can provide (helps electrician prep)
- Tenant availability

## Suggested tenant communication

**After self-fix**: "Great, sounds like it was just an overload. If it happens again with the same circuit, let me know because repeated trips mean something the electrician should look at."

**Dispatching**: "Since the breaker keeps tripping, I don't want you to keep resetting it. Leave it off and I'll get an electrician scheduled. If you need to use something on that circuit, run a single extension cord from a working outlet for now."

**GFCI won't reset**: "GFCI outlets protect a bunch of other outlets you might not expect, so that could be why several things went dead. Since it won't reset, I'll get an electrician out. If your fridge is on one of those dead outlets, you might want to run an extension cord from a working one to keep it cold."

## Notes for coordinator agent

- Never ask a tenant to open the panel cover (the inner door with the breaker labels is fine, the dead front cover with screws is not). Never ask them to touch wires, inspect connections, or do anything inside the panel beyond flipping breakers.
- A breaker that trips once and stays reset is usually fine (momentary overload). A breaker that trips repeatedly indicates a fault that needs professional diagnosis. Do not ask the tenant to keep resetting it.
- GFCI outlets protect other outlets downstream. A dead outlet in a bedroom could be protected by a GFCI in the bathroom on the other side of the wall. Always have the tenant check all GFCI outlets in the unit before dispatching.
- If the tenant reports a specific appliance trips the breaker, confirm whether it's an owner-provided or tenant-owned appliance. Tenant-owned appliance faults are not a maintenance issue.
- Flickering lights throughout the unit (not just one fixture) can indicate a loose neutral connection, which is a fire hazard. Do not triage. Dispatch immediately.
- For Level 1-2: just ask about the breaker and GFCI. For Level 3+: walk through the full tree including appliance isolation.
- Flag for NTE on anything beyond a standard service call. Panel upgrades are rare from a single call but can be significant.
