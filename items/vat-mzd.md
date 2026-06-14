---
id: vat-mzd
---

The pointer-suffix step of `vat sync` is unimplemented: the EARS are written but marked [ ] in docs/specs/sync-specs.md, and there is no logic in src/sync.rs. As a result `vat sync` extracts notes into items/<id>.md but never links the bullet to them.
SYNC-PTR-001: when a bullet's id has a corresponding backlog/items/<id>.md, ensure the title ends with the literal suffix ` (see ./items/<id>.md)` (single leading space, path relative to backlog/), appending if absent.
SYNC-PTR-002: when there is no item file for the id, do not add the suffix and do not strip an existing one.
SYNC-PTR-003: when the suffix is already present and the item file exists, leave it unchanged (idempotent on re-sync).
Surfaced while dogfooding `vat sync` on the real backlog — vat-72k got an item file but no pointer suffix, so it had to be added by hand. Explicitly deferred out of vat-v3k's scope.
