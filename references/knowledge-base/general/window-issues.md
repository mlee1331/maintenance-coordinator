---
id: KB-GEN-003
category: general
subcategory: windows-doors
title: Window Won't Open, Close, Lock, or Is Broken
severity: medium
tenant_fixable: false
tenant_responsible: never
required_photos: true
required_videos: false
typical_resolution_minutes: 5
response_target_hours: 24
jurisdictions: all
last_reviewed: 2026-05-05
---

# Window Won't Open, Close, Lock, or Is Broken

## Symptoms covered

- Window won't open (stuck, painted shut, mechanism broken)
- Window won't close or stay closed
- Window lock broken or won't engage
- Window glass cracked or broken
- Window screen torn or missing
- Window drafty (seal deteriorated)

Does NOT cover: window condensation between double-pane glass (seal failure, cosmetic, Cosmetic severity dispatch), blinds or window coverings broken (separate issue, typically tenant responsibility unless owner-provided).

## Intake questions for tenant

1. What's the problem? Won't open, won't close, won't lock, broken glass, or damaged screen?
2. Which window? (Room, floor, which side of the unit.) [PHOTO]
3. Is this an emergency? (Can't close in rain/cold, can't lock for security, broken glass with sharp edges or exposure.)
4. For broken glass: is anyone injured? Is the opening exposed to weather or accessible from outside?
5. For lock issues: is this the only way to secure that opening? Is it ground floor or accessible from outside?

**Classification check**:
- Broken window that compromises security (ground floor, accessible from outside, can't lock) → Medium to High depending on time of day and weather. Check `severity-classification.md`.
- Window that can't close during cold weather → High (heat loss, possible pipe freeze exposure)
- Window that can't close during severe weather (rain, storm) → Medium (water damage risk)
- Window won't open → Low (egress concern for fire code, but not immediate emergency)
- Broken glass with sharp edges → Medium (injury risk)
- Screen torn → Cosmetic

## Diagnostic decision tree

```
START
│
├─ Is there BROKEN GLASS?
│   ├─ Is anyone injured? → if yes, address injury first. Escalate if
│   │   medical attention needed.
│   ├─ Is the opening exposed to weather or accessible from outside?
│   │   └─ Yes → URGENT. Security and weather exposure.
│   │       [PHOTO] of the break.
│   │       Temporary mitigation: cardboard and tape, plastic sheeting,
│   │       or plywood over the opening from inside.
│   │       DISPATCH window repair/glass company.
│   │   └─ No (interior window, upper floor, small crack without
│   │       opening) → standard dispatch.
│   ├─ Is it a small crack or fully shattered?
│   │   └─ Small crack, no exposure → standard. Schedule glass repair.
│   │   └─ Shattered with opening → urgent. Secure opening temporarily.
│   └─ DISPATCH glass/window company.
│
├─ Window WON'T LOCK
│   ├─ Is it ground floor or otherwise accessible from outside?
│   │   └─ Yes → SECURITY CONCERN. Classify as urgent.
│   │       DISPATCH window repair or handyman.
│   │   └─ No (upper floor, not accessible) → standard priority.
│   ├─ At Level 3+: is the lock mechanism physically broken, or does the
│   │   window just not close far enough for the lock to engage?
│   │   └─ Window doesn't close fully → see "won't close" section.
│   │   └─ Lock itself is broken → DISPATCH.
│   └─ Temporary mitigation: a wooden dowel or stick in the track prevents
│       a sliding window from opening. For hung windows, a screw partially
│       driven into the frame above the sash can stop it from opening.
│
├─ Window WON'T CLOSE
│   ├─ What type of window? (Sliding, double-hung, casement/crank.)
│   ├─ Is something physically blocking it? (Debris in track, broken
│   │   hardware, paint or swelling.)
│   │   └─ Debris in track → At Level 3+: ask tenant to clean the track
│   │       with a vacuum and try again.
│   │       └─ If it closes → RESOLVED
│   │   └─ Paint or wood swelling → not tenant-fixable. DISPATCH.
│   │   └─ Hardware broken (crank, balance, tilt mechanism) → DISPATCH.
│   ├─ Is weather exposure a concern right now?
│   │   └─ Yes → classify with urgency. DISPATCH.
│   │       Temporary: tape plastic sheeting over the opening from inside.
│   └─ DISPATCH handyman or window repair.
│
├─ Window WON'T OPEN
│   ├─ Type of window?
│   ├─ At Level 3+: is it painted shut? (Common in older units.)
│   │   └─ Run a utility knife or putty knife along the seam where paint
│   │       connects the sash to the frame. Try opening.
│   │       └─ If it opens → RESOLVED
│   │       └─ If still stuck → DISPATCH
│   ├─ Is the hardware broken? (Crank won't turn, balance broken so sash
│   │   won't stay up, lock jammed in locked position.)
│   │   └─ DISPATCH handyman or window repair.
│   ├─ Is it swollen shut? (Wood frame, humid conditions.)
│   │   └─ Not tenant-fixable. DISPATCH.
│   └─ Note: windows that cannot open may be a fire code egress violation
│       if they're a bedroom window or required escape route. Flag this
│       for PM awareness. Not an emergency but a compliance concern.
│
└─ SCREEN torn or missing
    └─ Cosmetic. Low or Cosmetic dispatch. Schedule handyman
        or order replacement screen. Batch with other work at the property
        if possible.
```

## Tenant-fixable resolution steps

1. **Clean window track** (Level 3+): Vacuum debris from the track. Wipe with a damp cloth. Try opening/closing again. Applies to sliding and double-hung windows.

2. **Break paint seal** (Level 3+): Run a sharp utility knife or putty knife along the seam between the sash and frame. Score the paint. Try opening.

3. **Temporary security for broken lock** (sliding window): Place a wooden dowel or cut broomstick in the track so the window can't be opened from outside.

## When to dispatch

- Broken glass with exposure or security concern
- Lock broken on accessible window
- Window won't close during cold or severe weather
- Hardware broken (cranks, balances, locks)
- Painted or swollen shut and scoring doesn't free it
- Any window issue the tenant cannot safely resolve

## Vendor category to dispatch

Glass company for broken panes and sealed unit (double-pane) failures. Handyman for hardware, locks, tracks, and screens. Window specialist for full window replacement (old, rotted, failed units).

## Temporary mitigation while awaiting dispatch

- **Broken glass with opening**: Tape cardboard or heavy plastic over the opening from inside. Clear any loose shards (carefully, with gloves).
- **Can't close in cold weather**: Tape plastic sheeting over the entire window frame from inside to reduce heat loss. Towels at the sill to block draft.
- **Can't lock (security)**: Wooden dowel in the track (sliding), or partially driven screw in the frame above the sash (hung windows) to prevent opening from outside.
- **Won't open**: Not a mitigation scenario. Schedule repair.

## Tenant responsibility notes

Never tenant-responsible for window mechanisms, locks, glass, or frames. These are structural building components.

Exception: if a tenant broke the glass (ball, object thrown, etc.) or damaged the mechanism through misuse, it may be tenant-responsible for cost. But the repair is still owner-coordinated. Dispatch first, investigate responsibility after.

Screens: varies. Some leases hold tenants responsible for screen damage. Check lease terms.

## Work order fields to capture at dispatch

- Which window (room, location, floor)
- Type of window (sliding, double-hung, casement, awning)
- Nature of issue (glass, lock, mechanism, track, screen)
- Photo of the problem
- Whether there's a current security or weather concern
- Window dimensions if possible (helps vendor prep glass or parts)
- Whether the window is accessible from outside (ground floor, fire escape)
- Tenant availability

## Suggested tenant communication

**Broken glass, security concern**: "I'm treating this as a priority since it's a security issue. I'll have someone out today to board it up or replace the glass. In the meantime, if you can safely tape some cardboard over the opening from inside, that'll help."

**Won't lock, accessible window**: "A window that won't lock on the ground floor is something I want to fix quickly. If you have a wooden dowel or a cut broomstick, you can place it in the window track as a temporary block so it can't be opened from outside. I'll get a handyman scheduled for the lock."

**Won't open (stuck)**: "I'll get a handyman out to free that up. Just so you know, if that's a bedroom window, it's supposed to be openable as an emergency exit, so I'll make sure we get it scheduled within the week."

## Notes for coordinator agent

- Broken window glass has liability potential (injury from shards). If a tenant or their child is injured by broken glass, escalate to PM immediately.
- Ground-floor window security issues should be same-day dispatch. Don't let a tenant sleep with an unsecured accessible window.
- Bedroom windows that won't open are a fire code egress violation in most jurisdictions. Not an emergency, but flag for PM and schedule within the week.
- Window replacement (full unit, not just glass) is expensive. If the window is old and the frame is rotted, the vendor may recommend full replacement. Flag for NTE and owner decision.
- For double-pane windows with condensation between the panes (foggy glass): this is a seal failure. Not a security issue, but it reduces insulation. Schedule as Cosmetic. Some companies replace just the IGU (insulated glass unit) rather than the whole window.
- Screen replacement is low cost and batchable.
