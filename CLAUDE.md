# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-page production-batch calculator for baristas at ARN Coffee. The entire app — markup, styles, and logic — lives in one file: `index.html`. There is no build step, no package manager, no server, and no test suite. Tailwind (CDN script), Lucide icons (CDN script), and Google Fonts (Plus Jakarta Sans) are loaded from `<script>`/`<link>` tags in `<head>`; everything else is hand-written CSS in a `<style>` block and vanilla JS in a `<script>` block at the bottom of the file.

`.opencode/` contains Node tooling for an unrelated editor plugin (not app dependencies) — ignore its `node_modules`/`package.json` when reasoning about this project.

## Running / previewing

There's nothing to install or build. Open `index.html` directly in a browser (e.g. `open index.html` on macOS), or serve the directory with any static file server if you need a URL (e.g. `python3 -m http.server`). No lint, test, or build commands exist in this repo.

## Architecture

Everything revolves around three global mutable state objects declared in the `<script>` block of `index.html`:

- `recipes` — a fixed array of 7 recipe objects (id, name, icon, and per-cup gram amounts for every possible ingredient field: `esp`, `susu`, `evap`, `arn`, `srp`, `berry`, `mth`, `air`, `gul`, `krim`). Every recipe object sets *all* fields, using `0` for ingredients it doesn't use — this lets `render()` treat the shape uniformly.
- `orders` — quantity ordered per recipe id (keyed by numeric id as string).
- `completed` — done/not-done boolean per recipe id.
- `yieldValue` — grams of espresso per pull, adjustable 30–45, defaults to 35.

There is no framework and no virtual DOM diffing: every state mutation (`updateQty`, `toggleDone`, `adjustYield`, `confirmReset`) calls `render()`, which rebuilds `#recipe-list` and `#global-ingredients` from scratch via `innerHTML` string templates, then re-runs `lucide.createIcons()` to hydrate icon elements. When adding new state or interactions, follow this same "mutate state → call render()" pattern rather than doing targeted DOM patches.

Key behaviors to know before editing `render()`:
- Espresso pulls per recipe are `Math.ceil((esp * qty) / yieldValue)`, and only accumulate into global totals/inventory for recipes that are active (`qty > 0`) and *not* marked done — completing a recipe removes it from all running totals.
- The `air` ingredient field is shared/overloaded: recipe id 1 & 7 (Americano Berry & Americano Berry Single Shot) label it "Air Biasa" and id 5 (Butterscotch Strong) labels it "Air Hangat" — see the `r.id === 5` / `r.id === 1 || r.id === 7` branches in `render()`. Any new recipe using `air` needs an explicit branch added there too.
- `INGREDIENT_COLOR` is a fixed name→hex map used to color-code ingredient values consistently across recipe cards and the logistics panel. See "Ingredient color vocabulary" below before changing or adding colors.
- State is intentionally **not persisted** (no localStorage/cookies/service worker). This is a deliberate product decision ("reset is safe" — see PRODUCT.md) — do not add persistence.
- The reset confirmation is a custom bottom-sheet overlay (`#reset-overlay`), not `window.confirm()` — keep it that way; don't reintroduce native dialogs.

## Design & product source of truth

- `DESIGN.md` is the authoritative design system (colors, type scale, spacing, component specs, named rules) for this app, generated/maintained via the **impeccable** skill. Notable hard rules from it:
  - **Ingredient color vocabulary is fixed and must never be reassigned**: white = espresso, amber `#f59e0b` = gula aren, purple `#c084fc` = syrup, pink `#ec4899` = berry, green `#22c55e` = matcha, blue `#60a5fa` = water/air.
  - Amber (`#f59e0b`) is reserved for ≤3 primary attention elements at a time (pulls counter, active quantity, + button) — don't use it decoratively.
  - Green is reserved exclusively for the "done" state of the Mark-as-Done button.
  - No sharp corners anywhere (`border-radius` always ≥ 12px); no cast/offset box-shadows for elevation — depth comes from `backdrop-filter: blur()` + opacity only, and only on cards/header (never on inner elements).
  - All interactive controls must be reachable one-handed/one-thumb; minimum tap target 40×40px (44×44px preferred).
- `PRODUCT.md` is the authoritative product spec (users, positioning, constraints, principles) — also impeccable-skill-managed. Key constraints: five/six hard-coded recipes with no add/edit UI, no backend/auth/network dependency, must remain a single openable HTML file, UI copy in Bahasa Indonesia (English technical terms like `g`, `ESP`, `pulls` are accepted).
- A `.claude/settings.local.json` PostToolUse/Stop hook runs the impeccable design detector (`node .claude/skills/impeccable/scripts/hook.mjs`) automatically after edits to UI files — this checks changes against `DESIGN.md`'s rules. If it flags something, reconcile with `DESIGN.md` rather than suppressing it.
- For any nontrivial visual/UX change, prefer invoking the `impeccable` skill (audit/polish/critique/etc.) over ad hoc styling — it's the established workflow for this repo and keeps `DESIGN.md` in sync.
