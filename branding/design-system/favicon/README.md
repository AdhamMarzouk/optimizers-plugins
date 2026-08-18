# Favicon / App Icon Set — Unofficial Derivation

**This entire folder is not part of the original Optimizers brand kit.** The source brand guidelines
(`Optimizers Brand Guidelines.pdf`) contain no favicon or app-icon specification of any kind — confirmed
absent via a full-text sweep of all 22 pages `[GAP]`. Nothing here should be treated as brand law.

## What this is

`icon-pastelgreen.svg` (the tertiary green mark) on a **transparent** background — no composited square.
This construction was specified directly by the brand owner (superseding this file's first draft, which
used a Black Forest square background for small-size contrast; that reasoning still applies if you'd
rather use an opaque variant).

No corner radius is baked into any file — platforms (iOS, Android adaptive icons, browser tab UI) apply
their own masking, and the source guidelines specify no radius value anyway.

**Known caveat:** transparent-background icons can render inconsistently across browser/OS chrome. iOS
in particular has historically filled transparent apple-touch-icons with solid black rather than
respecting transparency, and a pure green mark can lose contrast against light browser-tab backgrounds.
This is a known tradeoff of the transparent construction, not a rendering bug in these files.

## Files

| File | Size | Purpose |
|---|---|---|
| `favicon.svg` | vector | Master source, scalable |
| `favicon-16.png` / `favicon-32.png` / `favicon-48.png` | 16/32/48px | Browser tab / bookmark |
| `favicon.ico` | multi-res (16/32/48) | Legacy browser fallback |
| `apple-touch-icon-180.png` | 180px | iOS home-screen icon |
| `android-chrome-192.png` / `android-chrome-512.png` | 192/512px | Android home-screen / PWA icon |
| `site.webmanifest` | — | PWA manifest referencing the two Android sizes |

## Before using this in an official or client-facing context

Get sign-off from whoever owns the Optimizers brand. This was generated programmatically from existing
kit assets to close a practical gap (every real project needs a favicon), not sourced from or approved
against any official brand deliverable.
