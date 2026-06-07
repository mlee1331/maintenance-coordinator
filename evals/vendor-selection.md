# Vendor Selection Eval Scenarios

## Scenario VS-1: Handyman vs. Plumber for Toilet Repair

**Setup**: Default config. Vendors available: handyman (Mike's Handyman) and plumber (City Plumbing).

**Tenant message**: "My toilet handle is loose and you have to jiggle it to flush."

**Expected behavior**:
1. Classify as standard.
2. Triage: likely a loose handle nut or detached chain. Walk through the diagnostic tree.
3. If dispatch needed: send the handyman, not the plumber. Toilet handle and internal parts (flapper, fill valve, chain, float) are handyman work.
4. Note in work order: likely handle tightening or chain reconnection.

**Red flags**:
- Dispatching a plumber for a toilet handle issue
- Not attempting triage first (this is a very fixable issue)

---

## Scenario VS-2: Handyman vs. Electrician for Outlet Swap

**Setup**: Default config. Troubleshooting aggressiveness: 3.

**Tenant message**: "One of my outlets doesn't work. I plugged a lamp into it and nothing."

**Expected behavior**:
1. Classify as standard (one outlet, not a whole circuit or unit).
2. Triage: is it a GFCI outlet? Check for a reset button on the outlet itself. Check other outlets nearby. Check breaker panel.
3. If triage resolves (GFCI reset or breaker flip), done.
4. If dispatch needed: handyman for outlet replacement or GFCI swap. This is straightforward work.
5. Only dispatch a licensed electrician if: multiple outlets are dead with no tripped breaker, there's a burning smell, or the outlet shows signs of damage (scorch marks, melting).

**Red flags**:
- Dispatching an electrician for a single dead outlet before triage
- Not checking for GFCI reset (the most common fix)

---

## Scenario VS-3: Owner-Required Vendor

**Setup**: Config has owner "Janet Chen" for property "450 Oak Ave" with preferred_vendors: ["ABC Plumbing"]. Handyman also available.

**Tenant message**: "Faucet in the kitchen at 450 Oak Ave is dripping badly."

**Expected behavior**:
1. Classify as standard.
2. Triage per aggressiveness level.
3. If dispatch needed: even though a handyman could handle a faucet drip, owner Janet Chen requires ABC Plumbing for this property. Dispatch ABC Plumbing.
4. Owner vendor preferences always override the default handyman-first hierarchy.

**Red flags**:
- Dispatching the handyman because it's cheaper (owner preference overrides)
- Not checking owner preferences before vendor selection

---

## Scenario VS-4: NTE Exceeded, Owner Unreachable, Habitability

**Setup**: NTE default: $300. Property in California. No hot water (habitability, 24h window). Water heater replacement estimated to cost well over NTE. Owner has not responded to approval request for 4 hours.

**Tenant message**: (Already triaged. Vendor on-site says water heater needs full replacement.)

**Expected behavior**:
1. This is a habitability issue with a 24-hour clock running.
2. Vendor recommends replacement. This always needs owner approval (capital expenditure) per owner-approval-rules.md.
3. Approval was requested. Owner hasn't responded in 4 hours.
4. Try alternate contact (if configured). If still no response and the habitability deadline is approaching, dispatch anyway and document that approval was attempted per the rules.
5. Escalate to PM. Note the habitability clock, the attempted approval, and the decision to proceed.
6. Don't let the tenant go without hot water because the owner didn't pick up the phone.

**Red flags**:
- Telling the tenant to wait indefinitely for owner approval
- Cancelling the dispatch because approval wasn't received
- Not documenting the approval attempt

---

## Scenario VS-5: Emergency, No Preferred Vendor Available

**Setup**: Property in New York. After-hours. Designated emergency plumber is not answering.

**Tenant message**: "Water is pouring from the ceiling in my bathroom."

**Expected behavior**:
1. Classify as urgent minimum (active leak causing damage). Could be habitability if major.
2. Immediate mitigation: place a bucket/container to catch water. If the leak is from the unit above, try to contact that tenant (if known). Look for a shutoff valve.
3. Dispatch emergency plumber. Preferred vendor not answering.
4. Try alternate vendors in the plumber category. Expand to any available emergency plumber.
5. If no plumber available, escalate to PM immediately. The clock is ticking.
6. Don't wait until morning. Active water leaks cause progressive damage.

**Red flags**:
- Scheduling for the next business day because the preferred vendor is unavailable
- Not trying alternate vendors
- Not escalating when no vendor can be reached

---

## Scenario VS-6: Pest Issue, Correct Specialty Vendor

**Setup**: Default config. Handyman and pest control company both available.

**Tenant message**: "I found bedbugs in my mattress. There are a lot of them."

**Expected behavior**:
1. Classify as urgent (active infestation, not a single sighting).
2. Do not dispatch a handyman. Bedbugs require licensed pest control with chemical or heat treatment.
3. Dispatch pest control company.
4. Advise tenant: don't move mattress or bedding to another room (spreads the infestation). Don't throw out furniture yet (pest control may be able to treat it). Wash bedding in hot water if possible.
5. Check jurisdiction for bedbug-specific response windows (some cities have 7-14 day requirements).

**Red flags**:
- Dispatching a handyman for bedbugs
- Classifying as standard (active infestation is urgent)
- Telling the tenant to buy over-the-counter bug spray (ineffective for bedbugs and delays proper treatment)
