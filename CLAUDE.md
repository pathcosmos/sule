# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project type

Static, single-page personal supplement guide (`index.html`) deployed via **GitHub Pages**. No build system, no package manager, no tests — edit the HTML directly.

The eight `IMG_9527.jpg`–`IMG_9534.jpg` files in the repo root are the source photos of the user's supplements; they are the ground truth that the HTML cards must stay consistent with. If a supplement is added/removed, update both the photo set and the corresponding `<article class="card">` block.

## Local preview

Open `index.html` directly in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/
```

## Deploying

GitHub Pages serves from the repo's default branch root. After pushing changes to `main`, the live site updates automatically (no Actions, no build step).

## Editing the guide

The page is intentionally one file — all CSS lives in the `<style>` block at the top of `index.html`, and content is hand-authored Korean HTML. Key structural conventions:

- **Time-of-day schedule** (`<section class="schedule">` at top) and the **per-supplement cards** (`<article class="card …">`) must agree. If you change a supplement's recommended timing in its card, also update the corresponding `<div class="slot …">` bullet.
- Each card uses a topical accent color via a modifier class (`gut`, `cardio`, `mineral`, `vitamin`, `sleep`, `energy`, `folate`). Reuse an existing modifier when adding cards rather than introducing new ones unless a new category is genuinely needed.
- Disclaimer banner at the top of `<main>` is load-bearing — this is health-adjacent content, so don't remove it without the user's explicit say-so.

## Content guidance

When updating dosage/timing text, prefer label-stated values from the product photos over generic web claims. Flag interactions (anticoagulants, antibiotics, thyroid meds, B12 masking by high-dose folate) explicitly in the relevant card's `<details>` block — those warnings are the main reason this page exists.
