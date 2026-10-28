## Summary

**Cause:** `parser`  
**Reports covered:** 379 of 412 unique reports merged into support ticket #4471  
**Tenants:** 11  
**Seen:** 2026-04-01 → 2026-10-04

## Problem

The shared date parser reads every date **month first**. Day-first tenants (all tenants in this export) send dates day-first through app, email, or booking-v2 form. Those dates come out with month and day swapped.

## How we know

`causeOf` in the kb (`src/lib/kb/causes.ts`) assigns `parser` when the tenant is day-first and the report is **not** the booking-v3 form+hint case. Against `reports-4471.json` + tenant files, that is **379** reports.

Intake `meta.intakeTag` often says `parser` too (356) but also mis-tags 23 as `hint`. The cause follows the tenant, not the tag.

## Not this ticket

33 reports under cause `hint` (booking-v3 form channel) are a different bug — see the sibling issue.

Five desk-notes `oneDayMove` ids were read as a one-day shift; by tenant they still belong under **parser**.
