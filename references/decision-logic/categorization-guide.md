# Categorization Guide

## Purpose

This guide tells the agent how to assign a category to a tenant work order. Category determines which trade is dispatched. Get it wrong and you send an expensive plumber for a job a handyman could do in 20 minutes, or you send a handyman for a job that needs a licensed electrician.

This is the **backend common layer** — these rules apply to every property management company using the skill. Per-PM overrides go in `custom/decision-logic/categorization-guide.md`.

## Categories

| Category | Trade dispatched | When to use |
|---|---|---|
| **General** | Handyman | **Default for non-specialist work.** Multi-item visits, retrievals, caulking, simple hardware, fixture adjustments, outdoor hose / spigot work. The handyman handles anything that does not require a license or specialized tools. |
| **HVAC** | HVAC technician | Heating, cooling, thermostats, furnaces, boilers (including boiler-attached components like expansion tanks and blow-off valves), mini-splits, central air. |
| **Plumbing** | Plumber | Interior water supply, drains, toilets, sinks, faucets, leaks, sewer, sump pumps, water heaters, water pumps. |
| **Electrical** | Electrician | Outlets, breakers, wiring, switches, circuits, electrical panel work. |
| **Appliance** | Appliance repair tech | Refrigerator/freezer cooling, stove burners, dishwasher, washer/dryer, microwave, garbage disposal. **Exception:** if the task is "level the fridge" or "retrieve the appliance," that is handyman work, not appliance repair. |
| **Door/Lock/Window** | Handyman (locksmith only if rekey or smart-lock failure) | Door alignment, knobs, locks, deadbolts, keypads, windows, screens. |
| **Structural/Exterior** | Handyman for minor work; escalate major jobs | Roof, ceiling, decks, porches, stairs, siding, foundation, chimney, gutters. **Minor repairs** (loose step, gutter reattach, a deck board, trim, fascia, lattice) → the company's handyman. **Major work** (full deck/porch/roof/siding replacement, foundation, anything needing scaffolding or roof access) → escalate to PM/owner for approval and a specialty contractor. Most operations do not keep a carpenter or general contractor on staff, so do not auto-dispatch one; route per the company's configured vendor list. |
| **Pest** | Pest control | Mice, rats, roaches, bees, wasps, ants (the insect, not the substring), bedbugs, infestations. |
| **Mold/Air Quality** | Mold remediation specialist | Mold, mildew, musty smells, spores. **Always escalate to a human** (escalate=true). Mold is liability-sensitive, the cause is often something else (a leak, condensation, poor ventilation), and it may not even be mold. Do not auto-dispatch; a human reviews. Category stays Mold/Air Quality; the escalate flag fires alongside it. |
| **Safety/Detector** | Handyman or electrician | Smoke detectors, carbon monoxide alarms, fire extinguishers. |
| **Grounds** | Landscaping crew | Lawn, trees, snow, ice, salt, mulch. |
| **Interior/Cosmetic** | Handyman | Paint, drywall, tile, flooring, carpet, cabinets, trim. **Caulking is General, not Interior/Cosmetic** — caulking comes up too often as standalone handyman work. |
| **Tenant Complaint** | No vendor needed | Noise complaints, smoking complaints, neighbor disputes. Route to office. |
| **Property/Common Area** | Property staff or appropriate trade | Parking, dumpsters, trash, shared-area issues. |
| **Administrative** | No vendor needed | Insurance questions, billing, pet applications, lease questions. Route to office. |
| **Needs More Information** | None yet | The original report alone is genuinely ambiguous and cannot be routed to a trade without more information. Do not guess. Ask the tenant a clarifying question first, then categorize. See "Diagnose from the original report only" below. |
| **Multiple** | Escalate — a human coordinates the trades | A multi-item work order whose distinct items require **two or more different vendor types** (e.g. a handyman task plus a plumber task). It is not a single automated dispatch — one person must coordinate the separate vendors, sequencing, and any owner approval. Set `escalate=true` and `multi_item=true`, set `vendor_type` to `multiple`, and list every item with the trade it needs. A multi-item WO whose items are all **one** trade does NOT use this — classify it by that trade (see the multi-item rule below). |

## Category is the domain; the dispatched trade is a separate decision

Category describes **what system the issue belongs to**, not necessarily who you send. A category does not automatically dictate the most expensive specialist.

The clearest example: a **toilet is a Plumbing fixture, so any toilet issue is category Plumbing.** But you do not send a plumber for every toilet. A handyman can swap a flapper, a flush handle, or a fill valve, or fix a running toilet, for a fraction of a plumber's cost. So:

- **Category = Plumbing** (the toilet is plumbing).
- **Dispatched trade = handyman** for minor internal parts; **plumber** for a clog that needs snaking, overflow/flooding, a base or wax-ring leak, sewage backup, or a full replacement.

This "a handyman can handle minor work in a specialist domain" idea is general: keep the category honest (it reflects the system), and let vendor selection pick the cheapest competent trade for the actual scope.

**Ownership, so the two files don't drift:** this guide is authoritative on the *category* (what the issue is). `vendor-selection-rules.md` is authoritative on the *trade* (who to send and at what price). The toilet/caulking examples here are illustrations of the category-vs-trade principle; for the definitive handyman-vs-specialist call, `vendor-selection-rules.md` wins.

**Roster facts are configuration, not common rules.** This is the shared backend layer used by every property management company, so it must not hard-code one company's roster. Which trades a company keeps (whether the handyman is in-house or contracted, whether a carpenter or GC exists, the actual vendor names) lives in that company's `config.yaml` vendor list and in `custom/` overrides — never here. This guide states the principle ("route to the cheapest competent trade the company keeps; escalate work that needs a trade they don't have"); config supplies the roster.

The same split applies to **Structural/Exterior**: minor exterior repairs (loose step, gutter reattach, a deck board, fascia, lattice) go to the company's handyman. Major work (full deck/roof/siding replacement, foundation, anything needing scaffolding or roof access) is big-ticket and usually over NTE; since most operations do not keep a carpenter or general contractor on staff, it escalates to PM/owner for approval and an external specialist rather than auto-dispatching. (A company that does keep a carpenter sets it in the vendor list and routes there instead.)

(Contrast with caulking and outdoor hose bibs, which are categorized **General** outright — those are not core plumbing fixtures, they are general maintenance that happens to involve water.)

## Diagnose from the original report only

At triage time, **the only information you have is the tenant's original report.** There are no tech notes, no diagnosis, no resolution history. Those only exist after a vendor has already been out, which is too late to be triaging.

(Historical/completed work orders in test data may have notes and resolution
logs appended below the original report. Ignore them. Categorize as if the
work order just arrived and nothing has happened yet.)

When the original report alone does not give you enough to pick a trade, **do not force a guess.** Output **Needs More Information** and state the one question you would ask the tenant to resolve it.

Example: "Replace the thermal expansion tank." An expansion tank can sit on a water heater (Plumbing) or a boiler (HVAC). The original report does not say which. Correct output: **Needs More Information** — "Is this tank on your water heater or your boiler/heating system?" Do not pick HVAC or Plumbing on a coin flip.

This is correct behavior, not a failure. A wrong specialist dispatch costs a trip charge and delays the real fix. One clarifying question is cheaper.

### Ask the tenant vs. escalate to a human

Both produce the category **Needs More Information**, but the next action differs:

- **Askable** (escalate = false): you can name the single question that would unblock routing. Ask the tenant, wait for the answer, re-triage. This stays in the automated loop.
  - Example: "Replace the thermal expansion tank." → ask "Is it on your water heater or your boiler?"

- **Escalate to a human** (escalate = true): the report is incoherent, internally contradictory, empty of actionable content, or you genuinely cannot identify what single question would make it routable. Hand it to a human coordinator per `escalation-criteria.md`. Do not keep guessing and do not fire off a vague question just to avoid escalating.
  - Example: "fd" or "sorry have ocd" or a long rambling message with no identifiable maintenance issue → escalate. There is no single question that turns this into a routable work order.

**Subject test (decides askable vs escalate):** can you identify an actionable subject — an appliance, fixture, door, room, system — even if you have to decipher a typo or shorthand?

- **Subject identifiable → askable.** Continue, do not escalate. Ask what is wrong with that subject.
  - "fredge" clearly means the refrigerator. Subject identified. Ask: "What's going on with your fridge — is it not cooling, leaking, making noise, or something else?" Category Needs More Information, escalate = false.
  - "door issue" names a door. Ask: "What's wrong with the door — won't latch, won't lock, sticking?"
- **No subject identifiable → escalate.** "fd", "sorry have ocd", "Hi" — nothing to ask about. There is no subject to question.

So the full test: *can I identify a subject and name one question that would unblock this?* If yes to both, ask. If the report names no decipherable subject at all, escalate.

## Category and responsibility are different questions

Two separate columns answer two separate questions:

- **Category** = *what* is the problem / which trade. Values: the trades above, plus **Needs More Information**.
- **Responsibility** = *who* handles it. Values: **Vendor / Tenant / Owner**. Nothing else.

There is no "unknown" value in the responsibility column. Here is why, and how the two columns relate:

- **If category is a real trade**, assign responsibility (Vendor / Tenant / Owner).
- **If category is Needs More Information**, leave responsibility **blank/pending.** You cannot decide who is responsible for a problem you have not yet identified. Responsibility gets filled in after the tenant answers your clarifying question (or after a human resolves the escalation).
- **If responsibility is a genuine grey area** even with a known category (e.g., "garbage disposal jammed" — tenant misuse or normal wear?), do **not** stall. Assign **Vendor**, dispatch, and flag the work order for chargeback review. A human decides the chargeback later. Never argue responsibility with the tenant up front.

This keeps a single "can't proceed yet" signal — **Needs More Information** in the category column — instead of writing a near-synonym in two columns. When you do not know the problem, you say so once, in the category, and the responsibility column simply stays empty until you do.

## Decision pipeline

Process every work order through these checks in order. First match wins.

### 1. Is it a status check or follow-up message?

Phrases like "any update," "checking in," "still waiting," "what is the plan for X," "follow up on WO #...". These are not new issues. Category is **Needs More Information** (you must look up the referenced work order before you can act). Leave responsibility blank until then. Do not dispatch a vendor on a status check.

### 2. Is it a multi-item work order?

A WO is multi-item when it contains **two or more distinct issues — whether or not they are numbered.** Numbered lists (`1.`, `2.`, `3.`) are the obvious case, but multiple separate problems written as separate sentences or paragraphs count just the same. Read for distinct issues, do not just look for numbers.

Example of an unnumbered multi-item WO:
> "Mice droppings in the kitchen counter. Weak water pressure, can't run two appliances at once. Toilet only has hot water running to it. Shower water is really weak."

That is four distinct issues (pest, water pressure, toilet, shower) with no numbering — it is multi-item.

Rule — decide by how many distinct **vendor types (trades)** the items need. Read each item, decide its trade (see `vendor-selection-rules.md`), then count the distinct trades:

- **All items need the same single vendor type** → classify by the **first item's category**, add `multi_item: true`, and dispatch that one vendor for the whole visit. Do not escalate. (If every item is handyman work, the category is **General** — unless the first item carries a more specific category that still routes to a handyman, e.g. Safety/Detector, in which case keep the first item's category.)
- **The items span two or more different vendor types** (e.g. a handyman task plus a plumber task, or a pest job plus a plumbing job) → category is **Multiple**, with `multi_item: true` and `escalate: true`. A multi-trade work order is not a single automated dispatch: a human coordinates the separate vendors, sequencing, and any owner approval. Set `vendor_type` to `multiple` and list every item with the trade it needs in the escalation notes.

Examples:
- "1. Smoke alarm going off. 2. Fix screen door." → both are handyman work → one vendor type → **Safety/Detector** (first item) + `multi_item: true`, no escalation.
- "1. Front screen door doesn't close. 2. Back screen door doesn't close. 3. Bathroom door sticks. 4. Fridge needs leveling." → all handyman → one vendor type → **General** + `multi_item: true`.
- "Mice droppings... Weak water pressure... Toilet hot water only... Shower weak." → pest control **plus** plumbing → two vendor types → **Multiple** + `multi_item: true` + `escalate: true`.
- "Remove the old vanity and run new water lines, then patch and paint the wall." → plumber **plus** handyman → two vendor types → **Multiple** + `escalate: true`.

### 3. Action verb override

If the first directive line starts with **retrieve**, **pick up**, **drop off**, **deliver**, **haul**, **remove**, **dispose**, **move**, or **bring back**, the WO is **General** regardless of the object.

Example: "Retrieve the mini fridge" → General (handyman task), not Appliance.

### 4. Context overrides

- **"Boiler" mentioned anywhere → HVAC.** Even when plumbing keywords are also present. Expansion tanks, blow-off valves, and bleed work attached to a boiler are HVAC, not plumbing. Water heaters (no boiler) stay Plumbing.

### 5. Handyman-grade overrides (handyman, not specialist)

These words look like Plumbing but should route to **General** unless paired with an active-leak or flooding signal:

- **caulk / caulking / caulked / recaulk** — handyman work. Only Plumbing if "caulking failure is causing an active leak."
- **outdoor hose / garden hose** — handyman work. Plumbing only if the hose tap or supply line is flooding the property.
- **hose bib / spigot** — handyman work for replacement. Plumbing only if it is connected to an interior leak or main shutoff issue.

Escalation signals that flip these back to Plumbing: "flooded," "flooding," "soaked," "actively leaking," "pouring water," "burst," "overflowing," "sewage," "won't clear / snake."

### 6. Keyword categorization

Run the description through the keyword rules in order. First match wins. Categories listed in the table above each have a keyword set. Use word-boundary matching so "ant" only matches the insect, not "tenant" or "plants."

### 7. Fallback

If nothing matches, **General** (handyman, assess on arrival). Do not throw the WO into a specialist queue out of indecision.

## Common mistakes to avoid

- **Substring matching.** "Tenants" contains "ants." "Important" contains "ant." Always use word boundaries.
- **Categorizing on a vendor or company name.** A work order may name a vendor — e.g., "as recommended by [a well & pump service]," "forwarded to [an HVAC company]." Those are company names, not the issue. Do not let "Well & Pump" route to Plumbing or "Heating & Cooling" route to HVAC. Categorize on the actual task. Example: "Routine UV filter/lamp replacement, recommended by the well-service company" → the task is a routine filter/lamp swap → **General**, not Plumbing.
- **Object over action.** "Retrieve the mini fridge" is handyman work, not appliance repair. The verb is doing the work.
- **Guessing on ambiguous reports.** If the original report does not say enough to pick a trade, output Needs More Information and ask one clarifying question. Do not coin-flip between two specialists.
- **Multi-item visits routed to one specialist.** A handyman can handle three small things in one trip cheaper than dispatching three specialists. Default to handyman unless the first item genuinely needs a specialist.
- **Caulking as Plumbing.** Caulking around a tub or window is handyman work. The plumber only gets called when caulking failure is causing an active water problem.

## How this guide is maintained

Rules in this file are derived from real corrections to mis-classified work orders. Each rule traces back to a specific feedback round. When a property management company corrects a categorization in their data, the correction is reviewed against this guide:

- If the correction matches a pattern that would apply to other PMs, update this file.
- If the correction is specific to one PM (their own lease language, their own vendor preferences), update `custom/decision-logic/categorization-guide.md` for that PM only.

See the changelog at the bottom of this file for the lineage of each rule.

## Changelog

- **Round 1 (2026-05-27):** Initial seven rules from first feedback batch.
  - General = handyman semantic (was treated as "couldn't classify").
  - Multi-item detection added.
  - Action verb override added.
  - Caulking moved out of Plumbing.
  - Outdoor hose / hose bib / spigot moved out of Plumbing.
  - Boiler context override added (boiler-attached components → HVAC).
  - ~~Tech notes preserved during extraction.~~ (Reverted, see round 2.)
- **Round 2 prep (2026-05-27):** Triage-realism correction.
  - Removed the round 1 "preserve tech notes" rule. At triage time there
    are no tech notes; the agent diagnoses from the tenant's original
    report only. Test data must strip appended notes/logs before grading.
  - Added **Needs More Information** as a valid category for reports that are
    genuinely ambiguous without more information (ask one question, do not
    guess between specialists). Reframes the round 1 expansion-tank case:
    on the original report alone it is Needs More Information, not HVAC.
  - Added escalate-to-human for reports that cannot be routed AND cannot be
    resolved with a single clarifying question (incoherent / empty intake).
  - Subject test: if you can identify (or decipher from a typo) an actionable
    subject, it is askable -- continue and ask, do not escalate. "fredge"
    -> ask about the fridge. Only escalate when NO subject is identifiable
    at all ("fd", "sorry have ocd").
  - Removed "Needs Investigation" as a responsibility value. Responsibility
    is Vendor / Tenant / Owner only. The single "can't proceed yet" signal
    lives once, in the category column, as Needs More Information; when it
    is set, responsibility stays blank until the issue is identified. Grey-
    area who-pays is handled by dispatching Vendor + a chargeback-review
    flag, not by a separate responsibility value.
- **Round 2 (2026-05-28):** 20/20 category-correct. One clarification:
  - Category is the domain; the dispatched trade is separate. A toilet is a
    Plumbing fixture, so toilet issues stay **category Plumbing** — but a
    handyman (not a plumber) is dispatched for minor internal parts (flapper,
    flush handle, fill valve, running toilet). Plumber for clogs needing a
    snake, overflow/flooding, base/wax-ring leaks, sewage, replacement.
    (Corrected an initial misread that had moved the category itself to
    General; the category stays Plumbing, only the trade differs.)
- **Round 3 (2026-05-28):** 19/20 category-correct. Three refinements:
  - Multi-item detection is not just numbered lists. Two or more distinct
    issues count as multi-item even when written as separate unnumbered
    sentences/paragraphs.
  - Mold/Air Quality always escalates to a human (liability-sensitive,
    cause often something else, may not be mold). Category stays
    Mold/Air Quality; escalate flag fires alongside it.
  - Do not categorize on vendor/company names. A "well & pump service"
    name misrouted a UV-lamp swap to Plumbing; the task (routine
    filter/lamp replacement) is General. Categorize on the task, not the
    company name in the text.
  - Structural/Exterior trade fix: there is no standing carpenter or
    general contractor. Minor exterior/structural repairs go to the
    in-house handyman; major work (full deck/roof/siding replacement,
    foundation, scaffolding/roof access) escalates to PM/owner for a
    specialty contractor + NTE approval. Category stays Structural/
    Exterior; only the dispatched trade changed.
- **Integration sweep (2026-05-29):** Wired this guide into SKILL.md's
  decision flow (it was previously orphaned and never loaded at runtime),
  verified via a no-hint production-path test (10/10 consistent). Then
  reconciled the rest of the skill to the rules above:
  - Mold: reconciled to "agent escalates at triage; human applies the KB's
    small-vs-large nuance after." Removed "handyman cleans small mold" from
    vendor-selection-rules.md and added a triage-rule banner to the
    mold-moisture.md KB entry (agent escalates every mold report; the size
    thresholds and tree are the human's post-escalation tool). The agent
    can't tell small grout mold from the tip of a hidden leak from text
    alone, so it does not auto-dispatch mold.
  - Carpenter/GC: updated the two lock/door KB entries to handyman +
    escalate-major, removing the standing-carpenter assumption.
  - Ownership: category lives here, trade lives in vendor-selection-rules.md;
    added explicit notes in both so they don't drift.
- **De-localize pass (2026-05-29):** Removed one company's roster facts from
  this shared backend file so it is safe for the open-source community and
  any PM to use. "In-house handyman" and "there is no standing carpenter"
  became the config-driven principle "route to the trades the company keeps;
  escalate work needing a trade they don't have." Vendor-name examples
  (a well & pump service, an HVAC company) genericized. Roster facts
  (in-house vs. contracted, whether a carpenter exists, vendor names) now
  live only in config.yaml / custom/, never in this common guide. Same fix
  applied to the carpenter references in the door/lock KB entries.
