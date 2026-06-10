---
id: KB-APPL-005
category: appliances
subcategory: general
title: Appliance Repair vs. Replace (Age & Lifespan)
severity: low
tenant_fixable: false
required_photos: true
required_videos: false
typical_resolution_minutes: 15
jurisdictions: all
last_reviewed: 2026-06-10
---

# Appliance Repair vs. Replace (Age & Lifespan)

When an owner-supplied appliance has failed (not a simple swap, not user error), decide whether to **repair** it or **replace** it before dispatching. Old appliances are often more cost-effective to replace than to repair — pouring a major repair into an appliance near the end of its life usually buys only a short reprieve before the next component fails.

This is a money decision the coordinator frames and the **owner approves** (replacement is a big-ticket item — see `owner-approval-rules.md`). It does not apply to routine swaps (a plain "replace the stove" is a handyman swap) or tenant-responsible items (filters, batteries).

## Typical appliance lifespans

Industry-consensus *typical* ranges. They are guidelines, not guarantees — usage, maintenance, water hardness, and brand all move the number.

| Appliance | Typical lifespan |
|---|---|
| Refrigerator / freezer | 10–15 years |
| Range / oven (electric) | 13–15 years |
| Range / oven (gas) | ~15 years |
| Cooktop | 13–15 years |
| Dishwasher | 9–10 years |
| Washing machine | 10–13 years |
| Clothes dryer | 10–13 years |
| Microwave (over-range/built-in) | 9–10 years |
| Garbage disposal | 10–12 years |
| Water heater (tank) | 8–12 years |
| Water heater (tankless) | ~20 years |
| Furnace | 15–20 years |
| Central AC / heat pump | 12–15 years |
| Window AC unit | 8–10 years |

## The repair-vs-replace rule

Use the **50% rule**, weighted by age:

- **Replace** if the estimated repair cost is **≥ 50% of a comparable new unit**, OR the appliance is **at/past its typical lifespan**, OR a **major component** failed (compressor, sealed system, control board, main motor, heat exchanger).
- **Replace** also when the same unit has needed **repeated repairs** — appliances age as systems; one worn part usually means others are close behind, and a repair never raises the unit's value.
- **Repair** when the appliance is **well within its lifespan** (rough rule of thumb: under ~50% of typical life) **and** the repair is a **minor/cheap part** (igniter, thermostat, valve, hinge, gasket, belt).
- **In warranty** → pursue the warranty repair regardless of the above.

The combined "50/50" test: an appliance that is **both** past ~half its expected life **and** facing a repair ≥ 50% of replacement → replace.

## Determining the appliance's age (the model-sticker photo)

To apply the rule you need the appliance's **age**. Get it from the **rating/serial plate**:

1. **Ask the tenant for a clear photo of the model + serial number plate.** Typical locations:
   - **Refrigerator/freezer:** inside, on a side wall or ceiling of the fresh-food compartment, or behind the kick plate.
   - **Range/oven:** on the door frame, behind/under the door, or a side panel; ranges often on the storage-drawer area.
   - **Dishwasher:** on the inner door edge or the tub side.
   - **Washer/dryer:** inside the door/lid opening, or on the back panel.
   - **Water heater / furnace / AC:** the main rating label on the body.
2. **Decode the manufacture date from the SERIAL number** (not the model number). Encoding varies by manufacturer, so use the brand's scheme or an appliance-age-finder lookup. Examples: **GE** — the first two letters encode month/year; **Whirlpool** — a letter near the end encodes the year; **LG** — leading digits give year then month; **Frigidaire** — first digit = year, next = week of year.
3. **If the date can't be decoded**, ask the tenant how long the appliance has been in the unit (or since move-in), or have the dispatched tech read the age on site before quoting.

Record the model, serial, and derived age in the work order so the owner can see the basis for a repair-vs-replace recommendation.

## How it routes

- **Repair (worth it):** dispatch **appliance_repair** for the internal mechanical fix.
- **Replace:** this is a big-ticket item → **get owner approval** (`owner-approval-rules.md`). A vendor who recommends replacement is already an escalation trigger (`escalation-criteria.md`). The install itself is usually a **handyman** swap for a simple plug-in unit, or a specialist when there's a gas, water-line, or hardwired hookup.
- **Cannot determine age and it matters to the decision:** capture what you can, flag it, and let the owner or the on-site tech make the call — do not block the work order on a missing date.

## Notes for coordinator agent

- This only applies to **owner-supplied** appliances. A tenant's own appliance is the tenant's responsibility.
- Lifespans are **typical**, not absolute. A well-maintained unit can outlive the range; a heavily-used one can fall short. Treat the table as a prior, not a verdict.
- Safety first: for any **gas** appliance with a gas smell, this decision is moot — that is an Emergency (life-safety), dispatch immediately.
- Don't over-apply: a clogged filter, a tripped reset, a loose hinge, or a "replace the stove" swap are not repair-vs-replace calls.
