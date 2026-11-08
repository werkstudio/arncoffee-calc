---
name: ARN Coffee Efficiency Tracker
description: A production-batch calculator for baristas — fresh, paper-white, and built for one-handed use under kitchen pressure.
colors:
  canvas: "#FAF9F5"
  card: "#FFFFFF"
  card-tint: "#F6F3EC"
  ink: "#241B10"
  ink-muted: "#7A6F5D"
  ink-ghost: "#A69C89"
  border: "rgba(36,27,16,0.08)"
  border-strong: "rgba(36,27,16,0.16)"
  amber-fire: "#F59E0B"
  amber-deep: "#D97706"
  amber-ink: "#451A03"
  amber-fg: "#92400E"
  danger: "#DC2626"
  danger-tint: "rgba(220,38,38,0.08)"
  danger-border: "rgba(220,38,38,0.25)"
  success: "#15803D"
  success-tint: "rgba(21,128,61,0.10)"
  success-border: "rgba(21,128,61,0.25)"
  ingredient-espresso: "#292524"
  ingredient-milk: "#78716C"
  ingredient-krimer: "#A16207"
  ingredient-gula-aren: "#B45309"
  ingredient-syrup: "#9333EA"
  ingredient-matcha: "#15803D"
  ingredient-berry: "#DB2777"
  ingredient-air: "#2563EB"
typography:
  display:
    fontFamily: "'Plus Jakarta Sans', sans-serif"
    fontSize: "3.75rem"
    fontWeight: 800
    lineHeight: 1
    letterSpacing: "-0.02em"
  headline:
    fontFamily: "'Plus Jakarta Sans', sans-serif"
    fontSize: "1.5rem"
    fontWeight: 800
    lineHeight: 1.1
    letterSpacing: "-0.015em"
  title:
    fontFamily: "'Plus Jakarta Sans', sans-serif"
    fontSize: "0.875rem"
    fontWeight: 800
    lineHeight: 1.2
  body:
    fontFamily: "'Plus Jakarta Sans', sans-serif"
    fontSize: "0.875rem"
    fontWeight: 700
    lineHeight: 1.4
  label:
    fontFamily: "'Plus Jakarta Sans', sans-serif"
    fontSize: "0.625rem"
    fontWeight: 900
    letterSpacing: "0.12em"
rounded:
  pill: "2rem"
  card: "2.5rem"
  panel: "3rem"
  chip: "1.5rem"
  icon-box: "0.8125rem"
  stepper: "0.75rem"
spacing:
  xs: "8px"
  sm: "12px"
  md: "16px"
  lg: "20px"
  xl: "32px"
  2xl: "48px"
components:
  button-primary:
    backgroundColor: "{colors.amber-fire}"
    textColor: "{colors.amber-ink}"
    rounded: "{rounded.stepper}"
    padding: "0 0"
    size: "44px"
  button-done:
    backgroundColor: "{colors.card-tint}"
    textColor: "{colors.ink-muted}"
    rounded: "{rounded.chip}"
    padding: "16px 24px"
  button-done-active:
    backgroundColor: "{colors.success-tint}"
    textColor: "{colors.success}"
    rounded: "{rounded.chip}"
    padding: "16px 24px"
  button-reset:
    backgroundColor: "{colors.danger-tint}"
    textColor: "{colors.danger}"
    rounded: "{rounded.stepper}"
    padding: "8px 16px"
  card:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.card}"
    padding: "20px"
  card-active:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.card}"
    padding: "20px"
  pulls-display:
    backgroundColor: "{colors.amber-fire}"
    textColor: "{colors.amber-ink}"
    rounded: "{rounded.pill}"
    padding: "20px"
  stepper-pill:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.amber-fire}"
    rounded: "{rounded.icon-box}"
    padding: "3px"
---

# Design System: ARN Coffee Efficiency Tracker

## Overview

**Creative North Star: "The Fresh Countertop"**

Same barista cheat-sheet, moved off the night-lit espresso machine and onto a bright morning counter. The mechanism hasn't changed — hard-coded recipes, instant gram math, one-handed operation — but the reading environment has: this now reads as a clean production sheet under real kitchen daylight rather than a control panel glowing in the dark. Amber (#f59e0b) stays the sole warm accent and Plus Jakarta Sans stays the only typeface — both are ARN Coffee's confirmed brand commitments and carried forward unchanged from the previous dark system. What's new is the ground: warm paper-white canvas, white cards lifted with soft amber-tinted shadows instead of glassmorphism blur, near-black espresso-brown ink instead of warm white, and a full ingredient-color re-tuning so every value still meets AA contrast on light instead of dark.

One deliberate holdover ties the two eras together: the quantity stepper is still a dark near-black pill with the amber count glowing inside it — the one intentionally dark object on an otherwise light page, like the machine itself sitting under the fresh counter. This is a signature detail, not an inconsistency; do not lighten it.

The operator's own flat-illustration SVG icons (`/assets`) now do real identity work — a coffee-shop mark in the header, a portafilter as the pulls-widget's ghost texture, a measuring cup on the yield stepper, and full-color bean/coffee-cup/syrup-bottle/portafilter icons on four of the six recipe cards — mixed with Lucide line icons on the two recipes (Americano Berry, Matcha Latte) that have no matching illustration.

**Key Characteristics:**
- Warm paper-white canvas with white cards lifted by soft amber-tinted shadow — depth without blur
- Amber as a single-frequency fill accent; a darker amber-fg (#92400E) carries amber *text/icons* on light surfaces for contrast
- The dark stepper pill — one deliberate dark object, a callback to the machine under the counter
- Ultra-high-contrast typography: massive display numbers vs. tiny receding labels
- Color-coded ingredient values, re-tuned for AA contrast on light surfaces
- The operator's own SVG illustrations used as real content (recipe icons, brand mark, widget icons), not decoration
- Generous tap targets on all interactive controls — built for wet hands, one grip
- Rounded to softness: `2.5rem` cards, `3rem` logistics panel, `2rem` yield widget

## Colors

The palette is a single warm accent burning against warm paper-white, not near-black. Amber earns its presence on fills; a darker amber carries text and icons so contrast survives on light.

### Primary
- **Amber Fire** (#F59E0B) / **Amber Deep** (#D97706): Fill-only. Used as background on the pulls display, the `+` quantity button, and the logistics summary callout — never as text or icon color on a light surface (fails contrast there).
- **Amber Ink** (#451A03): Text printed onto amber-filled surfaces (pulls counter, `+` button, espresso-required callout). Unchanged from the dark system.
- **Amber FG** (#92400E): The on-light amber role — recipe "ESP" meta labels, the "COFFEE" wordmark, yield chevrons, the pulls-tag `(2P)` suffix, the focus ring. This is a new role the dark system didn't need (amber text read fine on near-black; it does not read reliably on white).

### Neutral
- **Canvas** (#FAF9F5): The page background. Warm paper-white, not stark white — gives white cards something to lift off of.
- **Card** (#FFFFFF): Recipe cards, yield widget, logistics panel, reset sheet. Pure white against the slightly warmer canvas.
- **Card Tint** (#F6F3EC): Ingredient detail cells, the resting Mark-as-Done button, the idle recipe icon box. One step warmer/darker than Card — the system's "inset" surface.
- **Ink** (#241B10): Primary text, and the stepper pill's background. Warm near-black, not pure black.
- **Ink Muted** (#7A6F5D): Secondary labels, supporting copy — passes ~4.9:1 on white.
- **Ink Ghost** (#A69C89): Idle icon tint only; never relied on for text contrast.
- **Border** (rgba(36,27,16,0.08)) / **Border Strong** (rgba(36,27,16,0.16)): Hairline card borders and dividers, warm-tinted rather than neutral grey.

### Secondary (Ingredient Color Map — retuned for light backgrounds)
Every value below is chosen to clear 4.5:1 against white/card-tint; the old dark-theme hues (white text, `#fde68a`, `#f59e0b` for gula aren, `#60a5fa` for air) do not survive the swap to a light ground and were replaced, not reused.
- **Espresso** (#292524): Near-black neutral — the base ingredient, same role white played on dark.
- **Susu Fresh / Susu Evap / Susu UHT / Gula Pasir** (#78716C): Shared warm-grey neutral for plain dairy/sugar values.
- **Krimer** (#A16207): Warm caramel-gold, distinct from Gula Aren.
- **Gula Aren** (#B45309): Darker amber-orange — palm sugar's color, still adjacent to the brand amber family but distinct enough from Krimer and dark enough for contrast.
- **Syrup** (#9333EA): Purple.
- **Matcha Powder** (#15803D): Green (also the Mark-as-Done "done" color — pre-existing dual use carried forward unchanged from the dark system).
- **Berry Juice** (#DB2777): Pink.
- **Air Hangat / Air Biasa** (#2563EB): Blue.

### Named Rules
**The One Amber Rule.** Amber fill (#F59E0B/#D97706) appears on ≤ 3 elements per visible card at any time: the pulls widget, the `+` button, and the active-state icon-box tint. Amber text/icons always use amber-fg (#92400E), never the fill hue — the fill hue fails contrast on white.

**The Ingredient Color Vocabulary Rule.** Each ingredient color is fixed and never reused for another ingredient. AI agents generating new recipe cards must preserve this mapping exactly and must not reintroduce the old dark-theme hex values, which no longer meet contrast on this system's light surfaces.

**The Dark Stepper Rule.** The quantity stepper pill is always `var(--ink)` regardless of card state — it does not lighten, tint amber, or otherwise follow the card's active/idle styling. It is the system's one fixed dark object.

## Typography

**Display / Body Font:** Plus Jakarta Sans (with system-sans fallback) — unchanged brand commitment.
**No secondary font.** Single-family type system, carried forward from the dark system.

### Hierarchy
- **Display** (weight 800, 3.75rem/60px, tracking −0.02em): Total espresso pulls counter.
- **Headline** (weight 800, 1.5rem/24px): The yield value functions at this level.
- **Title** (weight 800, 0.875rem/14px): Recipe names, logistics panel heading.
- **Body** (weight 700, 0.875rem/14px): Ingredient quantity values.
- **Label** (weight 900, 0.5–0.625rem/8–10px, tracking 0.12em, ALL CAPS): Field names, section labels.

### Named Rules
**The Size Contrast Rule.** No two adjacent text elements share both size and weight — display numbers always paired with micro-labels, never medium text.

**The All-Caps-Only-For-Labels Rule.** ALL CAPS + tracking-widest reserved for field labels and section headers only.

## Layout

Single vertically-scrolling mobile column, `max-w-md` (448px) centered, phone-first. Sticky header at top, recipe cards scroll beneath, logistics panel anchors the bottom. Header uses a 10-column grid: pulls display `col-span-6`, yield widget `col-span-4`.

Card padding tightened from the dark system's `24px` to `20px`, and the identity/stepper row gained explicit `min-width:0` + `flex-shrink:0` rules, to keep the longest recipe names ("Butterscotch Classic/Strong") and the full stepper pill both on one line down to ~360px viewport width without clipping.

**The Thumb-First Rule.** All interactive controls reachable without repositioning grip; unchanged from the dark system.

## Elevation & Depth

The dark system's glassmorphism (backdrop-filter blur + translucent dark fills) is retired. This system uses **soft warm-tinted cast shadows** for elevation — appropriate now that the ground is light and blur no longer reads as "floating," it reads as murky.

**Layer 0 — Canvas:** #FAF9F5. No shadow, no border.
**Layer 1 — Card:** #FFFFFF, `1px solid var(--border)`, two-layer shadow (`0 1px 2px rgba(36,27,16,0.04), 0 14px 28px -10px rgba(120,72,20,0.14)`). Recipe cards, yield widget, logistics panel, reset sheet.
**Layer 2 — Card Tint:** #F6F3EC, no shadow. Ingredient cells, idle icon box, resting Mark-as-Done.
**Layer 3 — Accent Gradient:** `linear-gradient(135deg, #f59e0b 0%, #d97706 100%)`. Pulls widget, logistics espresso callout. Unchanged from the dark system — a saturated fill reads the same regardless of ground color.
**Layer X — Dark Stepper:** `var(--ink)` pill with its own small drop shadow (`0 2px 6px rgba(36,27,16,0.18)`), sitting on top of Layer 1 cards. The one place a card-level shadow is deliberately dark-tinted rather than amber-tinted.

The sticky header keeps a light `backdrop-filter: blur(12px)` — this is the one surviving blur use, kept because it serves a specific function (softening scrolled content behind a translucent header) rather than decorating a surface.

### Named Rules
**The Warm-Shadow Rule.** Card elevation shadows are tinted `rgba(120,72,20,…)` (warm amber-brown), not neutral black — ties depth to the brand instead of reading as generic UI chrome. Active cards get a slightly stronger, more amber-saturated shadow than idle ones.

**The One-Blur Rule.** `backdrop-filter: blur()` is reserved for the sticky header only, where it has a functional job (scroll separation). No other surface uses it.

## Shapes

Unchanged from the dark system — the radii are part of the same "no sharp edges" identity regardless of ground color.

- **Cards** (`2.5rem`), **Logistics Panel** (`3rem`), **Pulls/Yield Widgets** (`2rem`), **Icon Boxes** (`13px`, tightened slightly from `1rem` alongside the 48→42px icon-box size reduction for mobile-width safety), **Stepper Pill** (`14px` outer / `12px` buttons), **Mark-as-Done** (`1.5rem`), **RESET** (`0.75rem`).

**The No-Sharp-Edge Rule.** Still absolute: nothing below 8px anywhere.

## Components

### Quantity Stepper
Unchanged concept, same asymmetry (ghost `−`, filled amber `+`), but now the **one deliberate dark object** on the page: `var(--ink)` pill background, `#B7AC98` minus-icon, `#F59E0B` quantity digit (all high-contrast against the dark pill, unaffected by the canvas going light). Padding tightened to `3px` and gap to `3px` (from `4px`/`4px`) for mobile width.

### Recipe Card
- **Shape:** `rounded-[2.5rem]`, `p-5` (20px, tightened from 24px), white card + `1px solid var(--border)` + warm two-layer shadow.
- **Active state:** border → `rgba(245,158,11,0.45)`, shadow shifts to a stronger amber-tinted version. No glass, no blur.
- **Done state:** `opacity:0.35; filter:grayscale(0.6); scale(0.97)` — slightly less extreme than the dark system's `0.25`/full-grayscale, because full desaturation read as broken/disabled rather than "completed" against a light ground; this keeps the completed card legible-but-receded.
- **Icon box:** 42×42px (down from 48px). Idle = `var(--card-tint)` + `1px solid var(--border)`. Active = `rgba(245,158,11,0.14)` fill + `rgba(245,158,11,0.35)` border — a tint, not a solid amber fill, specifically so the full-color custom SVG icons stay legible; a solid amber fill would have muddied their own colors.
- **Icon:** either a Lucide icon (`var(--amber-deep)` active / `var(--ink-ghost)` idle) or one of the operator's SVGs at 30×30px, always full-color regardless of active state.

### Ingredient Detail Cell
Unchanged shape/role; colors now come from the retuned ingredient map (see Colors). `var(--card-tint)` background, `var(--ink-muted)` label, ingredient-hue value.

### Pulls Display Widget
Unchanged amber-gradient hero. Ghost decorative icon changed from Lucide `coffee` to the operator's `assets/015-portafilter.svg`, opacity 0.16, bottom-right — a literal reference to what "pulls" means instead of an abstract coffee-cup glyph.

### Yield Stepper Widget
Now a proper white card (`var(--card)` + border + small shadow) instead of translucent white-on-dark. Carries a small `assets/016-measuring%20cup.svg` (12px) as an absolutely-positioned corner mark rather than inline with the label — inline broke the label's line at ~390px width, so the icon was moved off the text's critical path. Chevron icons use `var(--amber-fg)`, not the fill amber (fails contrast on this card's white background).

### Mark-as-Done Button
Same shape/role. Default: `var(--card-tint)` bg, `var(--ink-muted)` text. Done: `var(--success-tint)` bg, `#15803D` text (darker than the dark system's `#4ade80` — the lighter green failed AA contrast on a light background).

### Logistics Panel
Same shape/role, now a plain white card with warm shadow instead of a `#111→#050505` gradient. Header icon changed from Lucide `clipboard-list` to `assets/010-coffee%20bag.svg` — reads as "stock/ingredients to buy," a closer fit for an accumulated-logistics summary.

### RESET Button
Same shape/role; colors retuned for light (`#DC2626` text on `rgba(220,38,38,0.08)` tint, `rgba(220,38,38,0.25)` border) — the dark system's `#ef4444` was chosen for contrast against near-black and does not need to change hue, only the tint/border opacity was adjusted for the lighter ground.

### Header / Brand Mark
New: `assets/050-coffee%20shop.svg` (34px) sits beside the "ARN COFFEE" wordmark — the system's first real logomark; previously brand was text-only.

## Icon System

Mixed, by design: the operator's own flat-illustration SVGs (`/assets`) are used wherever one exists for the specific ingredient/action; Lucide line icons cover everything else. Current assignments:
- **Custom SVG:** header brand mark (coffee shop), pulls-widget ghost (portafilter), yield-widget corner mark (measuring cup), logistics header (coffee bag). All six recipe cards share one custom SVG — `assets/001-coffee.svg` (to-go cup) — by explicit request, rather than a different illustration per recipe; each card's `icon` (Lucide) field stays populated as an unused fallback should `customIcon` ever be cleared for a given recipe.
- **Lucide:** Mark-as-Done state icon (circle/check-circle), yield chevrons. No recipe currently falls back to Lucide.

**The Full-Color Icon Rule.** Custom SVGs are never recolored or tinted — they carry their own illustration palette regardless of card active/idle state. Never place one on a solid amber fill (muddies both); the tinted `rgba(245,158,11,0.14)` icon-box background exists specifically to host them.

## Do's and Don'ts

### Do:
- **Do** use amber fill (#F59E0B/#D97706) only for backgrounds; use amber-fg (#92400E) for any amber text or icon on a light surface.
- **Do** keep the quantity stepper pill dark (`var(--ink)`) regardless of card or theme state — it is the signature holdover object.
- **Do** keep all tap targets at minimum 44×44px for the stepper buttons specifically (not reduced during the mobile-width tightening pass).
- **Do** tint the recipe icon box amber (not fill it solid) when active, so custom full-color SVGs stay legible.
- **Do** keep the ingredient color vocabulary exact per the retuned map above; never reintroduce a dark-system hex that fails contrast on white.
- **Do** use warm-tinted (`rgba(120,72,20,…)`/`rgba(36,27,16,…)`) shadows and borders instead of neutral black/grey ones.

### Don't:
- **Don't** reintroduce glassmorphism/backdrop-blur anywhere except the sticky header.
- **Don't** use the amber fill hue (#F59E0B) as a text or icon color on any white/light surface — it fails WCAG contrast there; use amber-fg.
- **Don't** recolor or tint the operator's custom SVG icons — they stay full-color as authored.
- **Don't** add border-radius below 12px, or use medium-size type (16–20px) as a standalone hierarchy level — both rules carried forward unchanged from the dark system.
- **Don't** use green anywhere except Matcha ingredient values and the Mark-as-Done completed state.
- **Don't** persist any state between sessions — reset-is-safe is unchanged by the visual redesign.
