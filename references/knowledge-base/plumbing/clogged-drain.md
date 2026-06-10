---
id: KB-PLUMB-003
category: plumbing
subcategory: drains
title: Clogged or Slow Drain
severity: low
tenant_fixable: true
tenant_responsible: sometimes
required_photos: false
required_videos: false
typical_resolution_minutes: 10
response_target_hours: 72
jurisdictions: all
last_reviewed: 2026-05-05
---

# Clogged or Slow Drain

## Symptoms covered

- Kitchen sink draining slowly
- Bathroom sink draining slowly
- Bathtub or shower draining slowly
- Sink completely stopped up (standing water)
- Multiple drains slow at the same time

Does NOT cover: toilet clogs (see KB-PLUMB-002), sewage backing up into the unit (Emergency severity), drains making gurgling sounds with no slow drainage (possible vent issue, dispatch directly), water backing up into a different fixture than the one being used (main line issue, dispatch directly).

## Intake questions for tenant

1. Which drain is slow or clogged? (Kitchen sink, bathroom sink, bathtub/shower, or multiple?)
2. Is the water draining at all, or is it completely standing?
3. Has this been getting worse over time, or did it happen suddenly?
4. For kitchen sinks: do you have a garbage disposal? Is it working?
5. For bathroom drains: is there visible hair or buildup near the drain opening?

**Classification check**: If multiple drains are slow simultaneously, this is likely a main sewer line issue, not a single fixture clog. Classify as urgent (risk of sewage backup) and dispatch directly. Do not attempt triage on suspected main line issues.

If there is any sewage smell or water is backing up into a different fixture, reclassify per `severity-classification.md`.

## Diagnostic decision tree

```
START
│
├─ Is it MULTIPLE drains at once?
│   └─ Yes → suspected main line issue. DISPATCH. Do not triage.
│
├─ KITCHEN SINK
│   ├─ Does the unit have a garbage disposal?
│   │   └─ Yes → is the disposal working? Run it with water flowing.
│   │       └─ If disposal is jammed/dead → see KB-PLUMB-001 first.
│   │           Clearing the disposal often fixes the drain.
│   │       └─ If disposal runs fine but drain is still slow → continue
│   ├─ Is there a clean-out plug under the sink? (Some have a removable
│   │   plastic piece at the P-trap.)
│   │   └─ At Level 4+: tenant can place a bucket, remove the clean-out,
│   │       let water drain into bucket, clear any debris, replace plug.
│   │   └─ Below Level 4: skip this step.
│   ├─ Try running hot water for 2-3 minutes straight. Does it improve?
│   │   └─ If improved → likely grease buildup. Advise running hot water
│   │       after every use. RESOLVED.
│   │   └─ If not → DISPATCH
│   └─ Note: do NOT recommend chemical drain cleaners (Drano, Liquid Plumr).
│       They can damage pipes, are a liability issue, and rarely work on
│       full clogs. The agent should never suggest them.
│
├─ BATHROOM SINK
│   ├─ Is there a visible pop-up stopper in the drain?
│   │   └─ Yes → pull it out (most lift or twist out). Clean off hair and
│   │       gunk. Replace. Test.
│   │       └─ If draining now → RESOLVED
│   │       └─ If still slow → continue
│   ├─ Can the tenant see hair or buildup in the drain opening?
│   │   └─ Yes → remove with fingers or a bent wire/zip-it tool if available.
│   │       Run water. Test.
│   │       └─ If draining → RESOLVED
│   │       └─ If still slow → DISPATCH
│   └─ If no visible obstruction and still slow → DISPATCH
│
├─ BATHTUB or SHOWER
│   ├─ Is there a drain cover/screen?
│   │   └─ Remove it (most pop off or unscrew with one screw).
│   ├─ Is there visible hair accumulated at or just below the drain opening?
│   │   └─ Yes → pull it out. This is usually a clump of hair wrapped
│   │       around the drain cross. Use fingers or a bent wire.
│   │       └─ If draining now → RESOLVED. Recommend a drain screen
│   │           to prevent recurrence.
│   │       └─ If still slow → DISPATCH
│   └─ If no visible obstruction → DISPATCH
│       (The clog is deeper in the P-trap or drain line and needs a snake.)
│
└─ If none of the above resolve → DISPATCH
```

## Tenant-fixable resolution steps

1. **Remove and clean the stopper or screen**: Most bathroom drain stoppers lift or twist out. Clean off accumulated hair and soap buildup. Replace and test.

2. **Pull hair from shower drain**: Remove the drain cover (pop off or one screw). Pull out the hair clump that's usually right at the opening or just below it. Replace cover.

3. **Hot water flush for kitchen grease**: Run hot water (hottest from the tap, not boiling) for 2-3 minutes continuously. This can melt soft grease buildup.

4. **P-trap cleanout** (Level 4+ only): Place a bucket under the P-trap. Remove the cleanout plug or the slip nuts on the P-trap. Let water and debris drain into the bucket. Clear any blockage. Reassemble hand-tight. Then run water immediately and check for drips at the connections. If it leaks, tighten slightly or dispatch.

## When to dispatch

- Multiple drains slow at the same time (main line issue)
- Kitchen sink clog that doesn't respond to hot water flush and disposal is working fine
- Bathroom drain with no visible obstruction at the opening
- Any drain the tenant has already tried to clear without success
- Recurring clogs at the same drain (may need professional snaking or camera inspection)
- Tenant unable or unwilling to perform steps

## Vendor category to dispatch

Handyman for simple drain snaking at a single fixture. Plumber for main line issues, recurring clogs, or if a camera inspection is needed (flag for NTE). Most single-fixture clogs are handyman-level work.

## Temporary mitigation while awaiting dispatch

- If completely stopped: don't use that fixture. Use a different sink/tub if available.
- If slow but draining: usable but annoying. Let it drain fully between uses.
- Kitchen: don't pour grease or food down the slow drain (makes it worse).
- Bathtub/shower: removable hair from the drain opening even if it doesn't fully fix the issue (reduces it).

## Tenant responsibility notes

Many leases classify single-fixture drain clogs as tenant responsibility, especially bathroom drains (hair) and kitchen drains (grease). Check the tenant-responsibility-matrix for the company's policy. Even if tenant-responsible, still provide troubleshooting guidance. If dispatch results in a chargeback, the PM handles that communication, not the coordinator. Main line clogs are always owner responsibility regardless of lease terms.

## Work order fields to capture at dispatch

- Which fixture (kitchen sink, bathroom sink, tub/shower, multiple)
- Completely stopped or slow
- Whether tenant tried anything (stopper removal, hot water, plunger)
- Whether multiple drains are affected (main line indicator)
- Whether there's a gurgling sound or sewage smell
- Tenant availability

## Suggested tenant communication

**Single slow drain**: "It sounds like a standard clog. I'll get a plumber scheduled to snake it out. In the meantime, that fixture will be slow but usable."

**Multiple drains**: "If multiple drains are slow at the same time, that usually means it's deeper in the system, not just one fixture. I'm dispatching a plumber with priority on this one because a main line issue can get worse fast."

**After resolution, prevention advice**: "To keep this from happening again: in the kitchen, avoid putting grease down the drain. In the bathroom, a cheap drain screen catches hair before it goes down. Those two things prevent most clogs."

## Notes for coordinator agent

- Drain clogs in kitchens are commonly caused by grease, food particles, and improper disposal use. If the clog is resolved by triage, advise the tenant on prevention: no grease down the drain, run cold water during disposal use, don't put fibrous vegetables (celery, onion skins) in the disposal.
- Drain clogs in bathrooms are almost always hair. A cheap drain screen/hair catcher prevents most recurrences. Recommend one.
- Never suggest chemical drain cleaners. They're a liability, they damage pipes over time, they're ineffective on full clogs, and if a plumber arrives after the tenant has poured chemicals, it creates a hazardous working condition.
- If the tenant reports a gurgling sound from drains without slow drainage, that's a venting issue, not a clog. Dispatch directly (plumber).
- Flag camera inspections and main line work for NTE.
