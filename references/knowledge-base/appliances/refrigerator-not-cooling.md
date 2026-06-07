---
id: KB-APPL-002
category: appliances
subcategory: refrigerator
title: Refrigerator Not Cooling (But Running)
severity: high
tenant_fixable: true
tenant_responsible: never
required_photos: false
required_videos: false
typical_resolution_minutes: 10
response_target_hours: 24
jurisdictions: all
last_reviewed: 2026-05-05
---

# Refrigerator Not Cooling (But Running)

## Symptoms covered

- Refrigerator is running (can hear compressor or fan) but interior is warm
- Food is spoiling faster than normal
- Freezer is cold but fridge compartment is warm
- Fridge was working but gradually stopped keeping temperature
- Ice buildup inside the fridge or freezer (frost-free unit that's frosting)

Does NOT cover: refrigerator completely dead/not running (see KB-APPL-001), refrigerator making loud unusual noises (dispatch directly), refrigerator leaking water on floor (usually a clogged condensate line or failed ice maker, dispatch directly).

## Intake questions for tenant

1. Is the fridge running? (Can you hear it humming or feel vibration when you touch it?)
2. Are both the fridge and freezer warm, or just the fridge section?
3. What temperature does food feel like? Cool but not cold, room temperature, or actually warm?
4. When did you first notice? Has it been getting worse gradually or did it happen suddenly?
5. Is there any ice buildup visible inside (on the back wall of the fridge or in the freezer)?
6. Has the fridge been overstuffed recently or had the door left open?

**Classification check**: A non-functioning refrigerator with food loss risk is a High severity (habitability) issue in most jurisdictions. If the fridge is completely failing (interior at room temperature) and there's perishable food at risk, classify per `severity-classification.md` and dispatch within 24 hours. If it's just cooling poorly but food is still cold-ish, classify as Medium.

## Diagnostic decision tree

```
START
│
├─ Is the fridge completely at ROOM TEMPERATURE inside?
│   └─ Yes → food safety issue. Advise tenant to move perishables to a
│       cooler with ice if they have one. DISPATCH urgently (within 24 hours).
│       Only continue triage if there's a high chance of quick resolution.
│
├─ Check THERMOSTAT / TEMPERATURE SETTINGS
│   ├─ Was the temperature dial bumped? (Common with overfull fridges.)
│   │   Check the dial inside (usually 1-7 or 1-9, with higher = colder).
│   │   └─ If set to 1 or lowest → turn to 4-5 (middle). Wait 4-6 hours.
│   │       └─ If temperature improves → RESOLVED
│   │       └─ If no change → continue
│   ├─ Digital display models: check if there's an error code showing.
│   │   → Note code for dispatch. Likely not tenant-fixable.
│
├─ Check CONDENSER COILS (Level 3+)
│   ├─ Coils are on the back of the fridge (older models) or underneath
│   │   behind a kick plate (newer models).
│   ├─ Are they visibly caked with dust/pet hair?
│   │   └─ Yes → vacuum or brush them off gently. This is the #1 cause
│   │       of reduced cooling on older units.
│   │       Wait 4-6 hours after cleaning.
│   │       └─ If cooling improves → RESOLVED. Advise cleaning every
│   │           6-12 months.
│   │       └─ If no improvement → continue
│   └─ Newer models with coils underneath: pull off the front kick plate
│       (usually snaps off). Vacuum visible dust.
│       [PHOTO if significant dust buildup before cleaning]
│
├─ Check for AIRFLOW OBSTRUCTION
│   ├─ Is the fridge overstuffed? (Especially blocking the vents between
│   │   freezer and fridge compartments.)
│   │   └─ Remove items blocking the vents (usually at the back top of
│   │       the fridge compartment or between the two sections).
│   │       Wait 4-6 hours.
│   │       └─ If improves → RESOLVED. Advise not blocking vents.
│   ├─ Is the fridge pushed tight against the wall?
│   │   └─ Pull it out 1-2 inches from the wall for airflow behind.
│   │       Wait 4-6 hours.
│   │       └─ If improves → RESOLVED
│
├─ Check DOOR GASKET (seal)
│   ├─ Close the door on a dollar bill. Pull the bill out.
│   │   └─ If it slides out easily → gasket isn't sealing. The fridge
│   │       is losing cold air.
│   │       └─ At Level 4+: clean the gasket with warm soapy water
│   │           (dirt/residue prevents seal). Apply a thin layer of
│   │           petroleum jelly to the gasket surface. Test again.
│   │           └─ If bill holds → RESOLVED (cleaned gasket restored seal)
│   │           └─ If still loose → gasket needs replacement. DISPATCH.
│   │   └─ If it holds firmly → gasket is fine. Continue.
│
├─ Is there ICE BUILDUP inside? (Frost on back wall, ice in freezer
│   that shouldn't be there on a frost-free unit.)
│   ├─ This indicates the defrost system has failed.
│   │   └─ Temporary fix: unplug the fridge for 24 hours with doors
│   │       open to fully defrost. Place towels on floor. Then plug
│   │       back in.
│   │       └─ If it cools normally after → defrost system issue. It
│   │           will freeze up again in days/weeks. DISPATCH for
│   │           defrost system repair.
│   │       └─ If still not cooling → DISPATCH
│   └─ Note: ask tenant to move perishables to a cooler during the
│       24-hour defrost. This is only appropriate if the tenant has
│       the time and willingness.
│
├─ Is the FREEZER cold but FRIDGE warm?
│   └─ Usually means the evaporator fan (which circulates cold air from
│       freezer to fridge) has failed, OR the vent between compartments
│       is blocked with ice.
│       ├─ Check for vent blockage (food or ice). Clear if visible.
│       └─ If vent is clear → DISPATCH (fan motor failure).
│
└─ If none of the above resolve → DISPATCH
```

## Tenant-fixable resolution steps

1. **Check temperature setting**: Find the dial or digital control inside the fridge. Set to middle (4-5 on most scales). Wait 4-6 hours to see improvement.

2. **Clean condenser coils** (Level 3+): Find coils on the back (pull fridge out slightly) or underneath (remove front kick plate). Vacuum off dust and pet hair. This is the most common fix for gradual cooling loss.

3. **Clear airflow obstructions**: Don't pack the fridge so tight that air can't circulate. Make sure the vents between freezer and fridge section aren't blocked by food. Pull fridge 1-2 inches from the wall.

4. **Clean door gasket** (Level 4+): Wipe down the rubber gasket around the door with warm soapy water. Apply a thin layer of petroleum jelly. Test seal with a dollar bill.

5. **Manual defrost** (Level 4+, only with tenant cooperation): Unplug fridge for 24 hours with doors open. Place towels on floor. Plug back in and monitor.

## When to dispatch

- Fridge completely at room temp with food at risk (urgent, within 24 hours)
- Coil cleaning and settings adjustment didn't help after 6 hours
- Defrost system failure (ice buildup, frost-free unit frosting)
- Gasket won't seal after cleaning
- Evaporator fan failure (freezer cold, fridge warm, vents clear)
- Error code on digital display
- Tenant unable or unwilling to try steps
- Fridge is old (15+ years) and showing signs of compressor wear

## Vendor category to dispatch

Appliance repair technician. Check vendor list for refrigerator-specific capability and brand coverage.

## Temporary mitigation while awaiting dispatch

- Move highly perishable items (meat, dairy, leftovers) to a cooler with ice
- If the freezer still works, consolidate critical items there temporarily
- Keep the fridge door closed as much as possible (every opening warms it further)
- If the fridge is at room temp and repair is next-day, suggest tenant use ice in a cooler for overnight

## Tenant responsibility notes

Never tenant-responsible. Refrigerator cooling failure is mechanical degradation of an owner-provided appliance. Even if dirty coils contributed (tenant didn't clean them), the repair is owner responsibility. Coil cleaning is maintenance that most tenants don't know about.

## Work order fields to capture at dispatch

- Symptom (not cooling at all, cooling poorly, freezer fine but fridge warm)
- Current approximate temperature inside (if tenant can tell)
- Make/model/age of the refrigerator (usually on a label inside the door or on the side)
- Any error code displayed
- What was tried (settings, coils, gasket, defrost)
- Whether food loss has occurred (some companies reimburse food loss)
- Tenant availability
- Whether the fridge is built-in or freestanding (affects access for repair)

## Suggested tenant communication

**Urgent (food at risk)**: "A fridge that's not cooling is something I take seriously. I'm getting an appliance tech out within 24 hours. In the meantime, if you have a cooler and some ice, move your meat and dairy into that. Keep the fridge door closed as much as you can. It helps it hold whatever cold is left."

**After coil cleaning resolves it**: "Good news, looks like the coils were just dirty and that was choking the cooling. It should start getting cold again over the next few hours. Quick tip: vacuuming those coils every 6 months or so prevents this from happening again."

**If replacement likely**: "Given the age of this fridge and what it's doing, the tech may recommend replacement over repair. I'll let you know what they find. If it comes to that, the property manager will make the call on replacement."

## Notes for coordinator agent

- Refrigerator failure is a High severity (habitability) issue. Don't let this sit in a Low queue. 24-hour response target maximum.
- Dirty condenser coils are the most common cause of gradual cooling loss. At Level 3+, always have the tenant check these before dispatching. Saves a service call.
- If the fridge is 15+ years old and the compressor is failing (running but not cooling, clicking), repair often costs more than replacement. Always flag for NTE and owner decision.
- Some companies provide or reimburse for food loss when a fridge fails. This is company-specific. Check config or escalate to PM if tenant asks about food replacement.
- For built-in or counter-depth units, replacement is more expensive and may require custom sizing. Note this for the PM.
- A fridge that cools poorly but is still somewhat cold (38-45F) is less urgent than one at room temp. But anything above 40F is a food safety concern per FDA guidelines.
