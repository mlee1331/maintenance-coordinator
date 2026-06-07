# Owner Schema

Information about a property owner. In many PM setups, owner info lives in the PM software and the coordinator only needs it when an approval decision comes up. Some harnesses won't have owner records at all, and the coordinator just escalates to the PM who handles owner communication. That's fine.

## Fields

### Identification

- **owner_id**: Unique identifier from the PM software, if available.
- **name**: Owner's full name or entity name.
- **phone**: Primary phone number.
- **email**: Email address.
- **preferred_contact**: How they prefer to be reached for approval requests (phone, text, email). Matters when the coordinator is trying to get a quick approval on a habitability repair.

### Properties

- **properties**: List of property addresses or IDs this owner owns. Links to the property schema.

### Approval Preferences

- **nte_override**: If this owner has a different NTE threshold than the company default, note it here. Overrides the global NTE from config for this owner's properties.
- **pre_approved_categories**: Repair categories this owner has blanket-approved (e.g., "all plumbing under NTE", "smoke detector replacement"). The coordinator can dispatch these without asking.
- **approval_response_pattern**: Informational. How responsive this owner typically is. "Usually responds within an hour." "Often takes 24+ hours, may need follow-up." Helps the coordinator decide when to escalate vs. wait.

### Vendor Preferences

- **preferred_vendors**: Vendors this owner wants used at their properties. Overrides the default vendor selection. List of vendor names or IDs.
- **refused_vendors**: Vendors this owner does not want at their properties. The coordinator should never dispatch these.

### Notes

- **notes**: Free text. Anything relevant to working with this owner. "Wants to be called, not texted, for anything over NTE." "Very cost-conscious, always wants repair over replacement." "Responsive on weekdays, unreachable on weekends." "Owns 3 other buildings managed by a different company, sometimes confuses which PM handles what."

## What's Required

The coordinator can function without any owner records. When an approval is needed and owner info isn't in the system, the coordinator escalates to the PM, who handles the owner communication.

If owner records are available, the useful minimum is:

- name
- At least one contact method
- Which properties they own

Everything else is context that helps the coordinator get approvals faster and respect owner preferences.

## Relationship to Config

Owner information can live in two places:

1. Inside each property's config entry (the `owner` block under each property in config.yaml)
2. As standalone owner records in the PM software, linked to properties

Either works. The coordinator checks both. If there's a conflict, the PM software is probably more current than the config file, but the coordinator should flag the discrepancy rather than guessing.
