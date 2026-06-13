---
version: 1
---

# VAT implementation backlog

Tasks to bring VAT from spec to a working `cargo install`-able binary. Roughly ordered bottom-up: format primitives, then commands, then packaging.

- Make the "/vat" skill default to using the vat binary if it's installed. If it's not installed, it just does what it does today
- [vat-p9k] [in-progress] [by:jared] Publish vat to crates.io as vat-cli (binary stays vat) — packaging metadata, dual MIT/Apache license, publish workflow (see ./items/vat-p9k.md)

---

Anything below this line is freeform notes and is not parsed by VAT.
