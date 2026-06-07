# Your customization layer

Everything in this directory **except this README is gitignored**. It's yours: your
customizations are never uploaded and are never overwritten when you pull skill updates.

The shipped backend (`SKILL.md` + `references/`) is community-maintained and stays the
same for every company. You don't edit it. You layer your changes on top, here.

## The one question: are you modifying, or adding?

**Modifying how the skill already behaves → write a rule in `custom/rules.md`.**
One plain-English line, layered on top of the always-current backend. Covers:

- Tweaks to an existing knowledge base article or decision
  ("for toilet clogs, always send a handyman; don't treat a clog as an emergency").
- General house rules ("never dispatch on Sundays", "always CC the regional manager").
- Custom emergency rules ("any water on the floor, regardless of source, is an emergency").

Modifying existing knowledge base content **must** be a rule here — do not copy a backend
KB file into `custom/` to edit it, or you freeze your copy and stop getting upstream fixes.
You can also just tell the agent a rule in conversation and it will save it here for you.

    custom/
    └── rules.md          # your house, emergency, and existing-KB-modification rules

**Adding knowledge the backend doesn't have at all → a new file.**
For an issue with no backend entry (e.g. pool maintenance), create a new knowledge base
entry, mirroring the backend structure, with a `KB-LOCAL-` id:

    custom/
    └── knowledge-base/
        └── general/
            └── pool-maintenance.md     # id: KB-LOCAL-POOL-001

Follow `references/knowledge-base/TEMPLATE.md` for the format.

## Precedence

When your customizations conflict with the backend, **custom wins** — every time, with one
exception. If a rule would conflict with a **life-safety** instruction (gas, carbon monoxide,
fire, electrical hazard, major flooding, or an evacuate/escalate directive), the agent does
**not** apply it silently — it double-checks with the property manager (or human maintenance
coordinator) that the change is intended before acting.

## Settings vs. rules

Structured settings (NTE limit, vendor list, tone, troubleshooting level) live in
`assets/config.yaml`, not here. This directory is for behavioral rules and new knowledge.
