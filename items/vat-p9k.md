---
id: vat-p9k
---

Make VAT installable via `cargo install vat-cli`. The bare `vat` crate name is taken on crates.io (an EU VAT-number crate), so the package is published as `vat-cli` while the binary stays `vat` via `[[bin]]`.

Scope:
- Cargo.toml: rename package to `vat-cli`, add `[[bin]] name = "vat"`, add crates.io-required metadata (description, license = "MIT OR Apache-2.0", repository, readme, keywords, categories, rust-version), and `exclude` dev-only paths from the published crate.
- LICENSE-MIT + LICENSE-APACHE (dual-license pair).
- README install section: lead with `cargo install vat-cli`, keep `--git` for unreleased main, add a License section.
- release.yml: a `publish-crate` job running `cargo publish` on a version tag, gated on the `CARGO_REGISTRY_TOKEN` secret (skips cleanly if unset).

Implemented in jmbeach/vat PR #60.

Remaining human steps (publishing is irreversible): add the `CARGO_REGISTRY_TOKEN` repo secret, then cut the first publish via a `v*` tag or `cargo publish` after `cargo login`.
