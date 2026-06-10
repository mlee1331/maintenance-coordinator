# Setup Interview

This interview is optional. The agent works out of the box using the defaults in `assets/config.defaults.yaml`. Property managers who want to jump in and start handling work orders immediately can skip this entirely and customize later.

Run this interview when the PM asks to configure the agent, when they say "run setup" or "let's set this up," or when they want to change multiple settings at once. The PM can also change any individual setting at any time by just telling the agent what to change, without running the full interview.

## How to Run the Interview

Walk through the sections below in order. Ask one question at a time. Be conversational, not robotic. Explain why you're asking when it's not obvious. Confirm each answer before moving on. If the person doesn't know an answer, note it as incomplete and move on. You can come back to incomplete fields later.

For several sections (properties, vendors, tenant responsibility), the person may already have this information in reports, spreadsheets, or documents from their property management software. Always offer the option to upload a file instead of answering questions one by one. If they upload a report, parse it, extract the relevant fields, confirm what you found, and ask about anything that's missing.

At the end, summarize everything back and ask for confirmation. Then write the answers to `assets/config.yaml`.

If the person has already filled out `assets/config.template.yaml` manually, validate it against the required fields below and only ask about anything that's missing.

## Section 1: Company Basics

These identify who the agent is working for.

**Ask:**

1. What's the name of your property management company?
2. What's the best phone number and email for your company? (This is what tenants will see as the "from" when the agent contacts them.)
3. Who should the agent notify when something needs human attention? Give me a name, phone number, and email for your primary coordinator or on-call manager.

**Why this matters:** The agent needs to know who it represents, how to identify itself to tenants, and who to escalate to.

## Section 2: Properties

The agent needs to know what properties it's coordinating maintenance for.

**Ask:**

1. Do you want to add your properties now, or would you rather the agent handle all incoming work orders by default and you add specific property details later?

**If they want to add properties now:**

2. Do you have a property list, portfolio report, or spreadsheet you can upload? Most PM software can export this. The agent will parse it and pull out addresses, unit counts, and jurisdictions.
3. If no upload: How many properties will the agent handle? For each property, what's the address, how many units, and what city and state is it in?
4. Are there any properties with special access instructions? (Lockbox codes, gate codes, pet warnings, parking restrictions, anything the vendor needs to know before arriving.)

**If they want to skip for now**, that's fine. By default the agent manages all properties. When a work order comes in for a property not in the config, the agent will handle it normally but will need to ask for jurisdiction and access details at that time. They can come back and add property details later to avoid those extra questions on every new property.

**Either way, ask:**

5. What state (or states) are most of your properties in? (The agent needs at least a default jurisdiction to look up habitability law. If all properties are in one state, one answer covers it.)

**Why this matters:** Jurisdiction determines which habitability laws apply. Access instructions prevent failed vendor visits. But neither should be a blocker to getting started.

## Section 3: Jurisdiction and Legal

These questions determine which laws the agent follows for habitability response windows, tenant rights, and required disclosures.

**Ask:**

1. I'll use the state for each property to look up habitability response windows and tenant rights. Are any of your properties in cities or counties that have local ordinances stricter than the state? (For example, some cities have their own AC habitability rules, rent escrow procedures, or required response timeframes that are tighter than the state.)
2. Do you operate under any specific local housing authority rules or affordable housing program requirements that affect maintenance response?

**If they don't know**, that's OK. Note it as needing review. The agent will default to state-level rules, which is the safe baseline. But flag it so they can research local ordinances later.

## Section 4: Emergency and Lockout Policy

These are company-specific decisions that the law doesn't fully dictate.

**Ask:**

1. What's your lockout policy? Some companies treat all lockouts as emergencies. Others treat after-hours lockouts as emergencies and daytime lockouts as urgent. Some only dispatch a locksmith after hours if the tenant has no other safe option. What's your approach?
2. Do you have a preferred locksmith or after-hours emergency service for lockouts?
3. Is there anything else your company always treats as an emergency that might not be obvious? (Some companies treat any pest sighting as an emergency. Some treat any water on the floor as an emergency regardless of source.)

**Why this matters:** The emergency classification file defers lockout and some other edge cases to company policy. This is where that policy gets set.

## Section 5: Not-To-Exceed (NTE) Thresholds

NTE is the dollar amount the agent can authorize a vendor to spend without getting explicit owner approval first.

**Ask:**

1. Do you use a single NTE threshold across all properties, or does it vary by property or owner?
2. What's the default NTE? (Common range is $200-$500 for standard work.)
3. Is there a separate, higher NTE for emergencies? (Many companies allow up to $1,000-$2,500 for Emergency severity situations without owner approval.)
4. For Emergency severity situations, should the agent dispatch even if the cost exceeds the emergency NTE and the owner is unreachable? (Recommended: yes, with documentation.)

**Why this matters:** Dispatching above NTE without approval is a serious problem for owner relationships. Not dispatching during an emergency because the owner didn't pick up the phone is a serious problem for tenants and potentially a legal problem for the company.

## Section 6: Vendors

The agent needs to know who to call.

**Ask:**

1. Do you have a vendor list you can upload? A spreadsheet, a report from your PM software, or even a document with names and phone numbers by trade. If so, upload it and the agent will parse it.
2. If no upload: at minimum, I need at least one vendor for each of these categories to handle emergencies. Can you give me a name and phone number for each?
   - Plumber (or plumbing company)
   - Electrician
   - HVAC technician
   - General handyman
   - Locksmith
3. For each vendor: what area do they cover? All your properties, or specific ones?
4. Are there any vendors that specific owners require or refuse to use? (Owner overrides.)
5. Do any of your vendors have preferred contact methods? (Some vendors want a text, some want a call, some use an app.)

**If they don't have a full vendor list yet**, that's fine for onboarding. Get at minimum one plumber, one electrician, one HVAC tech, and one locksmith. The agent can't handle emergencies without at least those four. Other categories can be added later.

**Why this matters:** The agent cannot dispatch if it doesn't know who to dispatch to. Missing a critical vendor category means the agent will have to escalate every issue in that category to a human, which defeats the purpose.

## Section 7: Troubleshooting Aggressiveness

How hard should the agent try to resolve issues with the tenant before sending a vendor?

**Explain the scale briefly:**

- Level 0: never troubleshoot, dispatch immediately
- Level 1: one or two quick questions, then dispatch
- Level 2: light troubleshooting (resets, simple checks, under 5 minutes)
- Level 3: full standard troubleshooting (default, 10-15 minutes)
- Level 4: thorough diagnostics (video, multi-step, 20-30 minutes)
- Level 5: maximum (guided repairs, shipped parts, 30+ minutes)

**Ask:**

1. Which level sounds right for your operation? If you're not sure, Level 3 is the default and works for most standard residential portfolios.
2. Should the level be the same across all properties, or do some properties need a different level? (Luxury properties might be Level 0-1. Cost-sensitive portfolios might be Level 4-5.)

**Why this matters:** This is the single biggest lever on maintenance spend vs. tenant experience. Getting it right matters.

## Section 8: Communication Preferences

How does the agent talk to tenants?

**Ask:**

1. How do tenants currently submit maintenance requests? (Text/SMS, email, tenant portal, phone call, in person, some combination.)
2. How should the agent communicate back? (Same channel, always text, always email, whatever the tenant used.)
3. Do you have a preferred tone? (Friendly and casual? Professional and formal? Somewhere in between?) If you're not sure, the default is warm, direct, and plain-spoken.
4. Is there anything the agent should always say or never say? (Some companies always include their company name. Some have legal language they want in every dispatch confirmation. Some never want the agent to say "sorry" because they think it implies liability.)

## Section 9: Tenant Responsibility

**Ask:**

1. Do you have a standard lease or lease template you can upload? The agent can read the maintenance responsibility clauses and extract what's tenant-responsible vs. owner-responsible. This is usually faster and more accurate than going through a list.
2. If no upload: do your leases generally require tenants to handle any of the following? (Go through the list, confirm each.)
   - Replacing light bulbs
   - Replacing smoke detector batteries
   - Replacing HVAC filters
   - Clearing minor drain clogs
   - Pest prevention (cleanliness-related)
   - Lawn care or snow removal
3. Is there a standard lease clause you use, or does it vary by property?
4. When a tenant disputes responsibility, what's your current process? (The default in this skill is: inform once, if disputed, escalate to a human. Do you want the agent to do anything differently?)

**Why this matters:** The tenant responsibility matrix is one of the most common sources of friction. Getting the company's actual policy in writing prevents the agent from making up answers.

## Section 10: Anything Else

**Ask:**

1. Is there anything else about how you run maintenance that I should know? Quirks, special procedures, things that have gone wrong in the past that you want to make sure don't happen again?
2. Do you want me to start handling work orders right away after setup, or do you want to run some test scenarios first?

**Recommend testing.** Point them to `evals/` for test cases they can run to see how the agent handles common scenarios before going live.

## After the Interview

1. Summarize all answers back to the person. Group by section.
2. Call out any fields they skipped and explain what the agent will do without them (use the default, ask on the fly, or escalate to a human, depending on the field).
3. Ask for confirmation.
4. Write structured settings to `assets/config.yaml`. Only write fields the PM explicitly set. Anything they didn't specify stays out of the file and falls back to `config.defaults.yaml`.
5. Write any plain-English rules to `custom/rules.md` (not config.yaml). This includes the Section 10 "quirks/special procedures" answer, the Section 4 "anything else you always treat as an emergency" answer, and any "always/never" behavioral instructions. Create the file if it doesn't exist; append if it does.
6. Tell the person they can change anything at any time: edit `assets/config.yaml` (settings) or `custom/rules.md` (rules) directly, tell the agent what to change in conversation, or re-run this interview.

## What Has Defaults vs. What Doesn't

Everything has a default in `assets/config.defaults.yaml`. The agent can start handling work orders with zero configuration. But some things work much better when configured:

**High-value to configure early** (the agent works without these, but with friction):

- Vendor list (without it, the agent asks the PM for a vendor at every dispatch)
- Escalation contact (without it, the agent flags issues in the work order but can't notify anyone)
- Default jurisdiction (without it, the agent asks the tenant what state they're in on every new property)

**Nice to configure but the defaults are solid:**

- NTE threshold (defaults to $500/work order, $1,500 for emergencies)
- Lockout policy (defaults to after-hours emergency)
- Troubleshooting aggressiveness (defaults to Level 3)
- Communication tone (defaults to warm and direct)
- Tenant responsibility (defaults to industry standard)

**Fine to skip entirely:**

- Individual property details (agent manages all properties, asks per work order as needed)
- Owner-specific vendor preferences (defaults to standard selection rules)
- Property access instructions (agent asks the tenant at dispatch time)
- Custom emergency rules, business hours, languages

The PM can fill in any of these at any time. There's no deadline and no "you must complete setup before proceeding." The agent adapts.
