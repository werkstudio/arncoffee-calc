# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Baristas at ARN Coffee, using a personal mobile phone (one-handed, glove-possible), during a production batch — before or while making multiple drinks simultaneously. No management or multi-user context; this is a solo, in-the-moment operational tool.

## Product Purpose

A production efficiency calculator that eliminates mental math during high-volume batch prep. The barista enters how many cups of each drink to make; the tool returns exact ingredient grams needed, total espresso pulls required, and a cumulative logistics summary across all active recipes. Marking a recipe done removes it from totals and visually confirms completion, allowing confident progress through a busy shift.

## Positioning

Purpose-built for ARN Coffee's exact five-drink menu with per-recipe ingredient breakdowns and a yield-adjustable espresso pull counter — not a generic recipe manager. The constraint (hard-coded recipes) is the feature: zero setup, zero mistakes, always correct for this shop.

## Operating Context

- Used on a mobile phone, one-handed, in a loud and fast-moving café kitchen.
- Always open during active production — never a planning-desk tool.
- Baristas may have wet or sticky hands; large tap targets are critical.
- The tool resets per shift; no cross-shift memory is needed.
- Language: Bahasa Indonesia is the operational language; some English technical terms (g, ESP, pulls) are standard and accepted by the crew.

## Capabilities and Constraints

- Seven hard-coded recipes: Americano Berry, Americano Berry Single Shot, Aren Classic, Aren Strong, Butterscotch Classic, Butterscotch Strong, Matcha Latte.
- Ingredients tracked: ESP (espresso), Susu Fresh, Susu Evap, Gula Aren, Syrup, Berry Juice, Matcha, Gula Pasir, Air.
- Espresso yield adjustable per session: 30–45 g per pull (default 35 g), recalculates live.
- Mark-as-done toggle: greyscales recipe card, removes from logistics totals.
- No persistence — refresh or reset clears all state. This is intentional.
- No recipe add/edit UI — recipes are fixed by design.
- No backend, no auth, no network dependency.
- Must function as a single HTML file openable directly in a browser (no build step required).

## Brand Commitments

- Name: ARN Coffee. Subtitle wording is flexible.
- Amber (#f59e0b → #d97706) is the established brand accent.
- Warm paper-white canvas (#FAF9F5) and white cards on soft amber-tinted shadow elevation are the established visual language (replaced the earlier near-black/glassmorphism direction by explicit request, 2026-08-15).
- Plus Jakarta Sans is the confirmed typeface.
- The recipe icon set mixes Lucide line icons with the operator's own flat-illustration SVGs (`/assets`) where one exists for the ingredient/action (bean, syrup, portafilter, measuring cup, coffee shop, coffee bag).

## Evidence on Hand

- Full working implementation in `index.html` (vanilla JS + Tailwind CDN), paired with a `/assets` folder of the operator's own flat-illustration SVG icons.
- Six complete recipes with all ingredient weights confirmed by the existing code.
- App now ships as `index.html` + `/assets` (no longer a single file in isolation) — still zero-build and directly openable from the folder.

## Product Principles

1. **Zero setup, zero error.** Fixed recipes remove input mistakes; the barista only enters quantity.
2. **One-handed in production.** Every control is reachable and tappable with a thumb under real kitchen conditions.
3. **Math done, not shown.** Surface answers (grams, pulls), not formulas. The barista acts, not calculates.
4. **Reset is safe.** State lives only in the session; no accidental persistence, no stale data from a previous shift.
5. **Speed over polish.** Load instantly, respond instantly — no network, no framework overhead.

## Accessibility & Inclusion

One-handed use must be guaranteed: all primary interactive controls (quantity steppers, done toggle, yield adjustment, reset) must be reachable with the right or left thumb without repositioning the phone grip. Minimum tap target 44 × 44 px. WCAG AA contrast minimum on all text.
