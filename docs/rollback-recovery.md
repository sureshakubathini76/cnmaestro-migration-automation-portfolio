# Rollback and Recovery

## Rollback

Rollback is treated as its own guarded workflow, not simply the inverse of the last API request.

The workflow uses original pre-migration state and lineage so that restoration is based on a known-good source context.

## Partial Failure Recovery

When only part of a migration fails:

- successfully migrated devices remain untouched
- failed / incomplete devices are identified explicitly
- recovery creates a separate child workflow
- the failed subset is revalidated before another production attempt
- completed destructive steps are not intentionally repeated

## Resume / Checkpoint Behavior

For recoverable workflow states, the system preserves the last safe checkpoint and continues from that point after the underlying issue is corrected.

This is especially important for switch workflows where ownership, onboarding, synchronization, and configuration restore are separate stages.
