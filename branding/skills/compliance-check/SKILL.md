---
name: compliance-check
description: Use when asked to audit, review, or check whether existing code/UI complies with the Optimizers brand guidelines — colors, typography, buttons/components, icons, logo usage — WITHOUT making any changes. Produces a report only. Trigger phrases: "brand compliance check", "does this comply with our brand guidelines", "audit for brand/design-system compliance", "brand QA report".
allowed-tools: Read, Grep, Glob
---

# Brand compliance check (report only)

This skill is read-only by design (see `allowed-tools` above) — it must never edit code, only report.

Read `../../AGENTS.md` first, then `BRAND_IDENTITY.md` and `design-system/tokens.css`/`components.css`
for the values/classes to check against. Scan the target code for compliance issues: hardcoded hex
colors that should be `--op-color-*` tokens, non-brand fonts, buttons/components that don't reuse the
`.op-btn--*`/`components.css` classes, logo-rule violations (rotated/recolored/outlined/stretched/
shadowed/decorated), and icon usage outside the 40-icon set's style.

Produce a structured report: file:line, what's wrong, what it should be instead, and whether the
expected value itself is `[FACT]`-backed spec or an `[UNVERIFIED]`/`[DEFAULT]`/extrapolated one (per
`BRAND_IDENTITY.md`'s provenance tags) — don't cite a `[DEFAULT]` value as a hard violation with the
same confidence as a `[FACT]` one. Do not modify any files.
