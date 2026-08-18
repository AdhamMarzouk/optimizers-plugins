# Optimizers Component Guidance

`components.css` has the implementation (classes, states). This file has the *usage rules* — when to
reach for a variant, what not to combine, and accessibility notes. `components.css` comments stay as
lightweight `SPEC'D`/`NOT OFFICIALLY SPECIFIED` banners; the "why/when" lives here. Same provenance tags
as `BRAND_IDENTITY.md` (`[FACT]`/`[INFERRED]`/`[UNVERIFIED]`/`[DEFAULT]`) apply throughout.

---

## Button — `SPEC'D` (BRAND_IDENTITY.md §9, PDF p.21)

**Purpose:** user actions. Primary is the one main/default action in a given view or group; secondary is
a less-important supporting action.

**Variants:** `.op-btn--primary` (Pastel Green fill, Black Forest text), `.op-btn--secondary-dark` (white
outline, for dark backgrounds), `.op-btn--secondary-light` (Black Forest outline, for light backgrounds).
Pick the secondary variant that matches the surface it sits on — don't use `-light` on a dark background
or vice versa (this breaks the same contrast logic as the logo's usage rule, `BRAND_IDENTITY.md` §3.5).

Two further variants, both `NOT OFFICIALLY SPECIFIED`, added to cover common needs beyond the PDF's two:
- **`.op-btn--ghost-dark` / `.op-btn--ghost-light`** — on-brand (no new colors): no fill/border, colored
  text only, subtle background-tint hover. For the lowest-emphasis action in a group.
- **`.op-btn--danger`** — explicitly **non-brand**: reuses `--op-utility-error`, the same red already
  established for input error states. Reserve for destructive actions only.

**Semantic mapping — "Confirm"/"Cancel"/"Delete" aren't separate CSS classes, they're usage guidance:**

| Intent | Variant | Why |
|---|---|---|
| Confirm / Save / Yes | `.op-btn--primary` | The one main action in the group |
| Cancel / Dismiss / Not now | `.op-btn--secondary-*` or `.op-btn--ghost-*` | Secondary if it needs visible weight (e.g. a modal with real stakes); Ghost if it should recede (e.g. a low-stakes dialog) |
| Delete / Remove / Discard permanently | `.op-btn--danger` | Destructive only — never use Danger for a merely secondary action |

Don't create additional named classes (`.op-btn--confirm`, `.op-btn--cancel`, etc.) that just re-skin
Primary/Secondary under a different name — that's duplication, not a new variant. Use the table above to
pick the right existing/new variant instead.

**Don't:**
- Don't use two primary buttons side-by-side in the same group — it breaks the "one main action"
  hierarchy the color choice implies.
- Don't use Danger for anything non-destructive — it's a strong visual signal (`NOT OFFICIALLY SPECIFIED`,
  non-brand) and loses meaning if used decoratively or for ordinary secondary actions.
- Don't apply a drop shadow — while `BRAND_IDENTITY.md` §3.4's "never drop shadow" rule is scoped to the
  logo mark itself, keeping buttons shadow-free too keeps the flat, minimal visual language consistent
  with the brand's overall look. `[INFERRED]` house-style recommendation, not a hard rule.
- Don't rely on the documented hover colors as pixel-perfect brand spec — they're `[UNVERIFIED]`/
  `[DEFAULT]` placeholders (see `tokens.css`). Fine to use, not fine to present as confirmed.

**Accessibility:** Primary text (Black Forest `#020601` on Pastel Green `#6ae499`) passes WCAG AA at
roughly 5.2:1 contrast. Secondary/Ghost variants rely on the outline/text contrast against whatever
background they're placed on — verify case-by-case if used against anything other than pure white or
Black Forest (e.g. a photo background, per `BRAND_IDENTITY.md` §7). Danger's white-on-red also passes
WCAG AA; don't lighten the red without re-checking contrast.

---

## Input — `NOT OFFICIALLY SPECIFIED`

**Purpose:** text entry (search, forms, filters). No input/form guidance exists anywhere in the source
guidelines `[GAP]` — this component is built to fit the palette/typography, not derived from brand law.

**Variants:** default, `:focus` (Pastel-Green-tinted ring), `:disabled`, `.op-input--error`.

**Don't:**
- Don't use `--op-utility-error` (the red error color) anywhere outside input validation states — it is
  explicitly not a brand color, just a generic UI necessity, and using it decoratively would misrepresent
  it as an approved accent.
- Don't skip the focus state for keyboard accessibility — it's included specifically so it isn't dropped
  under time pressure.

**Accessibility:** the focus ring (`box-shadow` with a Pastel-Green-tinted glow) is a supplement to,
not a replacement for, the browser's default focus outline behavior in `outline: none` — verify your
final implementation still signals focus clearly for keyboard users, especially on the disabled/error
variants where color alone shouldn't be the only signal (add `aria-invalid`/error text in real usage).

---

## Card — `NOT OFFICIALLY SPECIFIED`

**Purpose:** grouping related content into a bounded surface. No card guidance exists in the source
`[GAP]` — grounded in the approved background pairings (`BRAND_IDENTITY.md` §3.3/§4), not invented colors.

**Variants:** `.op-card--light` (white surface, Big Stone body text), `.op-card--dark` (Black Forest
surface, white text), `.op-card--accent` (Pastel Green surface, **required** Black Forest text per
`BRAND_IDENTITY.md` §4's "text on green" rule — never override this to white or any other color).

**Don't:**
- Don't nest a `.op-card--accent` inside another card of a different variant without checking the
  transition reads cleanly — the required-Black-Forest-text rule can look jarring against certain
  surrounding colors if not spaced/bordered deliberately.
- Don't mix card variants arbitrarily within one layout for no reason — pick a hierarchy (e.g. accent
  cards for featured/highlighted content only) and stay consistent, echoing the logo's own hierarchy
  discipline (primary/secondary/tertiary, used sparingly).

**Accessibility:** `.op-card--dark` and `.op-card--accent` both meet contrast requirements by
construction (reusing the same text/surface pairings validated in §4). If you add custom content colors
inside a card, re-check contrast against that specific card's background.

---

## Badge — `NOT OFFICIALLY SPECIFIED` as a component, but reuses a real `[FACT]` color pairing

**Purpose:** small status/label markers (e.g. "New", tags, counts). Not itself a documented brand
component, but its one color combination (Pastel Green background, Black Forest text) is directly the
`[FACT p.14]` pairing, not an invented one.

**Variants:** single style — intentionally not multiplied into semantic colors (success/warning/error)
since the source guidelines define no semantic palette (`BRAND_IDENTITY.md` §4). If a project needs
status-differentiated badges (e.g. red for "expired"), that requires new, clearly-non-brand colors — flag
it as such rather than presenting it as an Optimizers style.

**Don't:**
- Don't stack badges inside buttons or other badges.
- Don't use badge styling for anything that isn't a short, glanceable label — it's not a substitute for
  a card or an alert.

**Accessibility:** ensure badge text remains legible at small sizes (13px `[DEFAULT]`) — don't shrink
further without checking real-world legibility, especially for numeric counts.

---

## Icons — see `assets/icons/` and `BRAND_IDENTITY.md` §6

Not a `components.css` entry (they're SVG assets, not CSS components), but the same discipline applies:
the 40-icon set is green-only, built for dark backgrounds per the one documented pairing `[FACT p.16]`.
Don't recolor them for light backgrounds without acknowledging that's an extrapolation beyond the source
spec, the same way the logo's light-background icon guidance is flagged `[INFERRED]`/`[GAP]` elsewhere.

---

## Composition example: Contact form

`NOT OFFICIALLY SPECIFIED` — demonstrates Input, Textarea, Checkbox, and Button composing together. Live
version in `design-system/preview.html`'s "Example: Contact Form" section. Copy this pattern directly
rather than reverse-engineering it from the rendered page:

```html
<form>
  <label>
    <span>Name</span>
    <input class="op-input" type="text" placeholder="Jane Doe">
  </label>
  <label>
    <span>Email</span>
    <input class="op-input" type="email" placeholder="jane@example.com">
  </label>
  <label>
    <span>Message</span>
    <textarea class="op-input" placeholder="How can we help?"></textarea>
  </label>
  <label>
    <input class="op-checkbox" type="checkbox">
    <span>I agree to the terms and privacy policy.</span>
  </label>
  <div>
    <button class="op-btn op-btn--primary" type="submit">Submit</button>
    <button class="op-btn op-btn--ghost-light" type="reset">Cancel</button>
  </div>
</form>
```

Notes:
- `textarea.op-input` gets a `min-height`/`resize: vertical` rule in `components.css` — plain `.op-input`
  alone is tuned for single-line `<input>` elements.
- `.op-checkbox` sets `accent-color` to the brand green — the simplest correct way to get an on-brand
  checkbox without hand-building custom SVG checkbox artwork.
- Submit uses Primary (the one main action); Cancel uses Ghost per the button semantic mapping table
  above — this is a low-stakes form, so Ghost (not Secondary) is the better fit for "Cancel" here.
- Layout (label/field spacing, button row) is left to the consuming project — only the component classes
  above are part of this kit.
