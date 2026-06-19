---
id: vat-h4n
---

Bug: the 3-character project-ID prefix is validated against the Crockford base32 alphabet — the same `base32::validate()` used for the auto-generated 3-char suffix — applied via `ProjectConfig` at `src/cmd_init.rs` (CMD-INIT-004) and `src/cmd_config.rs` (`vat config set project.id`).

The Crockford restriction (forbids the ambiguous chars i/l/o/u, and any non-base32 char) is appropriate for the RANDOM SUFFIX, where avoiding visually ambiguous characters aids readability. But the prefix is user-chosen ONCE and never changes, so that rationale does not apply — and the restriction needlessly rejects natural choices like `lib`, `ui`, `io`, `sql` (which contain l/i/o/u).

Fix: relax PREFIX validation to accept any 3-character ASCII alphanumeric string — letters a–z (case-insensitive, stored lowercase as today) plus digits 0–9 — while still forbidding the `-` separator, whitespace, and bracket characters so `[<prefix>-<suffix>]` ID tokens still parse. Keep the SUFFIX generation and validation on the existing Crockford `base32::validate()` UNCHANGED. Length stays exactly 3.

Open decision (note rationale in the commit): letters-only vs alphanumeric for the prefix. Recommendation: alphanumeric (matches the request's "maybe even numeric"); both remain 3 chars and parse-safe.

Touch points:
- Add a distinct prefix validator; do NOT reuse `base32::validate` for the prefix.
- Update `cmd_init.rs` (CMD-INIT-004) and `cmd_config.rs` (`config set project.id`) and `ProjectConfig` to use it; leave `base32::validate` for the suffix.
- Update the EARS spec(s) stating the project.id charset, the LLD, and the tests that currently assert Crockford rejection of the prefix (cmd_config/cmd_init).
- Coherence: the `/vat` skill prose (`.claude/skills/vat/SKILL.md`) and any README/CLAUDE text that say "project.id is 3-char Crockford base32" must be updated to the relaxed prefix rule (same change or a noted follow-up).
