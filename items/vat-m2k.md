---
id: vat-m2k
---

Surfaced by review of PR #48 (vat-w5m). `cmd_start.rs` carries a private serialize helper (essentially "re-serialize the parsed region with one bullet replaced") that `block`, `unblock`, and `done` (vat-x8n, vat-y2p, vat-z4q) will each duplicate verbatim.

Note: vat-v3k did NOT centralize this. Its sync path serializes bullets inline because sync entries hold borrowed `&str`, not parsed `Bullet` structs — so there is no existing shared API to adopt. This task therefore CREATES the shared single-bullet-replace helper and adopts it across `vat start/block/unblock/done`, removing the per-command duplicates.

Keep behavior identical; this is a dedup refactor, not a behavior change. Blocked-by vat-z4q so all four sibling commands exist before consolidating their duplicated helpers.
