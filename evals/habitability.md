# Habitability Eval Scenarios

## Scenario HAB-1: No Heat in Winter

**Setup**: Property in Massachusetts. January. Outdoor temp is 25F. Troubleshooting aggressiveness: 3.

**Tenant message**: "Our heat stopped working last night. It's really cold in here."

**Expected behavior**:
1. Classify as Critical (outdoor temp below 32F, override per severity-classification.md).
2. Do not attempt triage. Dispatch emergency HVAC immediately.
3. Advise tenant on staying warm (space heaters if available, layer up, close off unused rooms).
4. Look up Massachusetts response window (24 hours), but since this is Critical due to temp, dispatch is immediate regardless.
5. Notify PM.
6. No NTE check needed for Critical.

**Red flags**:
- Classifying as High instead of Critical (the 25F temp triggers the Critical override)
- Asking the tenant to check the thermostat or filter before dispatching
- Waiting for owner approval

---

## Scenario HAB-2: No Heat, Mild Weather

**Setup**: Property in Georgia. November. Outdoor temp is 48F.

**Tenant message**: "The furnace isn't turning on."

**Expected behavior**:
1. Classify as High (habitability) (no heat during heating season, but temp is above 32F so not Critical).
2. Look up Georgia response window. No specific statute with hard hours, use conservative default (48 hours).
3. At aggressiveness 3, attempt quick triage: check thermostat settings, check breaker, check if filter is clogged.
4. If triage doesn't resolve, dispatch HVAC tech within the response window.
5. Follow normal NTE/approval rules (habitability with 48h window allows time for approval if needed).

**Red flags**:
- Classifying as Critical (48F is cold but not freezing)
- Skipping triage entirely (the response window allows time for it)
- Dispatching a handyman for HVAC system diagnosis

---

## Scenario HAB-3: No Hot Water

**Setup**: Property in California. Troubleshooting aggressiveness: 3.

**Tenant message**: "We have no hot water. Turned on the shower this morning and it's ice cold. Same at every faucet."

**Expected behavior**:
1. Classify as habitability (no hot water).
2. Look up California response window (24 hours).
3. 24-hour window is tight. Attempt quick triage only if it won't eat into dispatch time: check if water heater pilot is out (gas) or breaker tripped (electric). One or two questions max.
4. If quick triage doesn't resolve, dispatch within the 24-hour window. HVAC tech or plumber depending on water heater type.
5. If it's a water heater replacement situation, flag for owner approval but note the habitability clock. Don't let the approval process blow the deadline.

**Red flags**:
- Classifying as standard or urgent
- Extended troubleshooting that eats into the 24-hour window
- Not noting the habitability deadline in the work order

---

## Scenario HAB-4: Only Toilet Not Working

**Setup**: Property in New Jersey. Single-bathroom unit. Saturday evening.

**Tenant message**: "My toilet won't flush at all. I've tried everything."

**Expected behavior**:
1. Classify as habitability (no working toilet in a single-toilet unit).
2. Look up New Jersey response window (24 hours for no working toilet).
3. It's Saturday evening. This is effectively urgent/emergency dispatch since waiting until Monday blows the 24-hour window.
4. Attempt very quick triage: is the handle connected? Is the chain attached? Is the water supply valve on? These take 30 seconds each.
5. If triage doesn't resolve, dispatch plumber or handyman (internal toilet repairs are handyman-level). Use emergency/after-hours vendor if needed.
6. Note: if the unit had two bathrooms, this would drop to standard priority.

**Red flags**:
- Classifying as standard because "toilet issues" sounds routine
- Not recognizing that Saturday evening plus 24-hour window means this needs immediate attention
- Telling the tenant to wait until Monday

---

## Scenario HAB-5: Broken Exterior Door Lock

**Setup**: Property in Washington DC. Evening.

**Tenant message**: "My front door lock is broken. The deadbolt won't engage and the knob lock isn't catching either. I can't secure my apartment."

**Expected behavior**:
1. Classify as habitability at minimum (broken exterior door lock). Given that it's evening and the tenant can't secure their unit overnight, treat as same-day emergency per habitability-response-windows.md.
2. Do not attempt triage. This needs a locksmith or handyman with lock experience.
3. Dispatch locksmith from emergency/after-hours vendor list.
4. Advise tenant on interim security (chair against door, stay with someone, whatever is practical). Don't leave them overnight with an unsecurable door.
5. Notify PM.

**Red flags**:
- Classifying as standard or scheduling for next week
- Asking the tenant to try WD-40 or jiggle the lock
- Leaving the tenant overnight with no way to lock their door

---

## Scenario HAB-6: Refrigerator Died

**Setup**: Property in Texas. Summer. Troubleshooting aggressiveness: 3.

**Tenant message**: "Our refrigerator stopped working completely. No lights, no sounds, nothing. All our food is going to go bad."

**Expected behavior**:
1. Classify as habitability (refrigerator completely non-functional with food loss risk).
2. Quick triage: is it plugged in? Did the outlet trip (GFCI or breaker)? These take 60 seconds.
3. If triage doesn't resolve, dispatch appliance repair tech. Handyman can check power supply issues, but if the fridge itself is dead, it needs an appliance tech.
4. Advise the tenant: keep the door closed as much as possible (food stays cold longer), move critical items to a cooler with ice if available.
5. Standard NTE/approval rules, but note that if replacement is needed, that's an owner approval situation and the habitability clock is running.

**Red flags**:
- Classifying as standard ("appliance issue" sounds routine, but complete fridge failure with food loss is habitability)
- Extended troubleshooting when food is actively spoiling
- Dispatching a handyman for internal refrigerator failures (power supply check is fine, but the repair itself needs an appliance tech)
