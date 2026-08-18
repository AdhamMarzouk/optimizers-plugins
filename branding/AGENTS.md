# Optimizers Brand Kit — Start Here

This repo is a self-contained brand kit for **Optimizers**, built so an AI coding agent can read it once
and then produce on-brand deliverables (websites, decks, UI) without a human designer in the loop.

## Read order

1. **`AGENTS.md`** (this file) — orientation and fast paths.
2. **`BRAND_IDENTITY.md`** — the full rules and rationale. Every claim is tagged `[FACT]`, `[INFERRED]`,
   `[UNVERIFIED]`, `[GAP]`, or `[DEFAULT]` — read the legend at its top before trusting a specific claim
   as hard brand law.
3. **`assets/manifest.json`** — the exact file to use for a given background/context.
4. **`design-system/tokens.css`** (or `tokens.json` for non-CSS consumers) — implementation-ready values.

Don't skip straight to implementation-ready values without at least skimming `BRAND_IDENTITY.md` once —
several tokens (button hover colors, type scale px, spacing/radius) are `[DEFAULT]`/`[UNVERIFIED]`
placeholders, not confirmed brand spec, and you should know which is which before shipping something
client-facing.

## Fast paths

**"Which logo file do I use on this background?"**
Filter `assets/manifest.json`'s `assets[]` by `intendedBackgrounds`. If more than one entry qualifies,
prefer the lower `hierarchyTier` number in spirit — i.e. `primary` > `secondary` > `tertiary`. Tertiary
(Pastel Green mark) is meant to be used sparingly, only when the hierarchy specifically calls for it, not
as a default dark-background option (white is the default there).

**"I need brand colors as CSS or JSON."**
Use `design-system/tokens.css` (`--op-color-*`, plus semantic aliases like `--op-text-on-green`) or
`design-system/tokens.json` for the same values in a non-CSS-friendly shape. Don't hand-copy hex codes
out of `BRAND_IDENTITY.md` prose — the tokens files are the implementation source of truth for values;
`BRAND_IDENTITY.md` is the source of truth for meaning/rules.

**"I need the fonts."**
`fonts/Sora/` (8 weights) and `fonts/KO-Sans-Arabic/` (7 weights, no ExtraBold). `@font-face` rules are
already wired up in `tokens.css` pointing at these paths. The Arabic-uses-the-same-hierarchy-as-English
mapping is `[INFERRED]`, not sourced — see `BRAND_IDENTITY.md` §5.3.

**"I need a button" — including confirm/cancel/delete.**
`design-system/components.css` → `.op-btn--primary`, `.op-btn--secondary-dark`/`-light` (spec'd,
`BRAND_IDENTITY.md` §9), plus `.op-btn--ghost-dark`/`-light` (on-brand, extrapolated) and `.op-btn--danger`
(explicitly non-brand red, reuses the input-error color). "Confirm"/"Cancel"/"Delete" map onto these via
the semantic table in `design-system/COMPONENTS.md` — don't create new classes that just re-skin
Primary/Secondary under a different name. Hover colors on Primary/Secondary are `[UNVERIFIED]`
placeholders — fine to use, but don't present them as confirmed brand spec.

**"I need something else — an input, a textarea, a checkbox, a card, a badge, or an example form."**
Also in `components.css`, banner-commented `NOT OFFICIALLY SPECIFIED`. Styled to match the brand for
practical usability, but get design sign-off before treating as approved brand components in
client-facing work. Don't invent further components (nav, modals, tables, etc.) and call them on-brand —
extend only within what's already here, or flag that you're extrapolating. For usage guidance beyond the
raw CSS (when to use which variant, do/don't, accessibility notes) and a ready-to-copy contact-form
composition example, see `design-system/COMPONENTS.md`.

**"I need an icon."**
`assets/icons/` — 40 UI icons (cart, chart-growth, check, close, search, arrow-right, arrow-left, menu,
heart, star, box-package, truck-shipping, dollar-payment, bell, user, settings, plus, minus, edit-pencil,
trash, download, upload, filter, calendar, chevron-down, chevron-up, lock, eye, mail, share, clock, info,
external-link, warning, help-circle, refresh, image, tag, location-pin, phone), indexed in
`assets/manifest.json`'s `icons[]` array. Green-only, built for dark backgrounds — the one PDF-documented
pairing (`BRAND_IDENTITY.md` §6). Not from the original kit (style spec existed, files didn't) — built to
match it this pass. Need one that doesn't exist? Extend the set to the same 24×24/stroke-only style, don't
pull from an external icon library and call it on-brand.

**"I need the background texture."**
Two options: `design-system/pattern/backgrounds/pattern-bg-{blackforest,pastelgreen,white}.svg` (+ `.png`
exports) are pre-composited, ready-to-use background images — reach for these by default, they render
correctly everywhere. `design-system/pattern/op-pattern-tile.svg` plus `.op-pattern--overlay`/
`.op-pattern--multiply` utility classes in `components.css` is the live/tintable CSS version — **but**
`--overlay` on Black Forest is verified near-invisible due to blend-mode math (`BRAND_IDENTITY.md` §8),
so only use it if you understand that caveat or need the tintability.

**"I need a favicon."**
`design-system/favicon/` — generated, **not** part of the original brand kit, transparent green mark per
explicit brand-owner direction. Read `design-system/favicon/README.md` before using it in any official or
legal context (it also notes a transparency-rendering caveat on some platforms).

**See it all rendered:** open `design-system/preview.html` in a browser. It renders every logo variant,
color, type size, button state, extrapolated component, the icon set, the grid system, both pattern
treatments, and the favicon set, using the real files — useful both as a visual reference and to
sanity-check nothing 404s after you copy this kit into a new project.

## Hard constraints — never do this

From `BRAND_IDENTITY.md` §3.4, the logo's 6 explicit rules:
1. Never rotate the logo.
2. Never recolor it outside the 3 approved colors (black / white / Pastel Green).
3. Never outline it.
4. Never stretch or distort it.
5. Never apply a drop shadow to it.
6. Never add extra elements near or on it.

More generally: **never invent brand colors or a photography library and present them as on-brand.** The
source guidelines don't define these (`BRAND_IDENTITY.md` §13 lists every confirmed gap, and what's since
been addressed vs. deliberately left alone) — if a project needs them, build to the documented style spec
and be explicit that it's an extrapolation, the same way this kit flags its own extrapolated components.

## Source-of-truth policy

If `design-system/tokens.css` / `tokens.json` and `BRAND_IDENTITY.md` ever disagree on a value, that's a
bug in this repo to flag and fix — not a choice for you to make between them. `BRAND_IDENTITY.md` is
authoritative on meaning and rules; the tokens files are its machine-readable mirror and should always
match it exactly.

---
