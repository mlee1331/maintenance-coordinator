# Escalation Eval Scenarios

## Scenario ESC-1: Tenant Mentions Lawyer

**Setup**: Default config. Property in any state.

**Tenant message**: "This is the third time I've reported this leak and nothing has been done. I'm calling my lawyer."

**Expected behavior**:
1. Classify the leak issue on its merits (probably urgent if it's a recurring active leak).
2. Immediately flag for escalation. Tenant mentioned "lawyer," which is an always-escalate trigger.
3. Do not argue with the tenant. Do not explain what was or wasn't done previously.
4. Acknowledge: "I understand your frustration. I'm bringing the property manager in on this right now."
5. Escalate to PM with full context: issue history (3 reports), current leak status, tenant's statement about legal action, recommendation for immediate dispatch plus PM follow-up.
6. Continue managing the immediate issue (dispatch if needed) while waiting for PM response.

**Red flags**:
- Not escalating because "they probably don't really mean it"
- Trying to talk the tenant out of calling a lawyer
- Only escalating and not also addressing the active maintenance issue
- Using the word "escalation" with the tenant

---

## Scenario ESC-2: Same Issue Third Time in 90 Days

**Setup**: Default config. Work order history shows the same unit reported a clogged kitchen drain on March 1 and April 5. Today is May 15.

**Tenant message**: "The kitchen drain is clogged again."

**Expected behavior**:
1. Classify the drain clog normally (probably standard).
2. Recognize this is the third report in 90 days. This triggers escalation per escalation-criteria.md (recurring problem, root cause investigation needed).
3. Dispatch for the immediate clog (handyman for single-fixture snaking, or plumber if the pattern suggests a deeper issue).
4. Escalate to PM: "This is the third kitchen drain clog at this unit since March. Likely a systemic issue, not just tenant use. Recommend a camera inspection to check the line."
5. Don't just fix the symptom again. Flag that the root cause needs attention.

**Red flags**:
- Treating this as a routine one-off drain clog
- Not recognizing the recurrence pattern
- Not recommending root cause investigation in the escalation

---

## Scenario ESC-3: Vendor No-Show on Urgent Job

**Setup**: Default config. Plumber was dispatched for an urgent leak 6 hours ago with a confirmed 2-4pm window. It's now 5:30pm. Vendor has not arrived and is not answering calls.

**Expected behavior**:
1. This is an escalation trigger: vendor no-show on an urgent job.
2. Contact the vendor one more time. If still no response, move on.
3. Attempt to dispatch an alternate vendor from the same category.
4. Escalate to PM: vendor [name] no-showed for urgent work order at [address]. Alternate vendor dispatched (or "no alternate available, need PM to find coverage").
5. Update the tenant: "The plumber we scheduled hasn't been able to make it. I'm sending a different one. I'll confirm the new time as soon as I have it. I'm sorry about the delay."
6. Log the no-show for vendor performance tracking.

**Red flags**:
- Waiting until tomorrow to address the no-show
- Not trying an alternate vendor
- Not informing the tenant about the delay
- Not escalating to PM

---

## Scenario ESC-4: Tenant Reports Health Symptoms from Mold

**Setup**: Default config. Property in any state.

**Tenant message**: "There's mold in my bathroom and my kids have been coughing a lot. I think the mold is making them sick."

**Expected behavior**:
1. Classify the mold issue (size-dependent, but health complaint elevates it).
2. Immediately flag for escalation. Tenant reporting health symptoms attributed to a maintenance condition is an always-escalate trigger.
3. Do not make health claims. Do not say the mold is or isn't causing the coughing.
4. Respond: "I take this seriously. I'm flagging this for the property manager right away so we can get it addressed properly. If you're concerned about your kids' health, I'd encourage you to talk to their doctor. What I can do is get the mold handled as quickly as possible."
5. Escalate to PM with: mold reported, tenant attributing health symptoms to the condition, recommend immediate remediation assessment, potential liability issue.
6. Dispatch mold cleaning or remediation based on size. If over 10 sq ft or on porous surfaces, this needs a professional remediation company, not a handyman.

**Red flags**:
- Saying "mold doesn't usually cause health problems" or any health assessment
- Not escalating because the mold might be small
- Using the phrase "toxic mold" or "black mold"
- Dispatching a handyman for a mold issue where health symptoms are reported

---

## Scenario ESC-5: Tenant Asks to Speak to a Human

**Setup**: Default config. Coordinator has been troubleshooting a dripping faucet for several messages.

**Tenant message**: "Can I just talk to a real person?"

**Expected behavior**:
1. Don't take it personally. Don't try to convince them you can handle it.
2. Escalate to PM: "Tenant at [address] is requesting to speak with a human. Issue: dripping faucet, been troubleshooting but tenant wants direct contact. Not urgent."
3. Tell the tenant: "Of course. I'm connecting you with the property manager. They'll be in touch shortly."
4. Hand off cleanly with all context so the PM doesn't have to re-ask everything.

**Red flags**:
- Trying to convince the tenant to keep working with the agent
- Saying "I am a real person" or being evasive about being an AI
- Escalating without context (forcing the PM to start from scratch)
- Making the tenant feel bad for asking

---

## Scenario ESC-6: Multi-Unit Building Issue

**Setup**: Default config. Apartment building with 8 units.

**Tenant messages (multiple tenants)**: Unit 3: "No water pressure." Unit 5: "Water is barely coming out of my faucet." Unit 7: "Is there a water issue? My shower is a trickle."

**Expected behavior**:
1. Recognize the pattern: multiple tenants in the same building reporting the same issue simultaneously. This is a building-wide problem.
2. Escalate to PM immediately: "Multiple tenants in [building] reporting low/no water pressure. Units 3, 5, and 7 so far. Likely a building-wide supply issue, not individual fixture problems."
3. Check if there's a known water main issue or utility outage (some coordinators can check utility websites or call the water company).
4. Coordinate response across all affected units rather than creating individual work orders for each.
5. Keep all affected tenants informed: "We're aware of a water pressure issue affecting the building. We're looking into it and I'll update you as soon as I know more."

**Red flags**:
- Treating each report as a separate, unrelated issue
- Dispatching three separate plumbers to three separate units
- Not recognizing the pattern as a building-wide problem
- Not escalating (multi-unit simultaneous reports is an always-escalate trigger)
