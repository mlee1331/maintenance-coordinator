# Tenant Schema

Information about a tenant. In many setups, the coordinator won't have a persistent tenant record at all. It will just know the tenant's name and contact info from the incoming maintenance request. That's fine. This schema describes what's useful to track if the system supports it.

## Fields

### Identification

- **tenant_id**: Unique identifier from the PM software, if available.
- **name**: Tenant's full name.
- **phone**: Primary phone number.
- **email**: Email address.
- **preferred_contact**: How they prefer to be reached (text, email, phone, portal). If unknown, default to however they submitted the request.
- **preferred_language**: Language preference (e.g., "en", "es"). Default is English. If the tenant communicates in another language and the coordinator can match it, do so.

### Residence

- **property_address**: Where they live.
- **unit**: Unit number or identifier.
- **lease_start**: When the lease started. Useful for context but rarely needed during triage.
- **lease_end**: When the lease ends. Occasionally relevant if the tenant is moving out soon and the repair urgency changes.

### Maintenance History

- **previous_work_orders**: List of past work order IDs for this tenant, if tracked. Useful for spotting patterns (same issue three times in 90 days triggers escalation per `references/decision-logic/escalation-criteria.md`).
- **notes**: Free text. Anything relevant to future interactions. "Tenant works nights, prefers afternoon scheduling." "Tenant has a large dog, warn vendors." "Tenant is hard of hearing, prefers text over phone."

### Accessibility

- **accessibility_needs**: Any disability or accommodation needs related to maintenance. If present, escalate per `references/decision-logic/escalation-criteria.md`. The coordinator should not try to handle ADA/accessibility requests independently.

## What's Required

The coordinator needs:

- name (or at least some way to address them)
- At least one contact method (phone, email, or portal handle)

Everything else is bonus context. Many harnesses will only have name and phone from the incoming message, and that's enough to run the full workflow.
