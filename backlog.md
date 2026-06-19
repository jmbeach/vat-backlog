---
version: 1
---

# VAT implementation backlog

Tasks to bring VAT from spec to a working `cargo install`-able binary. Roughly ordered bottom-up: format primitives, then commands, then packaging.

- [vat-46x] [in-progress] [by:jared] [agent-ready] Make the "/vat" skill default to using the vat binary if it's installed. If it's not installed, it just does what it does today
- [vat-p9k] [in-progress] [by:jared] Publish vat to crates.io as vat-cli (binary stays vat) — packaging metadata, dual MIT/Apache license, publish workflow (see ./items/vat-p9k.md)
- [vat-72k] Write an in-depth blog post on what VAT is and why I built it (see ./items/vat-72k.md)
- [vat-mzd] [in-progress] [by:jared] [agent-ready] Wire `vat sync` to append the `(see ./items/<id>.md)` pointer suffix — implement SYNC-PTR-001..003 (see ./items/vat-mzd.md)
- [vat-h4n] [in-progress] [by:jared] [agent-ready] Relax project-ID prefix validation — allow any 3-char alphanumeric prefix, not just Crockford base32 (keep the suffix Crockford) (see ./items/vat-h4n.md)
---

Anything below this line is freeform notes and is not parsed by VAT.
