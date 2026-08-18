---
name: frontend-dev
description: Use when writing or reviewing frontend code (HTML/CSS/React/etc.) for Optimizers that should use the design system — tokens, components.css classes, icons, layout/grid utilities. For day-to-day feature/page development, not initial project scaffolding or fixing legacy non-compliant UI (see the scaffold skill for those). Trigger phrases: "build a page/component for Optimizers", "use our design system", "implement this UI with our tokens", "frontend dev using the Optimizers brand kit".
---

# Frontend dev with the Optimizers design system

Read `../../AGENTS.md` first for the read order and fast paths, and respect its caveats (provenance
tags in `BRAND_IDENTITY.md`, the `#020202`/`#020601` color discrepancy — prefer the shipped `#020202`,
favicon's unofficial status).

Default to `design-system/tokens.css` custom properties and `design-system/components.css` classes
over hand-rolled styles; use `design-system/layout.css` grid/breakpoint utilities for layout; pull icons
from `assets/icons/` (indexed in `assets/manifest.json`) rather than an external icon set; pick the
correct logo file via `assets/manifest.json`'s `intendedBackgrounds`/hierarchy rules. See `design-system/
COMPONENTS.md` for do/don't and accessibility notes per component, and `design-system/preview.html` to
see everything rendered together.
