# Vendor Schema

Information about a maintenance vendor. Vendors are added during onboarding (config.yaml) and can be updated as the coordinator learns more about vendor performance and availability.

## Fields

### Identification

- **vendor_id**: Unique identifier. Could be a name, a code from the PM software, or auto-generated. If the harness doesn't generate IDs, the coordinator uses the vendor name.
- **name**: Vendor's business or personal name.
- **phone**: Primary phone number.
- **email**: Email address, if they use email.
- **contact_method**: How the vendor prefers to receive dispatch requests (phone, text, email, app). Important because sending an email to a vendor who only checks texts means a delayed response.

### Trade

- **category**: Primary trade category. One of: handyman, plumber, electrician, hvac, locksmith, pest_control, mold_remediation, glass, garage_door, roofing, wildlife_removal, dryer_vent_cleaning, appliance_repair, landscaping, general. A vendor can have multiple categories (a handyman who also does basic plumbing).
- **additional_categories**: Other trades this vendor can handle, if applicable.
- **specialties**: Free text. Specific things this vendor is known for ("water heater installs", "commercial HVAC", "older building plumbing"). Helps with matching.
- **limitations**: Things this vendor doesn't handle despite their category. "Plumber but doesn't do sewer lines." "Electrician but won't touch panels over 200A."

### Coverage and Availability

- **coverage**: Which properties this vendor serves. "all" for all properties, or a list of specific property addresses/IDs.
- **service_area**: Geographic description if relevant ("north side only", "within 30 miles of downtown").
- **emergency_available**: Whether this vendor takes after-hours and emergency calls (true/false).
- **emergency_phone**: Separate phone for emergencies, if different from primary.
- **typical_response_time**: How quickly this vendor usually responds to a dispatch request. Free text ("same day", "within 2 hours for emergencies", "next business day"). Informational, not a guarantee.

### Owner Preferences

- **required_by_owners**: List of owner names or property IDs where this vendor is required. Some owners insist on specific vendors.
- **refused_by_owners**: List of owner names or property IDs where this vendor is not allowed.

### Performance (If Tracked)

These are optional. Not every system will track vendor performance, and even when tracked, the data comes in over time from completed work orders.

- **jobs_completed**: Total number of work orders completed.
- **on_time_rate**: Percentage of jobs where the vendor arrived within the scheduled window.
- **first_visit_fix_rate**: Percentage of jobs resolved on the first visit.
- **average_tenant_rating**: Average tenant satisfaction score, if collected.
- **notes**: Free text performance notes. "Fast but expensive." "Great with tenants, sometimes late." "Doesn't clean up after work."

### Financial

- **typical_rate**: General rate information, if known. Free text ("charges a flat service call fee plus parts", "hourly rate"). Don't store specific dollar amounts here since rates change. This is just context for the coordinator when estimating whether a job will be within NTE.
- **accepts_nte**: Whether this vendor works within NTE constraints or requires a full quote before starting (true/false). Most do, some don't.

## What's Required

To dispatch a vendor, the coordinator needs:

- name
- At least one contact method (phone or email)
- category (what trade they cover)

Everything else helps the coordinator make better decisions (choosing the right vendor, routing emergencies, respecting owner preferences), but the coordinator can dispatch with just a name, phone number, and trade.
