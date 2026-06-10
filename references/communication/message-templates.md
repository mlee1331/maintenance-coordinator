# Message Templates

Reusable message patterns for common situations. These are starting points, not scripts. Adapt them to the situation, the tenant, and the company's configured tone. Always check `config.yaml` for company-specific phrases to include or avoid.

Placeholders use `[brackets]`. Replace with actual values before sending.

## Acknowledging a New Request

**Standard**:
"Hi [name], thanks for reaching out. Let me take a look at this and figure out the best next step."

**When it sounds urgent**:
"Hi [name], thanks for letting me know. This sounds like it needs attention right away. Let me get on it."

**When tenant is clearly frustrated**:
"Hi [name], I hear you. Let's get this sorted out. Can you tell me a little more about what's going on so I can get the right person out there?"

## Troubleshooting

**Starting troubleshooting**:
"Before I send someone out, there are a couple things we can try that might fix this right now. Want to give it a shot? Should only take a few minutes."

**If tenant declines troubleshooting**:
"No problem at all. I'll get someone scheduled to come take a look."

**During troubleshooting**:
"OK, great. Here's what I'd like you to try: [step]. Let me know what happens."

**Troubleshooting resolved it**:
"Glad that worked! If it comes back or anything else seems off, just let me know."

**Troubleshooting didn't resolve it**:
"OK, sounds like this one needs a pro. I'll get [vendor type] scheduled to come out."

## Requesting Photos

See `photo-request-guide.md` for detailed guidance on when and how to request photos. These are the message patterns.

**First request**:
"Can you send me a photo of [specific thing]? That'll help me figure out the right next step."

**Requesting a specific angle or detail**:
"Could you get a close-up of [specific area]? And if possible, put something next to it for scale, like a coin or your hand."

**If tenant can't send photos**:
"No worries. I'll make sure the vendor knows to document it when they arrive."

## Dispatching a Vendor

**Standard dispatch confirmation**:
"I've got [vendor type] coming out to [address]. I'll confirm the exact time as soon as they get back to me and let you know."

**With confirmed time**:
"[Vendor type] is confirmed for [day] between [time window]. They'll [describe what they'll do]. If that time doesn't work, let me know and I'll reschedule."

**With access instructions needed**:
"I've got the vendor scheduled. A couple quick questions: will someone be home to let them in? Any pets they should know about?"

**Emergency dispatch**:
"I'm sending [vendor type] out right now. They should be there within [timeframe]. In the meantime, [any immediate safety or mitigation instructions]."

## Vendor Coordination

**Dispatch to vendor**:
"New work order at [address], unit [number]. [Issue summary]. [Urgency level]. NTE: [amount]. Tenant contact: [name, phone]. Access: [instructions]. [Any pets or special notes]."

**Follow-up with vendor**:
"Checking in on the work order at [address]. What's the status?"

**Vendor completed work**:
"Thanks. I'll follow up with the tenant to make sure everything's good."

## Tenant Responsibility

**Informing tenant before dispatch**:
"I want to let you know upfront that per your lease, [issue type] is the tenant's responsibility costwise. I'm still happy to send someone out. Just wanted you to be aware before we dispatch."

**If tenant disputes**:
"I hear you. Let me flag this for the property manager so they can take a look at it with you directly."

Never argue responsibility more than once. State it, note it in the work order, and move on. See `references/decision-logic/tenant-responsibility-matrix.md`.

## Waiting for Owner Approval

**Initial delay notification**:
"The repair needs the property owner's approval before we can move forward. I've sent the request and I'm waiting to hear back. I'll update you as soon as I have an answer."

**Extended delay**:
"I'm following up with the owner on the approval. I know this is taking longer than ideal and I appreciate your patience. I'll let you know as soon as I hear back."

**Habitability clock running**:
"I'm escalating this because I know you need this resolved. I'm doing everything I can to speed it up."

See `references/decision-logic/owner-approval-rules.md` for the full approval workflow.

## Escalation to PM

**Standard escalation context** (internal, not tenant-facing):
"Escalating [work order ID] at [address]. Summary: [what happened, what was tried, where things stand]. Urgency: [level, habitability deadline if applicable]. Recommendation: [what the coordinator thinks should happen]. Tenant status: [waiting, upset, safe]. Documentation: [photos, work order, communication history attached]."

**Telling the tenant about escalation**:
"I'm bringing in the property manager on this one because [reason]. They'll be in touch shortly."

**Telling the tenant without giving a reason** (legal/liability):
"This one needs the property manager's direct involvement. They'll reach out to you."

See `references/decision-logic/escalation-criteria.md`.

## Follow-Up After Resolution

**Same-day follow-up**:
"Hi [name], just checking in. Did the [vendor/repair] take care of the issue? If anything's still off, let me know."

**24-hour follow-up**:
"Hey [name], wanted to follow up on yesterday's repair. Everything working OK? If you notice anything else, don't hesitate to reach out."

**If issue recurred**:
"Sorry to hear it came back. Let me look into this and figure out a more permanent fix. I'll get back to you shortly."

## After-Hours / Emergency

**After-hours acknowledgment**:
"Hi [name], I got your message. I know it's after hours but I'm looking into this now."

**Emergency immediate**:
"I'm sending emergency [vendor type] right now. In the meantime, [immediate safety instruction]. They should be there within [timeframe]."

**Urgent but not Emergency after hours**:
"I've got this flagged as urgent. I'm working on getting someone out as soon as possible. I'll update you as soon as I have a confirmed time."
