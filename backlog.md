---
version: 1
---

# VAT implementation backlog

Tasks to bring VAT from spec to a working `cargo install`-able binary. Roughly ordered bottom-up: format primitives, then commands, then packaging.

- [vat-s3p] [in-progress] [by:jared] Add remote repo detection to the VAT skill that just teaches agent that remote backlog repos are a possibility more than anything
- [vat-x8n] [agent-ready] `vat block <id> <blocker-id>` command (see ./items/vat-x8n.md)
- [vat-y2p] [agent-ready] `vat unblock <id>` command (see ./items/vat-y2p.md)
- [vat-z4q] [agent-ready] `vat done <id>` command (see ./items/vat-z4q.md)
- [vat-m2k] [agent-ready] [blocked-by:vat-z4q] Create a shared single-bullet-replace serialize helper and adopt across vat start/block/unblock/done (see ./items/vat-m2k.md)
- [vat-d3t] [agent-ready] Snapshot / golden-file tests for sync (see ./items/vat-d3t.md)
- [vat-f7v] [agent-ready] [blocked-by:vat-z4q] Snapshot tests for the other commands (see ./items/vat-f7v.md)
- [vat-g4w] [agent-ready] [blocked-by:vat-z4q] End-to-end CLI tests (see ./items/vat-g4w.md)
- [vat-j5z] [agent-ready] [blocked-by:vat-g4w] Release packaging (see ./items/vat-j5z.md)

---

Anything below this line is freeform notes and is not parsed by VAT.
