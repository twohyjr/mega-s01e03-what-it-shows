## Summary

**Cause:** `hint`  
**Reports covered:** 33 of 412 unique reports merged into support ticket #4471  
**Tenants:** 3 — `alder.physio`, `copper.studio`, `pale.harbour`  
**Seen:** 2026-04-17 → 2026-09-22  
**Channel:** form only (booking-v3)

## Problem

booking-v3 prints **`MM/DD/YYYY`** under the date field. Day-first tenants type what the hint shows (month first). The form then reads the value the **tenant's** day-first way. Month and day disagree — a different bug from the shared month-first parser.

## How we know

`causeOf` returns `hint` when the tenant is day-first, `channel === 'form'`, and the form's date hint starts with `MM` (booking-v3). That is **33** reports in the #4471 merge. The CauseTable marks them "not this ticket — no ticket of its own."

Intake tagged 18 as `hint` and 15 as `parser`. Cause follows tenant + channel, not the tag.

## Split from #4471

These were wrongly merged into the parser ticket. They need their own fix (form hint / read order), not the shared-parser queue item.
