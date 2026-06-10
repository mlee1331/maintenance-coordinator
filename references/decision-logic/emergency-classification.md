# Emergency Classification

> **Note:** This file is retained as a detailed reference for life-safety (Emergency) classification criteria. The primary severity classification system is now in `severity-classification.md`.

How to classify the emergency level of every incoming work order. Run this classification on every intake, no exceptions. The result determines whether triage is attempted and how fast to dispatch.

## The Five Levels

### 1. Life-Safety Emergency

Immediate risk of death, serious injury, or catastrophic property damage. Dispatch immediately. Do not attempt triage. Advise the tenant on safety steps. Notify the property manager. Tell the tenant to call 911 if appropriate.

**Classify as life-safety when any of these are true:**

- Tenant reports fire or active smoke in the unit
- Tenant reports smell of gas (natural gas, propane) anywhere in the unit or building
- Carbon monoxide alarm is sounding
- Flooding with potential electrical exposure (standing water near outlets, panels, or appliances that are still energized)
- Sewage backing up into living space (not a slow drain, actual sewage in the unit)
- Complete loss of heat when outdoor temperature is at or below 32F (0C) and forecast shows no warming within 12 hours
- Structural damage that makes the unit feel unsafe to occupy (ceiling sagging, wall buckling, floor giving way)
- Lockout classified as life-safety by the property management company's configured lockout policy (see `assets/config.template.yaml`). There is no universal standard here. Some companies treat all after-hours lockouts as life-safety. Others treat all lockouts as urgent. Configure this per your operation and tenant population.
- Electrical sparking, burning smell from outlets or panels, or visible arcing
- Any situation where the tenant says they feel unsafe or are afraid to stay in the unit due to a maintenance condition

**Immediate actions for life-safety:**

1. Tell the tenant to leave the unit if there is fire, gas smell, CO alarm, or structural risk. Do not tell them to investigate.
2. Tell the tenant to call 911 if there is fire, gas smell, CO alarm, or any risk of immediate injury.
3. For gas smell specifically: tell the tenant not to flip any switches, not to use their phone inside the unit, and to leave the door open as they exit.
4. Dispatch the emergency vendor immediately. Do not wait for owner approval regardless of NTE.
5. Notify the property manager by the fastest available channel.
6. Log the classification, the safety advice given, and the dispatch in the work order.

### 2. Habitability Emergency

The unit fails to meet legal habitability standards. Not immediately life-threatening, but legally time-sensitive. Dispatch within the jurisdiction's required response window (see `habitability-response-windows.md`). Do not attempt triage. Owner approval is required only if the jurisdiction's response window allows time for it and the cost exceeds NTE.

**Classify as habitability emergency when any of these are true:**

- No heat during heating season (varies by jurisdiction, but generally October through April, or when outdoor temps are below 55F)
- No hot water
- No running water at all
- No working toilet (only if the unit has a single toilet)
- Refrigerator completely non-functional with food loss risk (not "making a weird noise," actually not cooling)
- Major water leak that is actively causing damage or will cause damage if not addressed within hours
- Broken exterior door or window that compromises unit security (can't lock, can't close, glass fully broken out)
- Broken exterior door or window during cold or severe weather
- Electrical failure affecting the entire unit (not one circuit, the whole unit is dark)
- Inoperable smoke detectors when the tenant cannot replace batteries themselves (hardwired units, units out of reach without a ladder the tenant doesn't have)

**How habitability differs from life-safety:**

Life-safety means someone could get hurt right now. Habitability means the unit doesn't meet the legal standard for a livable dwelling. A unit with no hot water is not going to kill anyone tonight, but the landlord has a legal obligation to restore it within a specific timeframe. That timeframe varies by state. Always check `habitability-response-windows.md` for the property's jurisdiction.

**Actions for habitability emergency:**

1. Look up the response window for the property's jurisdiction in `habitability-response-windows.md`.
2. Dispatch a vendor within that window. If the window is very short (same-day or 24 hours), dispatch immediately.
3. If cost is expected to exceed NTE and the response window allows it, request owner approval. If the owner is unreachable and the deadline is approaching, dispatch anyway and document the attempt to reach the owner.
4. Notify the property manager.
5. Confirm with the tenant that help is on the way and give a realistic timeline.

### 3. Urgent

Significant inconvenience, risk of property damage if not addressed soon, or conditions that could escalate to habitability or life-safety if ignored. Target dispatch within 24-48 hours. Triage is attempted per the configured aggressiveness level.

**Classify as urgent when any of these are true:**

- AC not working during high heat. Classification depends on jurisdiction. Some states (notably Arizona and Texas) treat AC as a habitability requirement during extreme heat, which would make this a habitability emergency, not just urgent. Other states have no AC habitability statute at all. Always check `habitability-response-windows.md` for the property's jurisdiction before classifying. If the jurisdiction treats AC as habitability and the temperature meets the statutory threshold, classify as habitability emergency instead of urgent.
- Slow but active water leak (under sink, from ceiling, around toilet base). Not a drip from a faucet. Water is going somewhere it shouldn't.
- Single broken window pane with weather exposure (rain, cold, insects) but unit security is not compromised
- Active pest infestation the tenant just discovered (roaches, mice, bedbugs). Not "I saw one ant." Visible evidence of ongoing infestation.
- One toilet out of service in a multi-toilet unit
- Washing machine or dryer completely non-functional (tenant cannot do laundry at all, and these are owner-provided appliances)
- Dishwasher leaking actively when run
- Garage door stuck open (security concern, weather exposure)
- Water heater making unusual noises or showing signs of corrosion/leaking (not yet failed, but showing signs it's about to)
- Electrical issues on one circuit (one room dark, one set of outlets dead) that affect daily use

**Actions for urgent:**

1. Attempt triage per configured aggressiveness level.
2. If triage does not resolve, dispatch within 24-48 hours.
3. Follow normal NTE and owner approval rules.
4. Confirm scheduling with the tenant.

### 4. Standard

Normal maintenance. The unit is livable, the tenant is not in distress, but something needs fixing. Schedule within 3-7 business days. Full triage attempted.

**Classify as standard when:**

- The issue causes inconvenience but not hardship
- There is no risk of property damage from waiting a few days
- The issue does not affect safety, security, or habitability

**Common examples:**

- Dripping faucet (slow, not wasting significant water)
- Running toilet (flapper issue, not overflowing)
- Cabinet door off hinge
- Squeaky door or floor
- Light fixture not working (tenant has other lighting in the room)
- Garbage disposal jammed (no standing water, no smell)
- Stove has one burner out of four not working
- Minor drywall damage (small hole, crack, nail pop)
- Caulking deterioration around tub or shower
- Sliding door sticking or hard to open
- Screen door or window screen torn
- Closet door off track
- Slow drain that is still draining (not backed up, not standing water)
- Minor appliance issues (ice maker not working, oven light out, microwave turntable broken)
- Exterior lighting out (not a security concern, other lighting present)

**Actions for standard:**

1. Full triage per configured aggressiveness level.
2. If triage does not resolve, schedule a vendor within 3-7 business days.
3. Follow normal NTE and owner approval rules.

### 5. Non-Urgent

Cosmetic, low-impact, or batchable work. No functional impact. Schedule at convenience, often batched with other work at the same property. Full triage attempted where applicable.

**Classify as non-urgent when:**

- The issue is purely cosmetic
- The issue has no functional impact on daily living
- The issue has existed for a while and is not getting worse
- The work can wait for the next scheduled maintenance visit

**Common examples:**

- Paint touch-ups (scuffs, marks, fading)
- Weatherstripping replacement (no air leak complaint, just visible wear)
- Grout discoloration
- Exterior cosmetic issues (fence stain fading, minor trim paint peeling)
- Cabinet hardware loose but functional
- Minor landscaping issues (unless lease specifies owner responsibility)
- Replacing a doorstop
- Adjusting a door that sticks slightly
- Recaulking for appearance (not for water intrusion)
- Outlet or switch plate cover cracked but functional

**Actions for non-urgent:**

1. Triage if applicable (some cosmetic items have no triage path).
2. Log the request and schedule at convenience, typically within 2-4 weeks.
3. Batch with other work at the same property when possible to reduce vendor trip charges.
4. Follow normal NTE and owner approval rules.

## Classification Rules

**When in doubt, classify higher.** A false urgent is better than a missed habitability emergency. A false habitability emergency is better than a missed life-safety. The cost of over-classifying is a faster vendor response. The cost of under-classifying can be tenant harm or legal liability.

**Time of day matters.** A lockout classification depends on the company's configured lockout policy, but time of day is a factor most companies weigh. A toilet clog at a unit with two bathrooms is standard. A toilet clog at a unit with one bathroom on a Friday evening is habitability (tenant has no working toilet for the weekend if not addressed).

**Weather and jurisdiction matter together.** A broken window in July in Phoenix is urgent at minimum, and may be habitability if the jurisdiction treats cooling as habitability. A broken window in January in Minneapolis is habitability (cold exposure, potential pipe freeze). A broken window in San Diego in April is standard. AC failure classification specifically depends on whether the property's jurisdiction has an AC habitability statute. Do not assume. Look it up in `habitability-response-windows.md`.

**Tenant vulnerability matters.** If the tenant is elderly, disabled, has young children, or reports a medical condition affected by the issue, classify one level higher than the issue alone would warrant. An elderly tenant with no AC at 90F is habitability, not just urgent.

**Multiple issues compound.** If a tenant reports two or more standard issues at once, consider whether the combination creates urgency. No hot water plus a broken heater in November is not two standard issues; it's a habitability emergency.

**Repeat issues escalate.** If the same issue has been reported for the same unit within the last 30 days, classify one level higher. A slow drain reported twice in a month is urgent, not standard. A vendor already came and the problem is back, that's a callback, and it should be treated as urgent minimum.

## What This File Does Not Cover

- Who pays for the repair (see `tenant-responsibility-matrix.md`)
- How quickly the jurisdiction requires a response for habitability (see `habitability-response-windows.md`)
- When to escalate to a human (see `escalation-criteria.md`)
- How deep to troubleshoot before dispatching (see the aggressiveness scale in `SKILL.md`)
