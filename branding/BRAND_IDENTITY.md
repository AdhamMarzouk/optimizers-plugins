# Optimizers — Brand Identity Reference

This is the authoritative prose reference for the Optimizers brand. `assets/manifest.json` and
`design-system/tokens.css` / `tokens.json` are machine-readable mirrors of the facts in this document —
they should never disagree with it. If they ever do, that's a bug to fix here, not a choice to make there.

**Source:** `Optimizers Brand Guidelines.pdf` (22 pages — not 51, despite an early tooling
mis-hint; confirmed via the PDF's own page-tree count and a full-text read of every page). The PDF is
the build-time reference only and is **not included** in this repo. This environment has no PDF
page-image renderer available, so anything that could only be verified visually in the source (e.g. an
exact hover-state hex, a corner-radius in px) could not be confirmed — it is labeled `[UNVERIFIED]`
below, never stated as fact.

## Provenance legend

Every non-obvious claim in this document carries one of these tags:

| Tag | Meaning |
|---|---|
| `[FACT p.N]` | Verbatim or near-verbatim text from the PDF, page N |
| `[INFERRED]` | A reasonable extrapolation from adjacent PDF context (captions, layout) — not a direct textual statement |
| `[UNVERIFIED]` | Could not be confirmed — no PDF page-image rendering was possible in this environment |
| `[GAP]` | Confirmed absent from a full-text sweep of all 22 pages — a real hole in the source, not a missed page |
| `[DEFAULT]` | An authoring/design-system choice made for practical necessity — explicitly **not** brand law |

---

## 1. Brand Overview

**Tagline** `[FACT p.2]`: *"We make optimization Simple, Practical, and Profitable for e-commerce
businesses."*

This is the only brand positioning statement in the source document — there is no longer-form mission,
vision, or values section `[GAP]`. Don't pad this with invented company-description boilerplate.

## 2. Brand Voice

`[FACT p.10]`: *"Sora is the voice of our brand. Strong, modern, and confident, it ensures clarity,
impact, and timeless presence across every visual."*

---

## 3. Logo

### 3.1 Construction
The mark is the letters "O" and "P" (Optimizers), each drawn with an arrow/loop motif, combined into a
single lockup that reads as a continuous/infinity loop. *(This is a descriptive observation of the mark's
geometry, not a quoted PDF passage — the closest PDF text, p.4, says the two letters "create a single,
balanced lockup that stands for an integrated continuous results, and refers to infinity process."
`[FACT p.4]`)*

### 3.2 Assets
All files live in `assets/png/` and `assets/svg/` — 12 files total, 6 per format, one per
`{icon | wordmark} × {black | white | pastelgreen}` combination. **`assets/manifest.json` is the
authoritative index** — every file's exact path, pixel dimensions/viewBox, literal hex, hierarchy tier,
and intended background is recorded there; this table is a quick-reference summary, not a substitute.

**Icon (the "OP" symbol, no wordmark) — `assets/{png,svg}/icon-{color}.{ext}`:**

| Use case | File | Tier |
|---|---|---|
| On a white or Pastel Green background | `icon-black.svg` / `.png` | Primary |
| On a Black Forest or Pastel Green background | `icon-white.svg` / `.png` | Secondary |
| On a Black Forest background only, used sparingly | `icon-pastelgreen.svg` / `.png` | Tertiary |

**Wordmark ("OPTIMIZERS" logotype) — `assets/{png,svg}/wordmark-{color}.{ext}`:**

| Use case | File | Tier |
|---|---|---|
| On a white or Pastel Green background | `wordmark-black.svg` / `.png` | Primary |
| On a Black Forest or Pastel Green background | `wordmark-white.svg` / `.png` | Secondary |
| On a Black Forest background only, used sparingly | `wordmark-pastelgreen.svg` / `.png` | Tertiary |

Notes on the files themselves:
- Prefer the `.svg` versions whenever a scalable vector is usable; the `.png` versions are 2000×2000
  (icons) or 1080×1080 (wordmarks), both transparent.
- Wordmark PNG/SVG canvases are square but the mark itself is wide/short and does **not** fill the
  canvas — expect transparent padding on all sides. Don't treat the canvas edge as a tight crop.
- `assets/png/wordmark-white.png` was renamed from a shipped typo (`wordmark-wite.png`) during this
  repo's AI-agent-optimization pass. If you see the old name referenced anywhere outside this repo's
  history, it's stale.

### 3.3 Color hierarchy rule `[FACT p.6]`
- **Primary (black logo):** default choice, on white or Pastel Green backgrounds.
- **Secondary (white logo):** on Black Forest or Pastel Green backgrounds.
- **Tertiary (Pastel Green logo):** on Black Forest background only, "according to the design
  hierarchy" — used sparingly. *(The word "sparingly" is this document's own house-style summary of
  "tertiary," not a PDF quote.)*

### 3.4 Hard rules — the 6 explicit "wrong using" rules `[FACT p.8]`
Verbatim from the PDF's dedicated "Logo Wrong Using" page — exactly these 6, no more:
1. Don't rotate the logo.
2. Don't color the logo (i.e. don't recolor outside the 3 approved colors).
3. Don't outline it.
4. Don't stretch it.
5. Don't drop shadow it.
6. Don't add elements (dots, extra icons, decoration) near or on it.

This "never drop shadow" rule applies to the **logo mark itself** — it does not extend to UI components
generally (buttons, cards, etc. may use shadows; see `design-system/`).

### 3.5 Contrast pairing rule `[INFERRED p.7]`
Separate from the 6 rules above (not itself one of the PDF's explicit "wrong using" bullets): the Logo
Usage page captions read *"Apply the black logo over clean and white images"* and *"Apply the white logo
over the dark images"* `[FACT p.7]`. The reasonable extrapolation from this — never place the black
variant on a busy/dark background, or the white variant on a light background — is kept here as guidance
but flagged as inferred, not a literal rule from the "wrong using" list.

### 3.6 Gaps
- No minimum logo size or clear-space/safe-area rule exists anywhere in the source `[GAP]`. Left
  unaddressed by design — no fill has been attempted for this one.
- No dedicated small favicon/app-icon export exists in the original kit `[GAP]` — see
  `design-system/favicon/` for a derivation built during this pass (`icon-pastelgreen.svg` on a
  transparent background, per the brand owner's explicit direction), clearly labeled as unofficial in
  its own README.

---

## 4. Color Palette `[FACT p.14]`

| Name | Hex | RGB | CMYK | Usage note (verbatim) |
|---|---|---|---|---|
| Pastel Green | `#6ae499` | 106, 228, 153 | 52, 0, 57, 0 | "Used with some text headlines, numbers, icons and some background according to the design hierarchy." |
| Big Stone ("Light black") | `#162a3d` | 22, 42, 61 | 92, 76, 50, 53 | "Used with paragraphs and backgrounds." |
| Black Forest ("Dark black") | `#020601` | 2, 6, 1 | 74, 65, 68, 87 | "Used with main headlines and the text on the green color." |

**Semantic derivation from the usage notes above:**
- Body/paragraph text color → Big Stone.
- Headline text color → Black Forest.
- Text placed on a Pastel Green background → **must** be Black Forest (this is stated as the color's
  role, not optional styling).

**Note on file-hex vs. nominal hex:** the shipped logo asset files use `#020202` as their black, not the
nominal Black Forest `#020601`. Both are "correct" in their own context — the asset files were exported
with a slightly different black than the documented brand hex. This is a known, intentional discrepancy
(see `assets/manifest.json`'s `sourceOfTruthNote`), not a bug to "fix" by matching one to the other.

**Confirmed gap:** there is no tint/shade ramp, secondary accent color, or semantic colors
(success/error/warning) defined anywhere in the source `[GAP]`. If a UI needs those, they are not
specified here — don't invent them and present them as brand colors. (`design-system/tokens.css` does
define one generic utility error color for its extrapolated input component, explicitly commented as
"NOT a brand color.")

---

## 5. Typography

### 5.1 Fonts available
- **English: Sora** — `fonts/Sora/`. 8 weights: Thin, ExtraLight, Light, Regular, Medium, SemiBold,
  Bold, ExtraBold.
- **Arabic: KO Sans** — `fonts/KO-Sans-Arabic/`. 7 weights: Thin, ExtraLight, Light, Regular, Medium,
  SemiBold, Bold. Note it has **no ExtraBold** — its top weight is one step below Sora's.

### 5.2 Hierarchy rules `[FACT p.12]`
| Level | Font | Weight | Size rule |
|---|---|---|---|
| Headline | Sora | Bold | Large, "according to artboard dimensions" |
| Sub-headline 1 | Sora | SemiBold | "Half size of the main headline font" |
| Sub-headline 2 | Sora | SemiBold | "Less size" than Sub-headline 1 (exact ratio not given) |
| Paragraph / body | Sora | Light | "24px or below" |

### 5.3 Arabic mapping `[INFERRED]`
The PDF's "Rules & Hierarchy" page is exclusively about Sora — it **never mentions Arabic or KO Sans**
`[GAP]`. Applying the same hierarchy logic to KO Sans (Light for body, SemiBold/Bold for headlines) is a
reasonable extrapolation, not a sourced rule. Remember KO Sans has no ExtraBold weight when adapting the
top of the scale.

---

## 6. Iconography `[FACT p.16]`
*"Icon style to be minimal, with rounded edges and rounded corners in line with the brand identity's
curvy style. Use the icons with green brand color on the black background."*

- Style: minimal line icons, rounded stroke caps and rounded corners — not sharp/geometric, not
  filled/solid.
- Color: Pastel Green on Black Forest is the only documented pairing. No guidance exists for icons on
  light backgrounds `[GAP]` — extrapolating the same green-on-dark logic, or using Big Stone/Black Forest
  strokes on light backgrounds, is a reasonable `[INFERRED]` choice but not officially specified.
- **A 40-icon UI set now exists at `assets/icons/`** (`cart`, `chart-growth`, `check`, `close`, `search`,
  `arrow-right`, `arrow-left`, `menu`, `heart`, `star`, `box-package`, `truck-shipping`,
  `dollar-payment`, `bell`, `user`, `settings`, `plus`, `minus`, `edit-pencil`, `trash`, `download`,
  `upload`, `filter`, `calendar`, `chevron-down`, `chevron-up`, `lock`, `eye`, `mail`, `share`, `clock`,
  `info`, `external-link`, `warning`, `help-circle`, `refresh`, `image`, `tag`, `location-pin`, `phone`),
  built to this exact style spec: 24×24 viewBox, stroke-only, rounded caps/joins, green-only (the one
  documented pairing — no light-background variant, consistent with the `[GAP]` above). This was **not**
  part of the original kit — the PDF gave the style spec but shipped no icon files — see
  `assets/manifest.json`'s `icons[]` array for the full index. If a project needs icons beyond this set,
  extend it to the same style spec rather than pulling from elsewhere and presenting them as on-brand.

---

## 7. Photography `[FACT p.17-19]`
Three approved treatments — pick based on background, don't mix within one layout:

1. **Style 1 — Natural/authentic color:** real color, natural light, no filter. Use on dark backgrounds.
   Subjects should read as Arab and dressed appropriately for the region; scenes should reference
   e-commerce, revenue growth, or technology.
2. **Style 2 — Black & white, light preset:** desaturated, lighter exposure. Use on white or Pastel Green
   backgrounds.
3. **Style 3 — Green overlay:** *"green multiply mode layer on the images... preferred to used with
   black or white background."* (This document previously called this "duotone" — that's a descriptive
   label of convenience, not a term the PDF uses; the source only describes a multiply-mode green layer.)

No stock/source photography files were included in the kit `[GAP]` — this is a treatment spec to apply
to licensed photography, not a photo library.

---

## 8. Pattern `[FACT p.20]`
*"We use the logo icon 'OP' with outline style in green color with opacity to match the background
color. It's used with overlay mode with the dark background, and multiply mode with the green
background."*

- Construction: the OP icon, outline/stroke-only style, in Pastel Green.
- Opacity: set "to match the background color" — the PDF gives no fixed opacity number. (An earlier
  draft of this document said "low opacity," which overstates precision the source doesn't provide —
  corrected here.)
- Blend mode: **Overlay** on a Black Forest (dark) background; **Multiply** on a Pastel Green background
  — both confirmed exact.
- "Tiled repeatedly" is a reasonable `[INFERRED]` layout treatment (matching the visible texture behind
  section headers in the guideline deck itself) but is not itself stated in the extractable PDF text.

A reusable tile asset now exists at `design-system/pattern/op-pattern-tile.svg`, built from the existing
icon geometry (no separate outline-only artwork was included in the original kit `[GAP]`). Tile size,
inset, and stroke weight are `[DEFAULT]` authoring choices; opacity is exposed as a tunable CSS variable
(`--op-pattern-opacity`) rather than baked in, since the source gives no number.

**Known caveat, verified in-browser during this pass:** CSS `mix-blend-mode: overlay` against a base
color this close to pure black is mathematically near-invisible — overlay's dark-tone response is
`2 × base × blend`, and Black Forest's near-zero luminance (`#020601` ≈ RGB 2,6,1) collapses that to
~0 regardless of opacity. Boosting `--op-pattern-opacity` to 0.9 confirmed the tile itself renders and
tiles correctly (clearly visible on a Pastel Green / multiply swatch at that opacity) — it's specifically
the overlay-on-near-black combination that reads as flat black in a literal CSS implementation, not a
broken asset. The PDF's own guideline deck visibly shows this texture behind its dark section headers, so
either their production tool's "Overlay" handles near-black bases differently, or their dark background
in that specific composition wasn't literally `#020601`. If a project needs the pattern to actually read
on a Black Forest surface, consider a slightly lightened dark surface for that treatment, or a different
compositing approach — this is a `[DEFAULT]`-territory implementation decision, not a brand rule to
violate.

**Ready-to-use pre-composited backgrounds** now exist at `design-system/pattern/backgrounds/`
(`pattern-bg-blackforest.svg`, `pattern-bg-pastelgreen.svg`, `pattern-bg-white.svg`, each with a
rasterized `.png` export). Unlike `op-pattern-tile.svg`, these bake the motif's final visible color and
opacity directly into the file — no `mix-blend-mode` involved — so they render correctly everywhere,
including the Black Forest case that doesn't work via CSS overlay. Use these when you need a guaranteed
correct result; use the CSS utility (`.op-pattern--overlay`/`--multiply` in `components.css`) when you
need a live/tintable version and are aware of its overlay-on-near-black caveat above. The White variant is
`[DEFAULT]` — not PDF-specified, a practical extrapolation since white/light is a very common surface.

**Two ways to tune stroke weight — they are not the same mechanism.** `design-system/preview.html`
renders these three backgrounds as **inline `<svg>`** (not `<img>`), with stroke-width/opacity wired to
`--op-pattern-bg-stroke-width` / `--op-pattern-bg-stroke-opacity` in `tokens.css` — edit either token and
refresh the browser to see the change instantly, no rebuild step. The standalone portable files in
`design-system/pattern/backgrounds/*.svg`/`.png` are a **separate baked snapshot** of whatever those
tokens said at the time they were last generated — an externally-linked SVG/raster file cannot consume a
linking page's CSS custom properties, so they cannot be made "live" the same way. If you change the
tokens, the portable files will silently drift out of sync until someone explicitly regenerates them
(ask the assistant, or re-run the same Node/`resvg` export used to build them) — that's an intentional
tradeoff to keep the shipped kit dependency-free, not a bug.

---

## 9. UI Elements — Buttons `[FACT p.21]`
*Primary — "Used for the main actions according to the background color with a rounded corner and green
color. And with black text."*
*Secondary — "Used for the less priority actions with white outline with dark background and black
outline with the white background."*

| Variant | Background | Text | Notes |
|---|---|---|---|
| Primary | Pastel Green | Black (Black Forest) | Rounded corners. Main/default action. |
| Secondary (on dark bg) | Transparent, white outline | White | Less priority action. |
| Secondary (on white bg) | Transparent, black outline | Black | Same role, light-background context. |

**Hover-state colors are `[UNVERIFIED]`.** The PDF's button page shows "Normal"/"Hover" mockup columns,
but no color values are present in the extractable text layer, and this environment has no PDF
page-image renderer to check the mockup visually. `design-system/tokens.css` defines a plausible
`[DEFAULT]` hover shade (a darker green for primary, a light green fill for secondary) — treat it as an
authoring placeholder, not confirmed brand spec, until someone can verify against the actual PDF
rendering.

No other UI components were specified in the source guidelines `[GAP]`.

Two further button variants exist beyond the spec'd Primary/Secondary — both `NOT OFFICIALLY SPECIFIED`,
see §10: **Ghost** (`.op-btn--ghost-dark`/`-light`, on-brand, no new colors) and **Danger**
(`.op-btn--danger`, explicitly non-brand, reuses the input-error red). "Confirm"/"Cancel"/"Delete" are
handled as a semantic mapping onto these variants in `design-system/COMPONENTS.md`, not as separate CSS
classes.

---

## 10. Extrapolated Component Set

Beyond buttons, `design-system/components.css` and `design-system/preview.html` include inputs, textareas,
checkboxes, cards, badges, and two additional button variants (Ghost, Danger) — styled to match the
palette/typography but **not officially specified** anywhere in the brand guidelines. Danger specifically
introduces a non-brand semantic red, on the same footing as the existing input-error color — never present
it as a 4th approved brand color. Each is clearly banner-commented as such in the code. Don't present
these to a client as approved brand components without design sign-off. For per-component usage guidance
(when to use which variant, do/don't, accessibility notes, and a composition example combining several
components into a form) beyond the raw CSS, see `design-system/COMPONENTS.md`.

---

## 11. Grid & Spacing System `[DEFAULT]`

Not specified anywhere in the source guidelines `[GAP]` — no grid, breakpoints, or container widths are
defined in the PDF. Built during this pass as a practical authoring convenience, same footing as the
existing radius/spacing tokens (§ token definitions below reuse the existing `--op-space-*` scale rather
than inventing a parallel one).

- **Breakpoints:** 640px / 768px / 1024px / 1280px (`--op-breakpoint-sm/md/lg/xl` in `tokens.css`).
- **Container:** max-width 1200px (`--op-container-max-width`), centered, with `--op-space-5` (24px)
  inline padding.
- **Grid:** 12 columns, `--op-grid-gutter` (reuses `--op-space-5`, 24px).

Implementation lives in `design-system/layout.css` (`.op-container`, `.op-grid`, `.op-col-{1..12}`, plus
`md:`/`lg:` prefixed variants). None of this is brand law — a project is free to use a different grid
system entirely without violating anything documented here.

---

## 12. File Manifest

```
optimizers-brand-kit/
├── BRAND_IDENTITY.md              ← this file
├── AGENTS.md                       ← start-here entry point for AI agents
├── assets/
│   ├── manifest.json                ← authoritative asset index: assets[] (logo marks), icons[] (UI icons)
│   ├── png/
│   │   ├── icon-black.png / icon-white.png / icon-pastelgreen.png     (2000x2000, transparent)
│   │   └── wordmark-black.png / wordmark-white.png / wordmark-pastelgreen.png  (1080x1080, transparent)
│   ├── svg/
│   │   ├── icon-black.svg / icon-white.svg / icon-pastelgreen.svg     (viewBox 0 0 1467 934)
│   │   └── wordmark-black.svg / wordmark-white.svg / wordmark-pastelgreen.svg (viewBox 0 0 1080 1080)
│   └── icons/                       ← 16 UI icons, green-only, 24x24 viewBox (built this pass, §6)
├── fonts/
│   ├── Sora/                       (8 weights, .ttf, no LICENSE file — see §5.4)
│   └── KO-Sans-Arabic/             (7 weights, .otf, no LICENSE file — see §5.4)
└── design-system/
    ├── tokens.css                   ← CSS custom properties + @font-face
    ├── tokens.json                  ← machine-readable mirror of tokens.css
    ├── components.css               ← buttons (spec'd) + inputs/cards/badges (extrapolated)
    ├── layout.css                    ← grid/spacing/container utilities [DEFAULT], see §11
    ├── COMPONENTS.md                 ← per-component usage guidance (purpose/variants/don't/a11y)
    ├── preview.html                  ← visual reference / QA page
    ├── pattern/
    │   ├── op-pattern-tile.svg         ← small CSS-repeat tile (mix-blend-mode dependent)
    │   └── backgrounds/                ← pre-composited, ready-to-use pattern backgrounds (§8)
    └── favicon/                     ← unofficial derivation, see favicon/README.md
```

---

## 13. Open Gaps (confirmed absent from the source)

Items below reflect explicit direction on what to fill vs. leave alone — not every gap is meant to be
closed, and some are intentionally left as-is.

**Addressed this pass:**
- ~~No grid/spacing/layout system~~ — now built, `[DEFAULT]`, see §11.
- ~~No icon set beyond the single OP mark~~ — a 16-icon set now exists at `assets/icons/`, see §6. Still
  not part of the *original* kit — built to match its style spec, not sourced from it.
- Favicon — closed with a derivation built to explicit brand-owner direction (transparent, green-only),
  see `design-system/favicon/README.md`. Still not from the original kit (no favicon spec exists there).
- No component usage guidance beyond raw CSS — addressed via `design-system/COMPONENTS.md`, see §10.

**Left as-is, no action taken (explicit decision):**
- No minimum logo size or clear-space/safe-area rule.
- No stationery, social media templates, motion/animation guidance, or co-branding rules.
- No photography library (treatment spec only, §7).

---
