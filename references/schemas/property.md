# Property Schema

Information about a managed property. Properties are populated during onboarding (config.yaml) or added on the fly when a work order comes in for an unknown property.

Not every harness or PM software will track all of these. Use what's available. The coordinator can function with just an address and a jurisdiction. Everything else makes it faster and reduces back-and-forth with tenants and vendors.

## Fields

### Identification

- **property_id**: Unique identifier. Could be an address, a code from the PM software, or whatever the harness uses. If none exists, the coordinator uses the street address.
- **address**: Full street address.
- **city**: City.
- **state**: Two-letter state code. Used for jurisdiction/habitability lookups.
- **zip**: ZIP code.
- **unit_count**: Number of units. 1 for single-family. Helps the coordinator understand whether an issue might affect multiple tenants.
- **property_type**: single_family, duplex, triplex, fourplex, apartment, condo, townhouse. Informational. Some issues (roof, sewer) behave differently in multi-unit buildings.

### Jurisdiction

- **jurisdiction_state**: Usually matches the state field. Pulled out separately because this is what drives habitability law lookups.
- **jurisdiction_city**: Only needed if the city has local ordinances stricter than state law. Set during onboarding or when the coordinator discovers a local override.
- **local_ordinance_notes**: Free text notes on anything jurisdiction-specific for this property (stricter AC requirements, local mold disclosure rules, etc.).

### Access

- **lockbox_code**: If the property uses a lockbox for vendor access.
- **gate_code**: Gated community or building gate code.
- **key_location**: Where a spare key is kept, if applicable.
- **parking_notes**: Where vendors should park, especially for properties with limited or restricted parking.
- **general_access_notes**: Anything else a vendor needs to know to get in (security desk, call tenant first, side entrance, etc.).

### Owner

- **owner_name**: Name of the property owner. Used for approval workflows.
- **owner_phone**: Owner phone.
- **owner_email**: Owner email.
- **owner_preferred_contact**: How the owner prefers to be reached for approval requests.
- **preferred_vendors**: List of vendor names or IDs the owner requires for this property. Overrides the default vendor selection.
- **refused_vendors**: List of vendor names or IDs the owner does not want used at this property.
- **owner_nte_override**: If this owner has a different NTE than the company default, note it here.

### Notes

- **property_notes**: Anything else relevant. Known issues ("unit 3 has old galvanized pipes, expect plumbing calls"), recurring problems ("Building B has a history of roof leaks on the east side"), or quirks ("tenant in 2A works nights, don't schedule before noon").

## What's Required

The coordinator needs at minimum:

- Some way to identify the property (address or ID)
- jurisdiction_state (for habitability lookups)

Everything else is helpful but optional. If access instructions aren't in the config, the coordinator asks the tenant at dispatch time. If owner info isn't stored, the coordinator escalates to the PM for approval situations.
