# Migration Workflow

## Configuration Migration

1. Discover source configuration.
2. Resolve dependencies and conflicts.
3. Run Dry Run validation.
4. Simulate execution without production changes.
5. Execute the approved migration.
6. Verify destination configuration.

Typical configuration areas include networks, sites, AP groups, WLAN profiles, access-control related objects, switch groups, and templates.

## Access Point Migration

A guarded AP workflow follows the pattern:

**Backup → Dry Run Validate → Dry Run Execute → Actual Migration → Verify Cloud**

The design checks source state, onboarding/readiness, destination prerequisites, group placement, and final cloud presence.

## Switch Migration

Switch migration adds additional safeguards for:

- source release / ownership transition
- destination onboarding
- switch-group placement
- configuration synchronization
- port configuration restoration
- post-migration validation

Port restoration is gated on healthy synchronization rather than performed immediately after the device first appears in the destination.
