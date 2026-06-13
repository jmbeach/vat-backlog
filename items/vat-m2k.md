---
id: vat-m2k
---

Surfaced by review of PR #48 (vat-w5m). `cmd_start.rs` carries a private serialize helper that is essentially `ParsedRegion::serialize` with one bullet replaced — and `block`, `unblock`, and `done` (vat-x8n, vat-y2p, vat-z4q) will each duplicate it verbatim.

Once vat-v3k lands the canonical `ParsedRegion::serialize` (marker normalization + write), extract a single shared single-bullet-replace helper and adopt it across `vat start/block/unblock/done`, removing the per-command duplicates. Keep behavior identical; this is a dedup refactor, not a behavior change. Blocked-by vat-v3k because it depends on that shared serialize API existing.
