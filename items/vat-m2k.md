---
id: vat-m2k
---

Surfaced by review of PRs #48/#52/#53/#54 (the vat start/unblock/block/done commands). Each command module independently duplicates the same scaffolding:

- **Serialize helper**: `serialize_region_with_replaced_bullet` (re-serialize the parsed region with one bullet replaced) currently lives `pub(crate)` in `cmd_start.rs` — a command-specific home for a general bullet-mutation utility.
- **Test helpers**: `make_backlog_dir`, `write_backlog`, `read_backlog`, and `HEADER` are copy-pasted byte-for-byte across the command test modules.
- **Backlog-path constant**: `Path::new("backlog")` is constructed at ~5 separate sites in `main.rs` with no shared constant.

Note: vat-v3k did NOT centralize the serialize path (its sync code serializes inline because sync entries hold borrowed `&str`, not parsed `Bullet` structs). So this task CREATES the shared homes and adopts them across all four commands.

Scope: move the serialize helper to a shared module (e.g. alongside `Bullet`/`ParsedRegion`), extract the duplicated test helpers into one shared test-support module, and introduce a single backlog-path constant. Behavior-preserving dedup, not a behavior change. Blocked-by vat-z4q so all four sibling commands exist before consolidating.
