# Tenant Intake Questions

Standard question sets by category. When a new maintenance request comes in, use these to gather enough information to classify the issue and route it correctly. Each KB entry has its own detailed intake questions for that specific issue. These are the general-purpose questions for initial triage before you've identified the specific issue.

## How to Use This File

1. Start with the universal questions (every request, regardless of category).
2. Once you have a rough category (plumbing, electrical, HVAC, appliance, general), ask the category-specific questions.
3. Once you've identified the specific issue, switch to the intake questions in the relevant KB entry for deeper diagnostics.

Don't ask all of these in one message. One or two at a time. The goal is a conversation, not a questionnaire.

## Universal Questions (Every Request)

These are the first things to establish, regardless of what the issue is.

1. **What's happening?** Let the tenant describe it in their own words first. Don't lead. "Tell me what's going on" or "What are you seeing?"
2. **When did it start?** Establishes urgency and timeline. "When did you first notice this?"
3. **Is anyone in danger?** Only ask explicitly if the description sounds like it could be safety-related. Otherwise, infer from context. If there's any doubt, ask: "Is everyone safe right now?"
4. **Which unit?** If not already known from the contact information.
5. **Where in the unit?** Room, location. "Which room is this in?"

After these, you should have enough to classify the issue into a category and check for emergency conditions per `references/decision-logic/severity-classification.md`.

## Plumbing

Ask these once you know it's a plumbing issue but haven't pinpointed the specific problem yet.

- **Is there standing water or active water flow?** Determines urgency. Standing water or active leaking gets priority.
- **How many fixtures are affected?** One fixture is usually a localized issue. Multiple fixtures point to a main line problem.
- **Is there any sewage smell?** Distinguishes drain issues from supply issues and flags potential health/habitability concerns.
- **Is the water on or off?** For leak situations. If the tenant can shut off a valve, that buys time.
- **Hot water, cold water, or both?** Narrows between supply issues, water heater problems, and fixture-specific problems.

## Electrical

- **Is anything sparking, smoking, or hot to the touch?** Safety screen. If yes, this is Emergency. Tell them to stop touching it and potentially leave the area.
- **What stopped working?** One outlet, one room, the whole unit, or specific appliances.
- **Did you check the breaker panel?** Many electrical issues are tripped breakers. If the tenant hasn't checked, walk them through it before asking more questions.
- **Are there any burning smells?** Another safety screen. Burning smell plus electrical issue is Emergency.
- **Did anything happen before it stopped working?** Plugging in a new appliance, a storm, a loud pop. Helps identify cause.

## HVAC

- **Heating or cooling?** Determines which system to focus on and whether this is a High severity issue (no heat in winter).
- **Is the system running at all?** No power vs. running but not producing heat/cool are different diagnostic paths.
- **What's the thermostat set to, and what's the actual temperature?** Confirms the system isn't just set incorrectly.
- **When was the filter last changed?** Clogged filters are the most common cause of poor HVAC performance and are often tenant-fixable.
- **Is this the whole unit or one room?** One room could be a vent or duct issue. Whole unit is the system itself.

## Appliances

- **Which appliance?** Get the specific appliance. "The oven" not "something in the kitchen."
- **What's it doing (or not doing)?** Not starting, making noise, leaking, not heating, error codes.
- **Is it plugged in?** Sounds obvious, but it resolves a surprising number of calls.
- **Did you try resetting it?** Unplug for 60 seconds, plug back in. Handles most control board glitches.
- **How old is it, if you know?** Helps the vendor decide repair vs. replace before arriving.

## General / Structural / Pest

- **Can you send a photo?** For structural, pest, mold, lock, and window issues, a photo is worth a hundred questions. Ask early.
- **Is this affecting your ability to use the unit normally?** Determines habitability impact. A stuck window is annoying. An exterior door that won't lock is a safety issue.
- **How long has this been going on?** Gradual deterioration (months) vs. sudden change (today) affects urgency and may indicate a bigger issue.
- **Is there any water or moisture involved?** Water damage escalates almost everything. A crack in the wall is standard. A crack in the wall with water coming through is urgent.

## When to Stop Asking and Act

Stop asking intake questions and move to action when:

- You've identified a Emergency issue. Act immediately.
- You've identified a High severity issue with a tight response window. Dispatch, don't diagnose.
- The tenant is frustrated with questions. If they've answered 4+ questions and you still aren't sure, dispatch and let the vendor diagnose on-site.
- You have enough to classify and route. You don't need to know everything before dispatching. You need to know enough to send the right vendor with the right urgency.

The intake questions are a tool, not a checklist. Use judgment.
