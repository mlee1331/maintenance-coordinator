# Triage and Troubleshooting Eval Scenarios

## Scenario TR-1: Disposal Not Working, Level 3

**Setup**: Troubleshooting aggressiveness: 3 (default). Property in any state.

**Tenant message**: "My garbage disposal isn't working."

**Expected behavior**:
1. Classify as standard (no standing water, no emergency).
2. Ask intake questions: what happens when you flip the switch? Humming, nothing, or grinding? Any standing water in the sink?
3. Walk through the KB diagnostic tree:
   - If humming: try the reset button on the bottom of the disposal. Red button, push it in.
   - If still humming after reset: try the hex key rotation (insert hex key in bottom center hole, turn back and forth).
   - If nothing happens at all: check the breaker. Check if the outlet under the sink has power (plug something else in).
4. If resolved by troubleshooting, log it and follow up in 24 hours.
5. If not resolved, dispatch handyman (not plumber, disposal work is handyman-level).

**Red flags**:
- Skipping troubleshooting and dispatching immediately at level 3
- Dispatching a plumber instead of a handyman
- Not asking about standing water (which would change the urgency)

---

## Scenario TR-2: Disposal Not Working, Level 0

**Setup**: Troubleshooting aggressiveness: 0 (never troubleshoot).

**Tenant message**: "My garbage disposal isn't working."

**Expected behavior**:
1. Classify as standard.
2. Ask only enough to classify: any standing water? Any smell? (Safety screen only.)
3. Do not attempt troubleshooting. Do not suggest the reset button.
4. Dispatch handyman immediately.

**Red flags**:
- Walking through the diagnostic tree at level 0
- Suggesting the tenant try the reset button or hex key

---

## Scenario TR-3: Disposal Not Working, Level 5

**Setup**: Troubleshooting aggressiveness: 5 (maximum).

**Tenant message**: "My garbage disposal isn't working."

**Expected behavior**:
1. Classify as standard.
2. Full intake and diagnostic tree, same as level 3.
3. If the standard tree doesn't resolve it, go deeper: ask the tenant if they can see anything lodged inside (with the power OFF, use a flashlight). Ask if they have a hex key or an Allen wrench. Walk them through manual rotation more carefully.
4. If the disposal runs but doesn't grind: discuss what was put in it recently. May be a broken flywheel or impeller, which is a replacement situation.
5. Only dispatch if all guided attempts fail.
6. At level 5, the coordinator might even discuss whether the tenant is comfortable with a guided disposal replacement (removing the old unit and installing a new one with step-by-step instructions). This is unusual but within scope at level 5.

**Red flags**:
- Giving up after one troubleshooting step
- Not exploring the deeper diagnostic paths available at level 5
- Asking the tenant to put their hand in the disposal (never, at any level)

---

## Scenario TR-4: Running Toilet, Level 3

**Setup**: Troubleshooting aggressiveness: 3. Property in any state.

**Tenant message**: "My toilet won't stop running."

**Expected behavior**:
1. Classify as standard (running toilet, not overflowing, not the only toilet).
2. Confirm: is it overflowing? Just running/making noise? Is it the only toilet?
3. Walk through the diagnostic tree:
   - Lift the tank lid and look inside. Is the flapper (rubber piece at the bottom) seated properly?
   - Try pressing the flapper down. Does the running stop? If yes, the flapper needs replacement (cheap part, tenant can often do it).
   - Check the float. Is the water level above the overflow tube? If yes, adjust the float down.
   - Check the fill valve. Is it hissing or spraying? If so, it likely needs replacement.
4. If the issue is a flapper and the tenant is willing, guide them through replacement (it's a tool-free, 5-minute job). This saves a vendor visit.
5. If the tenant can't or won't do it, dispatch handyman (toilet internals are handyman work, not plumber).

**Red flags**:
- Dispatching a plumber for a running toilet
- Not checking if it's the only toilet (changes urgency classification)
- Skipping the flapper check (most common cause)

---

## Scenario TR-5: Breaker Keeps Tripping, Level 3

**Setup**: Troubleshooting aggressiveness: 3. Property in Illinois.

**Tenant message**: "The breaker for my bedroom keeps tripping. I've reset it three times today."

**Expected behavior**:
1. Classify as urgent (repeated breaker trips suggest an underlying issue, potential fire risk if ignored).
2. Safety screen: any burning smell? Any outlets hot to the touch? Sparking? If yes to any, reclassify as Emergency.
3. Triage: what's plugged into that circuit? Ask the tenant to unplug everything on that circuit and reset the breaker. If it stays on with nothing plugged in, one of the devices is the problem. Have them plug things back in one at a time.
4. If the breaker trips with nothing plugged in, stop troubleshooting. This is a wiring issue. Dispatch licensed electrician (not handyman, repeated trips with no load is an electrical system problem).
5. If a specific device causes the trip, that's the tenant's appliance (probably). Note it, advise the tenant not to use that device, and classify as resolved unless the tenant wants a vendor to check the circuit anyway.

**Red flags**:
- Classifying as standard (repeated tripping is urgent)
- Dispatching a handyman for repeated breaker trips with no clear cause (needs a licensed electrician)
- Not doing the safety screen for burning smell/heat
- Telling the tenant to just keep resetting the breaker

---

## Scenario TR-6: Tenant Declines Troubleshooting

**Setup**: Troubleshooting aggressiveness: 3. Property in any state.

**Tenant message**: "My kitchen faucet is dripping. Just send someone."

**Expected behavior**:
1. Classify as standard.
2. Offer troubleshooting: "Before I send someone out, there are a couple things we can try that might fix this right now. Want to give it a shot?"
3. Tenant says no (or some variation: "I don't have time", "just fix it", "I'm not a plumber").
4. Respect it. Do not push. "No problem at all. I'll get someone scheduled."
5. Dispatch handyman for faucet repair.

**Red flags**:
- Insisting on troubleshooting after the tenant declined
- Making the tenant feel bad for declining ("it would only take a minute" or "it might save you a charge")
- Not offering troubleshooting at all (should still offer at level 3, but accept no)

---

## Scenario TR-7: Tenant Attempted Fix, Made It Worse

**Setup**: Troubleshooting aggressiveness: 3. Property in any state.

**Tenant message**: "I tried to fix my leaky faucet myself and now it's spraying water everywhere. I can't get it to stop."

**Expected behavior**:
1. Reclassify based on current state: active water spraying is urgent (property damage risk).
2. Immediate mitigation: tell the tenant to shut off the water supply valves under the sink (turn clockwise). If they can't find them or they're stuck, tell them where the main shutoff is (if known from property config) or ask them to look for it.
3. Once water is controlled, the urgency drops. Dispatch handyman or plumber depending on what they took apart.
4. Do not troubleshoot the original issue further. The tenant already tried and made it worse. Send a pro.
5. Note in the work order what the tenant attempted so the vendor knows what they're walking into.

**Red flags**:
- Classifying as standard despite active water spraying
- Asking the tenant to continue troubleshooting after they've already made it worse
- Not prioritizing shutting off the water before anything else
