---
version: 1
---

# VAT implementation backlog

Tasks to bring VAT from spec to a working `cargo install`-able binary. Roughly ordered bottom-up: format primitives, then commands, then packaging.

- [vat-p9k] [in-progress] [by:jared] Publish vat to crates.io as vat-cli (binary stays vat) — packaging metadata, dual MIT/Apache license, publish workflow (see ./items/vat-p9k.md)
- [vat-72k] Write an in-depth blog post on what VAT is and why I built it (see ./items/vat-72k.md)
- [vat-h4n] [in-progress] [by:jared] [agent-ready] Relax project-ID prefix validation — allow any 3-char alphanumeric prefix, not just Crockford base32 (keep the suffix Crockford) (see ./items/vat-h4n.md)
---

Anything below this line is freeform notes and is not parsed by VAT.
