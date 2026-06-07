---
id: KB-GEN-005
category: general
subcategory: mold-moisture
title: Mold or Moisture Complaint
severity: medium
tenant_fixable: false
tenant_responsible: sometimes
required_photos: true
required_videos: false
typical_resolution_minutes: 5
response_target_hours: 48
jurisdictions: all
last_reviewed: 2026-05-05
---

# Mold or Moisture Complaint

> **Triage rule — read first. Every mold or suspected-mold report escalates to a human before any dispatch.** At triage you only have the tenant's words. You cannot tell small surface mold from the visible tip of a hidden leak, and it may not be mold at all. So the coordinator agent's job on a mold report is: document it, classify the category as **Mold/Air Quality**, set **escalate = true**, and hand it to a human per `escalation-criteria.md`. The agent does **not** auto-dispatch mold — not even "small grout mold."
>
> Everything below this banner — the size thresholds, the diagnostic tree, the vendor guidance — is the tool the **human** uses *after* escalation to decide the actual dispatch. It is not a triage-time dispatch path for the agent.

## Symptoms covered

- Visible mold growth on walls, ceiling, or around windows
- Musty smell in the unit
- Persistent condensation on windows
- Peeling paint or bubbling wallpaper from moisture
- Water stains with dark spots
- Mold on bathroom ceiling or grout

Does NOT cover: mold in HVAC system (dispatch HVAC specialist), mold caused by active water leak (fix the leak first per KB-PLUMB-005 or KB-PLUMB-008, then address mold), mold on tenant's personal belongings only (not a building maintenance issue unless the source is building-related).

## Intake questions for tenant

1. Where are you seeing mold or moisture? Which room(s), which surfaces? [PHOTO]
2. How much area is affected? (Smaller than a dinner plate, larger, or extensive?)
3. What color is it? (Black, green, white, orange?)
4. Is there a musty smell?
5. Have you noticed any water leaks, condensation, or dampness in that area?
6. Does the bathroom have a working exhaust fan? Do you use it during showers?
7. How long has it been there? Is it growing or stable?

**Classification check**: Mold is almost never Critical, but it IS health-sensitive and potentially a High severity (habitability) issue depending on jurisdiction, extent, and tenant health conditions.
- Large area of mold (more than 10 sq ft) → escalate to PM. Professional remediation may be needed. Do not dispatch a handyman for large-scale mold.
- Tenant reports health symptoms (respiratory issues, allergic reactions) → urgent. Treat with priority.
- Small bathroom mold on grout/caulking → likely routine, but the agent still escalates first; the human may then route it as standard maintenance.
- Mold related to an active leak → fix the leak first (see appropriate plumbing entry).

**IMPORTANT**: Do NOT make legal claims about mold. Do not tell the tenant mold is or isn't dangerous. Do not diagnose health effects. Do not use the phrase "toxic mold." Route any health or legal questions to the PM. The coordinator's job is to document, report, and dispatch.

## Diagnostic decision tree

```
START
│
├─ Is there an ACTIVE WATER LEAK causing the moisture?
│   └─ Yes → address the leak first (see appropriate KB entry). Mold
│       treatment is meaningless until the moisture source is eliminated.
│       Create a follow-up work order for mold treatment after the leak
│       is fixed and the area dries.
│
├─ How LARGE is the affected area?
│   ├─ Smaller than 10 square feet (roughly a 3x3 area) → standard
│   │   maintenance dispatch. Handyman or mold remediation tech can handle.
│   ├─ Larger than 10 square feet → ESCALATE TO PM. Professional mold
│   │   assessment and remediation likely required. Do not dispatch a
│   │   handyman for this. PM may need to involve a mold remediation
│   │   company, which often requires testing and documentation.
│   └─ If uncertain of size → ask for [PHOTO] with something for scale.
│
├─ WHERE is the mold?
│   ├─ BATHROOM ceiling or grout
│   │   └─ Most common mold location. Usually caused by inadequate
│   │       ventilation (no exhaust fan, or fan not used).
│   │   └─ At Level 3+: does the bathroom have an exhaust fan?
│   │       └─ No → that's a building issue. Dispatch for fan installation
│   │           and mold cleaning.
│   │       └─ Yes but tenant doesn't use it → advise tenant to run the
│   │           fan during and 15 minutes after every shower.
│   │           Still dispatch for mold cleaning of existing growth.
│   │       └─ Yes and tenant uses it → fan may not be working properly
│   │           (not venting outside, weak suction). Check: hold a tissue
│   │           up to the fan when running. Does it stick?
│   │           └─ No (doesn't stick) → fan is weak or disconnected.
│   │               DISPATCH for fan repair AND mold cleaning.
│   │           └─ Yes (tissue sticks) → fan works. Mold may be from
│   │               a leak or building envelope issue. DISPATCH for
│   │               inspection.
│   │
│   ├─ AROUND WINDOWS (sill, frame, wall near window)
│   │   └─ Usually condensation-related. Window insulation may be poor
│   │       (single-pane, failed seal, no storm window in cold climate).
│   │   └─ Not tenant-fixable at the building level. DISPATCH for mold
│   │       cleaning and PM should assess window condition for replacement
│   │       or insulation improvement.
│   │   └─ Advise tenant: improve ventilation, use a dehumidifier if they
│   │       have one, don't block registers/vents near windows.
│   │
│   ├─ WALLS or CEILING (not bathroom)
│   │   └─ Could indicate: roof leak, pipe leak in wall cavity, exterior
│   │       envelope breach (missing siding, flashing issue), or
│   │       humidity/ventilation problem.
│   │   └─ [PHOTO] essential. Look for associated water staining.
│   │   └─ DISPATCH. Needs inspection to identify moisture source.
│   │
│   └─ BASEMENT or CRAWLSPACE area (if applicable)
│       └─ Common in older homes. May need dehumidification, drainage
│           improvement, or vapor barrier. DISPATCH for assessment.
│           Flag for PM (scope can be expensive).
│
├─ Is the tenant reporting HEALTH SYMPTOMS?
│   └─ Yes → do NOT dismiss or minimize. Do NOT diagnose.
│       Classify as urgent. Dispatch with priority. Note health complaint
│       in work order. Escalate to PM for awareness (liability concern).
│       If symptoms are severe → suggest tenant consult their doctor.
│       Do NOT recommend they leave the unit (that's a legal/PM decision).
│
└─ All mold complaints → the agent ESCALATES to a human first (see the
    banner at the top). The human then uses this tree to decide dispatch.
    Even small mold should be professionally cleaned to prevent regrowth.
```

## Tenant-fixable resolution steps

Mold remediation is not tenant-fixable and should not be presented as such. However, prevention measures the tenant can take:

1. **Run the bathroom exhaust fan** during and 15 minutes after every shower.
2. **Improve ventilation**: open windows periodically (weather permitting), don't block HVAC registers, use a dehumidifier in humid climates.
3. **Reduce condensation**: don't dry clothes indoors on racks near walls, keep closet doors open for air circulation, wipe down window condensation.
4. **Small surface mold on hard surfaces** (Level 4+ only, and ONLY on non-porous surfaces like tile, glass, or sealed counters): tenant can clean with a solution of 1 part bleach to 10 parts water. Wear gloves. Ventilate the area. This does NOT replace professional treatment for porous surfaces (drywall, wood, carpet).

Do NOT ask tenants to clean mold on drywall, ceiling, carpet, or any porous surface. That requires professional handling.

## When to dispatch (human decides, after escalation)

Mold always escalates first (see the banner). Once a human has reviewed, dispatch is warranted for:

- All mold complaints beyond minor condensation that the tenant can manage
- Any visible mold growth on building surfaces
- Musty smell even without visible mold (could be hidden in walls)
- Tenant health complaints
- Large areas (10+ sq ft) → professional remediation
- Mold associated with a leak (fix leak first, then mold)

## Vendor category to dispatch (human's choice, post-escalation)

The agent does not pick this — the human does, after reviewing. Small areas (under 10 sq ft) on hard surfaces: handyman or maintenance tech for cleaning and caulk replacement. Medium areas or porous surfaces: mold remediation specialist. Large areas (10+ sq ft) or recurring mold: professional mold remediation company (likely requires testing and containment). Exhaust fan repair or installation: handyman preferred (cheaper), electrician only if new wiring is needed.

## Temporary mitigation while awaiting dispatch

- Improve ventilation in the affected area (open windows, run fans)
- Do NOT have tenant cover the mold with paint (traps moisture, worsens problem)
- If mold is in a closet: remove clothes and belongings, leave door open for airflow
- If tenant has a dehumidifier: run it in the affected area
- If health symptoms: suggest tenant keep the affected room's door closed to limit exposure to the rest of the unit, and see their doctor

## Tenant responsibility notes

This is jurisdiction-dependent and politically sensitive.

- **Bathroom mold from inadequate ventilation by tenant** (fan available, not used, no window opened): some leases hold the tenant responsible for mold caused by their failure to ventilate. However, many jurisdictions place the burden on the landlord to provide adequate ventilation regardless.
- **Mold from building issues** (poor insulation, leaks, no exhaust fan, building envelope failure): always owner responsibility.
- **Mold from tenant behavior** (hanging wet clothes inside, blocking vents, never opening windows in humid climate): grey area. Some leases address this.

**DO NOT argue responsibility with the tenant on mold.** It's legally complex, jurisdiction-specific, and inflammatory. Dispatch, remediate, and let the PM sort responsibility after the fact. Health and habitability come first.

## Work order fields to capture at dispatch

- Location (room, surface, wall/ceiling/floor)
- Approximate area affected (square footage estimate or comparison to common objects)
- Color of mold
- Photo of the affected area with scale reference
- Whether there's an associated leak or moisture source
- Whether the area has a working exhaust fan
- Whether tenant is reporting health symptoms
- How long it's been present
- Whether it's growing or stable
- Tenant availability

## Suggested tenant communication

**Acknowledging the complaint**: "Thanks for reporting this. I take mold seriously and I want to get it handled properly. I'm going to have someone come take a look and clean it up. In the meantime, try to keep that area ventilated. If the bathroom has an exhaust fan, run it every time you shower."

**If tenant asks about health risks**: "I'm not qualified to assess health risks from mold, but if you're experiencing symptoms you're concerned about, I'd encourage you to talk to your doctor. What I can do is get the mold addressed as quickly as possible, which I'm doing now."

**If large/escalating to PM**: "This looks like it covers a larger area than what a standard cleaning can handle. I'm flagging it for the property manager to evaluate. They may want to bring in a specialist to assess it properly. I'll keep you updated on next steps."

## Notes for coordinator agent

- NEVER use the phrase "toxic mold" or "black mold" or make any health claims. The agent is not qualified to assess mold toxicity. Report what's visible, dispatch appropriate remediation, and escalate health concerns to the PM.
- Mold is one of the most litigated topics in property management. Document everything carefully. Photos, tenant communication, response time, remediation steps.
- Small bathroom mold on grout/caulking is the most common mold call and the least concerning. Standard fix: remove old caulk, clean with mold-killer, recaulk, ensure ventilation.
- If mold keeps coming back after cleaning: the moisture source hasn't been addressed. Don't just keep dispatching for cleaning. Identify and fix the root cause (leak, ventilation, insulation, building envelope).
- EPA guidance says areas under 10 sq ft can be handled by maintenance staff. Over 10 sq ft should involve a professional remediation company with containment procedures.
- Some jurisdictions require mold disclosure to tenants or have specific mold response requirements. Check local ordinances. This is a PM/legal question, but the coordinator should flag timing.
- Costs escalate significantly from small area cleaning to exhaust fan installation to professional remediation. Large-scale remediation can be very expensive. Always flag for NTE and PM awareness on anything beyond small surface cleaning.
