# Habitability Response Windows

Required response times for habitability issues by jurisdiction. The agent must check this before deciding whether to triage or dispatch immediately. If the response window is tight and triage will take time, skip triage and dispatch.

## What Counts as Habitability

Under the implied warranty of habitability (recognized in all US states), landlords must maintain rental units in a condition fit for human habitation. The specific items vary by state, but these are universally included:

- Working heat (during heating season)
- Hot water
- Working plumbing (at least one functional toilet, no sewage exposure)
- Weatherproofing (roof, windows, exterior doors that close and lock)
- Working electrical (safe, functional)
- Pest-free conditions (from infestations, not single sightings)
- Structural soundness
- Working smoke detectors (required by code in all states)
- Working locks on exterior doors

Some states additionally include:

- Air conditioning (varies by state, some only in certain temperatures)
- Working appliances if provided by the landlord
- Mold remediation
- Adequate ventilation

## How to Use This File

When the agent classifies an issue as High severity (habitability) per `severity-classification.md`, it should:

1. Identify the tenant's jurisdiction (state, and city if relevant)
2. Look up the response window below
3. If the window is 24 hours or less and triage hasn't resolved the issue quickly, dispatch immediately
4. Note the applicable response window in the work order so the PM and vendor are aware of the deadline
5. If the jurisdiction isn't listed, use the conservative default (24 hours for no heat/hot water, 48 hours for other habitability)

## Response Windows by State

**IMPORTANT**: This is a reference guide, not legal advice. State and local laws change. The agent should flag the applicable statute for PM review rather than making legal claims to the tenant. Some cities have stricter requirements than their state. When in doubt, use the shorter window.

### Heat

Most states require heat to be restored "within a reasonable time." In practice:

- **24 hours or less**: California, New York, Massachusetts, Illinois, New Jersey, Connecticut, Maryland, Washington DC, Minnesota, Wisconsin
- **48 hours**: Most other states with explicit timelines
- **"Reasonable time" (no specific hours)**: Many southern states where heating emergencies are less common
- **Override**: If outdoor temperature is at or below freezing, treat as Emergency (life-safety) regardless of jurisdiction. Don't wait for a habitability clock.

### Hot Water

- **24 hours**: California, New York, Massachusetts, Illinois, New Jersey, Connecticut, Washington DC
- **48 hours**: Most other states
- **Override**: None. Hot water loss is never Emergency, but it is always High severity (habitability).

### Plumbing (No Working Toilet)

- **24 hours**: Most jurisdictions treat a single-toilet unit with no working toilet as requiring prompt repair
- **Override**: If there are multiple toilets and at least one works, this drops to Low severity. If sewage is backing up, reclassify as Emergency (life-safety).

### Exterior Door Security

- **Same day**: A door that cannot be secured is treated as an emergency in virtually all jurisdictions. Do not leave a tenant with an unsecurable exterior door overnight.

### Air Conditioning

This is the most jurisdiction-dependent habitability item. Many states do not consider AC a habitability requirement at all.

- **Required as habitability**: Arizona, Nevada, Texas (some cities), Florida (some cities), Georgia (some cities), Louisiana (some cities)
- **Not required as habitability (even if provided)**: Most northern and temperate states
- **Temperature-triggered**: Some jurisdictions only require AC when outdoor temps exceed a threshold (often 95F or 100F)
- **When provided**: Some jurisdictions say if the landlord provides AC, they must maintain it, even if AC isn't generally required

The agent must look up the specific jurisdiction during onboarding or when an AC complaint comes in. Do not assume AC is or isn't required without checking.

### Pest Control

- **Varies widely**: Some states require landlord response within 14-30 days for non-emergency pest issues. Bedbugs often have shorter windows (7-14 days in some cities).
- **Infestations**: Treated as habitability in all states. Single sightings are not.

## What to Do When the Clock Is Running

1. Note the deadline in the work order (e.g., "Habitability: heat must be restored within 24 hours per [state] law")
2. Dispatch with appropriate urgency
3. If the vendor cannot meet the window, escalate to PM immediately
4. If the issue cannot be resolved within the window (e.g., water heater replacement on backorder), escalate to PM for tenant communication and potential temporary accommodation or rent abatement
5. Document everything: when the issue was reported, when it was dispatched, when the vendor responded, when it was resolved

## Configuration

During onboarding, the agent captures the company's jurisdiction(s). For companies managing properties in multiple states, the agent should track which properties are in which jurisdiction and apply the correct window per property. If the company provides custom response windows that are stricter than the legal minimum, use the company's windows.
