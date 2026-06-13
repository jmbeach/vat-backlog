---
version: 1
---

# VAT implementation backlog

Tasks to bring VAT from spec to a working `cargo install`-able binary. Roughly ordered bottom-up: format primitives, then commands, then packaging.

- [vat-x8n] [in-progress] [by:jared] [agent-ready] `vat block <id> <blocker-id>` command (see ./items/vat-x8n.md)
- [vat-y2p] [in-progress] [by:jared] [agent-ready] `vat unblock <id>` command (see ./items/vat-y2p.md)
- [vat-m2k] [agent-ready] Consolidate duplicated command-module code across vat start/block/unblock/done — shared single-bullet-replace serialize helper, shared test helpers, backlog-path constant (see ./items/vat-m2k.md)
- [vat-d3t] [agent-ready] Snapshot / golden-file tests for sync (see ./items/vat-d3t.md)
- [vat-f7v] [agent-ready] Snapshot tests for the other commands (see ./items/vat-f7v.md)
- [vat-g4w] [agent-ready] End-to-end CLI tests (see ./items/vat-g4w.md)
- [vat-j5z] [agent-ready] [blocked-by:vat-g4w] Release packaging (see ./items/vat-j5z.md)

---

Anything below this line is freeform notes and is not parsed by VAT.
