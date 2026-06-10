# Severity Classification

Six severity levels for every incoming work order. The severity drives response time, dispatch rules, triage expectations, and whether owner approval is needed. Classify every work order on intake. No exceptions.

## Levels at a Glance

| Severity | Response Time | Triage? | Owner Approval? | Dispatch |
|---|---|---|---|---|
| Emergency | Immediate | No | No | Immediate, any available vendor |
| High | Same day | No | Only if over NTE | Within hours |
| Medium | 24-48 hours | Yes | Yes, per normal rules | Within 1-2 days |
| Low | 3-7 business days | Yes | Yes, per normal rules | Scheduled |
| Cosmetic | 2-4 weeks | If applicable | Yes, per normal rules | Batched when possible |

## Level Definitions

### Emergency

The top, immediate-response level. An issue is **Emergency** if either is true: **(a)** life, health, or safety is at immediate risk — someone could get hurt right now (evacuate / call 911); or **(b)** something is actively going wrong where every hour of delay makes the damage worse or the repair more expensive. (Life-safety cases were formerly a separate "Critical" level; they are now Emergency. See `emergency-classification.md` for the full life-safety criteria and immediate safety instructions.)

The test: **Could someone get hurt, or — if I wait until tomorrow — will the damage or cost be significantly worse?** If yes, it's an Emergency. If the acute event has already happened and what remains is damaged but **stable** — not imminently dangerous and not actively worsening — classify it **High**, not Emergency.

No triage. No owner approval. No waiting on estimates. Dispatch immediately.

Examples — life, health, or safety:

- Fire or active smoke
- Gas leak (natural gas or propane)
- Carbon monoxide alarm sounding
- Flooding with electrical exposure risk
- Sewage in the living space
- No heat at or below 32F with no warming forecast
- Structural failure (ceiling sagging, wall buckling, floor giving way)
- **Active or ongoing** electrical arcing, sparking, burning smell, smoke, scorch marks, or an outlet/panel warm to the touch — a fire risk right now. (A one-time spark when plugging something in, with no ongoing arcing or burning and where the tenant can simply stop using that outlet, is **High**, not Emergency — see below.)
- Tenant feels unsafe in the unit due to a maintenance condition

Examples — active property damage:

- Broken water supply line, even if the water has been shut off. The pipe is still broken. The tenant or property may be without water service. The ground, walls, or subfloor may already be damaged.
- Active water intrusion from a roof leak, failed flashing, or broken gutter during rain or with rain in the forecast.
- Water heater actively leaking or ruptured (not condensation, actual tank failure).
- Sump pump failure during wet conditions or with rain in the forecast.
- Burst or frozen pipe that's been shut off but not repaired. The break still exists.
- Sewer line blockage affecting the entire unit (all drains backing up, not just one slow drain).
- HVAC failure with extreme weather in the forecast (heat index above 100F or windchill below 10F within 24 hours), even if current conditions aren't at the habitability threshold yet.
- Significant appliance failure creating active damage (refrigerator leaking onto hardwood, dishwasher flooding the kitchen).
- Water pouring or gushing from a ceiling or overhead — e.g., a burst supply line in the floor above — especially with the ceiling sagging, bulging, or collapsing. Active interior flooding plus structural damage; every hour makes it worse.
- Exterior door or gate that cannot be secured after storm damage or attempted break-in.
- Tree or large branch **actively or imminently threatening** — a limb hanging over an entrance or the structure, a tree leaning on the unit, or a fall that is blocking access or causing ongoing damage right now. (A tree that has already dropped a limb and is damaged but **stable** — not imminently dangerous — is **High**, not Emergency.)
- Garage door stuck open overnight or with severe weather coming.
- Electrical panel tripped and won't reset, affecting major systems (HVAC, water heater, refrigerator) but not the entire unit.

Actions:

1. If life-safety is involved, advise the tenant immediately (evacuate if needed, call 911 if appropriate).
2. Do not attempt triage. This needs a professional. Dispatch immediately — no owner approval regardless of NTE.
3. Notify the owner/PM after dispatch (use the fastest channel for life-safety). This is a courtesy notification, not an approval request.
4. Request photos from the tenant if not already provided and it is safe to do so.
5. Confirm with the tenant that help is on the way; log any safety advice given.

### High

Habitability is compromised or at risk. The unit doesn't meet legal standards for a livable dwelling, or it will cross that line soon. Not immediately life-threatening, but legally time-sensitive. Response windows are set by state law (see `habitability-response-windows.md`).

Examples:

- No heat during heating season (generally October through April, or outdoor temps below 55F)
- No hot water
- No running water
- No working toilet (single-toilet unit)
- Refrigerator completely non-functional with food loss risk
- Major water leak actively causing damage or will cause damage within hours
- Broken exterior door or window that can't lock or close (security compromised)
- Electrical failure affecting the entire unit
- An outlet that sparked on plug-in but is **not** actively arcing or burning — a serious electrical fault. Advise the tenant to stop using that outlet; dispatch urgently, but it is High (avoidable, not an active fire), not Emergency.
- Inoperable hardwired smoke detectors the tenant can't fix themselves
- AC failure in jurisdictions that treat cooling as habitability (check the statute)

Actions:

1. Check the response window for the property's jurisdiction.
2. Dispatch within that window. If the window is same-day or 24 hours, dispatch immediately.
3. Owner approval needed only if cost exceeds NTE and the response window allows time. If owner is unreachable and the deadline is approaching, dispatch anyway and document the attempt.
4. Confirm with the tenant that help is coming and give a realistic timeline.

### Medium

Significant inconvenience or risk of property damage if not addressed soon. Could escalate to High or Emergency if ignored. Triage is attempted per configured aggressiveness level.

Examples:

- AC not working during high heat (in jurisdictions where AC is NOT a habitability requirement)
- Slow but active water leak (under sink, a slow seep from a ceiling, around toilet base). Not a drip, not pouring. Water going somewhere it shouldn't. (Water *pouring* or *gushing* from a ceiling, or a ceiling sagging/collapsing, is **Emergency** — see above.)
- Single broken window pane with weather exposure but security not compromised
- Active pest infestation the tenant just discovered (roaches, mice, bedbugs, not "I saw one ant")
- One toilet out of service in a multi-toilet unit
- Washing machine or dryer completely non-functional (owner-provided)
- Dishwasher leaking when run
- Water heater making unusual noises or showing signs of corrosion (not yet failed, but showing signs)
- Electrical issues on one circuit affecting daily use

Actions:

1. Attempt triage per configured aggressiveness level.
2. If triage doesn't resolve, dispatch within 24-48 hours.
3. Follow normal NTE and owner approval rules.
4. Confirm scheduling with the tenant.

### Low

Normal maintenance. The unit is livable. The tenant is not in distress. Something needs fixing but nobody's in a hurry. Full triage attempted.

Examples:

- Dripping faucet (slow, not wasting significant water)
- Running toilet (flapper issue, not overflowing)
- Cabinet door off hinge
- Squeaky door or floor
- Light fixture not working (other lighting available)
- Garbage disposal jammed (no standing water, no smell)
- One burner out on a four-burner stove
- Minor drywall damage (small hole, crack, nail pop)
- Caulking deterioration around tub or shower
- Sliding door sticking
- Screen door or window screen torn
- Closet door off track
- Slow drain that's still draining
- Minor appliance issues (ice maker, oven light, microwave turntable)
- Exterior lighting out (not a security concern)

Actions:

1. Full triage per configured aggressiveness level.
2. If triage doesn't resolve, schedule a vendor within 3-7 business days.
3. Follow normal NTE and owner approval rules.

### Cosmetic

No functional impact. Purely appearance. Schedule at convenience, batch with other work at the same property when possible.

Examples:

- Paint touch-ups (scuffs, marks, fading)
- Weatherstripping replacement (visible wear, no air leak complaint)
- Grout discoloration
- Exterior cosmetic issues (fence stain fading, minor trim paint peeling)
- Cabinet hardware loose but functional
- Minor landscaping issues
- Replacing a doorstop
- Door that sticks slightly
- Recaulking for appearance (not water intrusion)
- Outlet or switch plate cover cracked but functional

Actions:

1. Triage if applicable (some cosmetic items have no triage path).
2. Schedule at convenience, typically within 2-4 weeks.
3. Batch with other work at the same property to reduce vendor trip charges.
4. Follow normal NTE and owner approval rules.

## Classification Rules

**When in doubt, classify higher.** The cost of over-classifying is a faster vendor response. The cost of under-classifying can be tenant harm, property damage, or legal liability.

**Time of day matters.** A toilet clog at a unit with two bathrooms is Low. The same clog at a unit with one bathroom on a Friday evening is High (tenant has no working toilet for the weekend).

**Weather and jurisdiction matter together.** A broken window in July in Phoenix is Medium at minimum (maybe High if cooling is habitability in AZ). A broken window in January in Minneapolis is High (cold exposure, pipe freeze risk). A broken window in San Diego in April is Low. AC classification depends on whether the property's jurisdiction has an AC habitability statute. Do not assume. Check `habitability-response-windows.md`.

**Tenant vulnerability matters.** If the tenant is elderly, disabled, has young children, or reports a medical condition affected by the issue, classify one level higher than the issue alone would warrant.

**Multiple issues compound.** Two Low issues at once may create Medium-level urgency. No hot water plus a broken heater in November is not two Low issues, it's High.

**Repeat issues escalate.** Same issue reported for the same unit within 30 days: classify one level higher. If a vendor already came and the problem is back, that's a callback, Medium minimum.

## Relationship to Other Files

- How to handle the triage and dispatch for each classification: `emergency-classification.md`
- Legal response windows by state for habitability issues: `habitability-response-windows.md`
- When to get owner approval and when to skip it: `owner-approval-rules.md`
- When to escalate to a human: `escalation-criteria.md`
- Who pays for the repair: `tenant-responsibility-matrix.md`
