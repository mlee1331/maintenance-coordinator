# Vendor Selection Rules

How to choose which vendor to dispatch for a given work order. The goal is to get the right person there at the right price within the required time window.

## General Principle

Prefer the cheapest qualified vendor who can respond within the required window. In practice, this means: handyman first for routine work, specialist when the job genuinely requires one.

## Vendor Hierarchy

For any given issue, evaluate vendors in this order:

### 1. Handyman (Preferred for Routine Work)

Handymen are cheaper than licensed specialists and can handle a wide range of common maintenance tasks. Use a handyman for:

- **Plumbing**: faucet repair/replacement, toilet internals (flapper, fill valve, handle), wax ring replacement, P-trap tightening/replacement, supply line replacement, garbage disposal swap, simple drain snaking at a single fixture
- **Electrical**: GFCI outlet replacement, outlet/switch swap, breaker identification and diagnosis, smoke detector replacement, exhaust fan replacement (existing wiring)
- **Appliances**: door latches, power supply troubleshooting, dryer vent cleaning, disposal replacement
- **General**: lock changes (non-emergency), door alignment, window hardware, screen replacement, caulking, minor drywall repair

### 2. Licensed Specialist (When the Job Requires It)

Use a licensed plumber, electrician, or HVAC tech when:

- **Plumber**: main line issues, water heater repair/replacement, pipe repair inside walls, sewer line work, backflow prevention, anything requiring permits
- **Electrician**: panel work, wiring repair, new circuit installation, repeated breaker trips with no clear cause, anything behind the dead front cover
- **HVAC technician**: system diagnosis and repair (furnace, heat pump, central AC), refrigerant work, compressor/motor replacement, ductwork
- **Appliance repair tech**: internal mechanical failures (compressor, motor, control board, sealed systems, gas valve solenoid)

### 3. Specialty Vendor (Specific Situations)

- **Locksmith**: emergency lockouts, rekeying, high-security locks
- **Pest control**: licensed pest control for chemical/heat treatment (not handyman)
- **Mold remediation company**: any mold or suspected mold escalates to a human first (see `escalation-criteria.md`) — do not auto-dispatch, including handyman surface cleaning. The human decides the vendor; a remediation company is used for larger areas (over ~10 sq ft) or porous surfaces
- **Glass company**: window glass replacement, sealed unit (double-pane) failures
- **Wildlife removal**: raccoons, bats, squirrels (separate from pest control)
- **Dryer vent cleaning service**: dedicated vent cleaning with specialized equipment
- **Garage door company**: garage door springs, cables, openers, off-track or broken doors. High-tension spring and cable work is a safety job beyond handyman scope — dispatch a dedicated garage door company. A handyman may handle a loose panel, weather seal, or a remote/battery swap.
- **Landscaping / grounds**: lawn mowing, overgrowth, tree and shrub trimming, leaf and debris removal, seasonal cleanup, and snow removal where applicable. Use for routine grounds upkeep, not for irrigation/sprinkler plumbing (that is a plumber) or exterior structural work.
- **Roofing company**: roof leaks, missing/lifted/damaged shingles or tiles, flashing, and roof-tied gutters. Roof work is a licensed specialty and is not a handyman job; it frequently exceeds NTE, so get owner approval per `owner-approval-rules.md` unless an active leak makes it an emergency.

## Selection Within a Category

When multiple vendors of the same type are available, select based on:

1. **Availability**: can they respond within the required window? If the issue is Medium severity or higher and vendor A can come today but vendor B can't come until Thursday, send vendor A.
2. **Property assignment**: some companies assign specific vendors to specific properties or areas. Check the vendor list in config.
3. **Performance history**: if the company tracks vendor performance (response time, first-visit fix rate, tenant feedback), prefer higher-performing vendors for standard dispatch.
4. **Specialty match**: does the vendor have experience with the specific issue? (e.g., a plumber who specializes in water heaters for a water heater replacement)

## Emergency vs. Standard Dispatch

### Emergency Dispatch

For Critical and High severity issues:

- Use the company's designated emergency vendor for that trade. This is configured during onboarding.
- Emergency vendors are often more expensive (after-hours rates, priority fees). That's acceptable for emergencies.
- Do not wait for NTE approval on Critical (life-safety) issues. Dispatch and notify the PM.
- For High severity (habitability) issues, check whether the NTE threshold covers the likely cost. If it does, dispatch. If it might not, dispatch anyway and flag for PM.

### Standard Dispatch

For Low and Cosmetic severity issues:

- Use the preferred vendor for that trade and property.
- Schedule within the response window from `habitability-response-windows.md` if applicable.
- Confirm the NTE covers the expected scope before dispatching.

## NTE (Not-to-Exceed) Considerations

Before dispatching, check the company's NTE threshold (configured during onboarding):

- If the expected repair cost is within NTE: dispatch without owner approval
- If the expected cost might exceed NTE: dispatch but flag in the work order that owner approval may be needed before the vendor proceeds with the full repair
- If the issue is clearly going to exceed NTE (e.g., water heater replacement, major HVAC repair): get owner approval before dispatching unless it's Critical or High severity

See `owner-approval-rules.md` for the full approval workflow.

## What to Include in the Dispatch

Every dispatch should include:

- Complete work order with all fields from the KB entry's "Work order fields to capture" section
- Severity level and any response window deadline
- NTE threshold and whether pre-approval is needed
- Tenant contact information and availability
- Access instructions (lockbox code, key location, gate code)
- Whether pets are in the unit
- Any relevant photos from intake

## Vendor Not Available

If no vendor of the right type is available within the required window:

1. Check if a different vendor type can handle it (handyman instead of plumber for simple work)
2. Expand the search radius if the company has vendors in adjacent areas
3. Escalate to PM if no vendor can be found within the required window
4. For High severity (habitability) issues: escalate immediately. The clock is running.
