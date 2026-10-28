# mega-s01e03-what-it-shows

Public deliverable for [MEGA.dev S01E03 · what it shows](https://hq.mega.dev/challenges/what-it-shows).

Support desk ticket **#4471** merged 412 date reports and marked them known as one parser bug. The kb export’s own cause logic shows **two** causes. This repo holds:

1. **GitHub issues** — one ticket per cause, with report counts
2. **kb page** — `kb/support-kb/src/routes/kb/incidents/4471-split/+page.svx` (signed)
3. **Rendered page** — `rendered/4471-split.html` (how the desk sees it)

| Cause | Reports | Issue |
|-------|---------|-------|
| parser | 379 | shared parser reads month-first for day-first tenants |
| hint | 33 | booking-v3 form hint says MM/DD; form reads day-first |

Source kb export unpacked under `kb/support-kb/`.
