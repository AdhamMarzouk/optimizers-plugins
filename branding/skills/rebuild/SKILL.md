---
name: rebuild
description: Use when scaffolding a new Optimizers-branded codebase/page/component, or when updating existing UI code that doesn't comply with the Optimizers brand guidelines — colors, typography, buttons/components, icons, layout. Makes the actual code changes. Trigger phrases: "scaffold [with] Optimizers branding", "set up the brand kit", "apply our branding", "make this on-brand", "fix this UI to match our brand guidelines", "bring this up to brand spec".
---

# Brand scaffold / fix

Read `../../AGENTS.md` first for the read order and fast paths, and respect its caveats (provenance
tags in `BRAND_IDENTITY.md`, the `#020202`/`#020601` color discrepancy — prefer the shipped `#020202`,
favicon's unofficial status).

**New scaffold:** wire up `design-system/tokens.css` (or `tokens.json`), reuse `design-system/
components.css` classes rather than writing new ad-hoc styles, and pull logo/icon files per
`assets/manifest.json`'s background/hierarchy rules.

**Fixing existing non-compliant UI:** find hardcoded colors/fonts/buttons that don't match the tokens
or `components.css` classes, and replace them with the design-system equivalents. Don't invent new
components (nav, modals, tables, …) and call them on-brand — extend only within what `components.css`
already defines, or explicitly flag that you're extrapolating, per `AGENTS.md`'s hard constraints.
Never violate the 6 logo rules (no rotate/recolor-outside-3-colors/outline/stretch/shadow/added
elements).
