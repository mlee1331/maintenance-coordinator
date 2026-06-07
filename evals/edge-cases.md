# Edge Case Eval Scenarios

## Scenario EDGE-1: Compound Issues Escalate Classification

**Setup**: Property in Illinois. November. Outdoor temp 40F.

**Tenant message**: "My furnace stopped working and now I'm noticing water dripping from the ceiling in the hallway."

**Expected behavior**:
1. Two issues reported. Evaluate each, then evaluate the combination.
2. No heat at 40F: High (habitability) (above 32F, so not Critical override, but still no heat in heating season).
3. Water dripping from ceiling: urgent (active leak, property damage risk).
4. Combined: don't treat these as two separate standard issues. The combination is at least habitability-level. The ceiling leak could even be related (frozen/burst pipe if it gets colder overnight).
5. Dispatch HVAC for the furnace (priority, habitability clock) and separately assess the leak. If they could be related (HVAC condensate line, frozen pipe), note the connection for the vendor.
6. Two separate work orders or one combined, depending on what the harness supports. But coordinate so the vendors aren't stepping on each other.

**Red flags**:
- Treating each issue independently without considering the combination
- Classifying the overall situation as standard
- Only addressing one issue and forgetting the other

---

## Scenario EDGE-2: After-Hours Timing Changes Classification

**Setup**: Property in any state. Single-bathroom unit. Friday at 9pm.

**Tenant message**: "My toilet won't flush."

**Expected behavior**:
1. Single toilet in the unit, non-functional: habitability (no working toilet).
2. It's Friday 9pm. If not addressed now, the tenant has no working toilet all weekend. The 24-hour habitability window means this needs attention by Saturday 9pm, but practically speaking, getting a vendor on a Saturday is harder and more expensive.
3. Dispatch now. Use the after-hours/emergency vendor if the regular handyman isn't available.
4. Quick triage first if the tenant is willing (check the handle, chain, flapper, water supply valve). These are fast checks that might resolve it in minutes.
5. If dispatch is needed, accept after-hours rates. The alternative is a tenant with no toilet for 48+ hours.

**Red flags**:
- Scheduling for Monday ("it's after hours, we'll get someone out next week")
- Not recognizing that Friday evening + single toilet = needs immediate attention
- Not attempting quick triage (the fix might be a 30-second chain reconnection)

---

## Scenario EDGE-3: Vulnerable Tenant Elevates Classification

**Setup**: Property in Arizona. July. Outdoor temp 105F. AC is a habitability requirement in AZ.

**Tenant message**: "My air conditioning stopped working. I'm 82 years old and I have heart problems."

**Expected behavior**:
1. AC out in Arizona in July: already habitability (AZ has AC habitability statutes during extreme heat).
2. Tenant is elderly with a medical condition affected by the heat: classify one level higher per severity-classification.md. This is now Critical.
3. Dispatch emergency HVAC immediately. No NTE check. Notify PM.
4. Advise tenant on immediate cooling: drink water, stay in the coolest room, use fans if available, wet towels on neck/wrists. If they feel dizzy, nauseated, or confused, call 911.
5. If the HVAC can't be fixed quickly, the PM may need to arrange temporary accommodation (hotel) for a vulnerable tenant in 105F heat. Flag this in the escalation.

**Red flags**:
- Classifying as Low or even just High (vulnerable tenant + extreme heat = Critical)
- Not mentioning heat safety precautions
- Not flagging the medical condition and age for the PM
- Extended troubleshooting while an 82-year-old with heart problems is in 105F heat

---

## Scenario EDGE-4: Vague Initial Message

**Setup**: Default config. Troubleshooting aggressiveness: 3.

**Tenant message**: "Something is wrong with the kitchen."

**Expected behavior**:
1. Not enough information to classify. Do not guess.
2. Ask a clarifying question: "Can you tell me a little more about what's going on in the kitchen? What are you seeing or hearing?"
3. Wait for the response before classifying. Don't assume it's an appliance issue, plumbing issue, or electrical issue.
4. Don't batch multiple questions. One question, get the answer, then follow up.

**Red flags**:
- Guessing the category ("sounds like an appliance issue")
- Dispatching without understanding the problem
- Asking 5 questions at once ("Is it the faucet? The disposal? The stove? The dishwasher? An outlet?")

---

## Scenario EDGE-5: Jurisdiction-Dependent AC Classification

**Setup A**: Property in Arizona. July. Outdoor temp 108F.
**Setup B**: Property in Michigan. July. Outdoor temp 92F.

**Tenant message (same for both)**: "My AC isn't working."

**Expected behavior for Setup A (Arizona)**:
1. Arizona has AC habitability statutes. At 108F, this meets the threshold.
2. Classify as habitability emergency. Dispatch HVAC within the jurisdiction's response window.
3. Do not schedule for next week.

**Expected behavior for Setup B (Michigan)**:
1. Michigan does not treat AC as a habitability requirement.
2. Classify as urgent (significant inconvenience at 92F, but not legally habitability).
3. Attempt triage per aggressiveness level (thermostat check, breaker check, filter check).
4. Dispatch HVAC within 24-48 hours if triage fails.
5. Note: if the tenant reports a medical condition or vulnerability, elevate classification.

**Red flags**:
- Treating both the same (jurisdiction matters)
- Not looking up the jurisdiction's AC stance before classifying
- Classifying Michigan AC as habitability (it's not in that state)
- Classifying Arizona AC as standard (it is habitability in AZ at that temp)

---

## Scenario EDGE-6: Repeat Callback, Vendor Quality Issue

**Setup**: Default config. Handyman was dispatched to fix a leaky faucet at unit 4B two weeks ago. Work order was closed after tenant confirmed resolution.

**Tenant message**: "The faucet you fixed two weeks ago is leaking again. Same faucet, same leak."

**Expected behavior**:
1. Classify based on the current issue (probably standard, dripping faucet).
2. Recognize this as a callback/recurrence. Same issue, same unit, within 30 days. Per emergency-classification.md, classify one level higher than the issue alone would warrant (standard becomes urgent).
3. Do not ask the tenant to troubleshoot the same steps again. They already went through this.
4. Dispatch, but consider whether to send the same vendor or a different one. If the original handyman's repair didn't hold, the PM should know.
5. Escalate to PM: "Callback at [unit]. Same faucet leak that [vendor] repaired on [date]. Repair didn't hold. Recommend dispatching a different vendor or a plumber to assess whether the fixture needs full replacement."
6. Log vendor performance: first-visit fix rate miss.

**Red flags**:
- Treating this as a brand new issue (it's a callback)
- Not elevating the classification (repeat issue within 30 days)
- Sending the same vendor without flagging the callback
- Making the tenant go through the full troubleshooting tree again

---

## Scenario EDGE-7: Tenant Mentions Disability/Accommodation

**Setup**: Default config. Property in any state.

**Tenant message**: "The grab bar in my shower came loose. I'm in a wheelchair and I need it to transfer safely. Without it I can't shower."

**Expected behavior**:
1. Classify based on impact: the tenant cannot safely use their shower without the grab bar. This is at minimum urgent, possibly habitability (tenant can't use a basic facility).
2. ADA/accessibility-related maintenance is an always-escalate trigger per escalation-criteria.md. Escalate to PM regardless of how simple the repair seems.
3. Dispatch for the grab bar repair (handyman can handle grab bar reattachment in most cases, but it may need blocking behind the wall for proper support, which is more involved).
4. Escalate to PM: "Accessibility issue at [unit]. Tenant uses wheelchair, shower grab bar came loose, tenant cannot safely shower without it. Dispatched [vendor] for repair. Flagging because this is an ADA/accessibility maintenance request."
5. Prioritize this over a typical "loose hardware" classification.

**Red flags**:
- Classifying as Low/Cosmetic ("loose grab bar" sounds minor out of context)
- Not escalating (disability/accommodation is always-escalate)
- Not recognizing the impact on the tenant's daily functioning
- Dispatching without considering whether the grab bar needs proper structural mounting

---

## Scenario EDGE-8: Insurance-Worthy Damage

**Setup**: Default config. Property in any state.

**Tenant message**: "A pipe burst in the wall upstairs and water has been pouring into my living room for the last hour. The ceiling is soaked, the carpet is ruined, and there's standing water on the floor."

**Expected behavior**:
1. Classify as Critical or High depending on whether there's electrical exposure risk (standing water near outlets or appliances). At minimum, Medium bordering on High.
2. Immediate mitigation: is the water still flowing? Can the tenant find and shut off the main water supply? Move furniture and electronics away from the water.
3. Dispatch emergency plumber immediately.
4. Escalate to PM: this will involve an insurance claim. Flood damage, ceiling damage, carpet damage. PM needs to notify the owner and potentially the insurance company.
5. Document everything: photos (request from tenant), timestamps, extent of damage. This documentation matters for the claim.
6. The tenant may need temporary accommodation if the unit is uninhabitable. Flag for PM.

**Red flags**:
- Not flagging for insurance (this is clearly beyond routine maintenance)
- Not requesting documentation/photos (critical for claims)
- Treating as a standard plumbing call
- Not considering temporary accommodation for the tenant
