# BRIEF — Visual redesign of `index.html` (academic slide deck)

## What this is

`index.html` is a **finished, self-contained web slide deck** (12 slides) for a Thai graduate-school research presentation. It is presented **today** on a projector. The content is final and correct.

Your job is **visual design only**. Make it look genuinely beautiful and professional — the kind of deck that makes an academic audience sit up.

## HARD RULES — breaking any of these ruins the deck

1. **DO NOT change, translate, rewrite, shorten, or reorder ANY Thai or English text content.** Every word, number, table cell, citation and `data-note` attribute must survive byte-identical. This is graduate research content that was fact-checked; invented or altered facts are a serious failure.
2. **DO NOT add, remove, or reorder slides.** Exactly 12 `<section class="slide">` elements must remain, in the same order, each keeping its `data-note` attribute intact.
3. **DO NOT change image `src` paths or add new images.** Available assets are only: `assets/audit1.webp` (real photo), `assets/iv_map.webp` (site map), `assets/sol_sign.webp`, `assets/sol_outcome.webp`. Do not reference any file that does not exist — a broken image on stage is fatal.
4. **Keep all JavaScript behaviour working**: arrow-key / space / PageUp-Down navigation, touch swipe, `N` toggles speaker notes, `F` fullscreen, `#hash` deep-link, progress bar, slide counter, `data-count` number count-up animation.
5. **Keep it a single self-contained `index.html`.** No build step, no external CSS/JS files, no CDN scripts. Google Fonts `<link>` in `<head>` is the one allowed external resource (already present).
6. **Bump the version string** in `<div id="ver">` from `v0.2.0` to `v0.3.0`.
7. Overwrite `index.html` in place. Ignore `index.v020.backup.html` — do not edit or delete it.

## Design brief

**Subject:** office energy waste — people forget to switch off lights when leaving a room. The proposed solution is a low-cost *check-before-you-leave* standard (a prompt sign at the door, a checklist, feedback), deliberately chosen over expensive occupancy sensors.

**Current look:** dark olive-green (`#101408`) ground, amber (`#FFC63A`) accent, green (`#58D6A4`) for positive, coral (`#FF7A5C`) for negative, Noto Sans Thai + JetBrains Mono for figures. That palette direction is good — keep the dark ground and the amber/green/coral semantic roles. Refine it; do not swap to a different colour world.

**Raise the quality bar on:**
- **Typographic hierarchy** — the eyebrow/heading/body/caption scale is flat right now. Make headings command the slide; make captions recede. Keep Thai text comfortably readable at projector distance (Thai glyphs need more line-height than Latin — never go below 1.5).
- **Spacing and rhythm** — consistent vertical rhythm, generous breathing room, nothing cramped against slide edges. Use flex/grid `gap`, not stacked margins.
- **Cards, tables and diagrams** — these carry the argument (a 3-card cause layout, a two-column gap analysis, a 5-step workflow, three data tables). Make them feel designed, not defaulted: considered borders, layered surfaces, real alignment. Numbers in tables must stay `tabular-nums` and right-relationships must stay scannable.
- **A quiet sense of motion** — the deck already has a drifting-particle canvas background and a count-up. You may add restrained slide-entry transitions. Do not add anything that distracts during a live talk, and respect `prefers-reduced-motion`.
- **One memorable visual idea.** The strongest metaphor available: a light being switched off, the threshold of a door, the moment of decision before leaving. Express it in CSS/SVG/canvas, not by inventing image files.

**Constraints that come from the room:**
- Rendered on a **projector at 16:9**, viewed from several metres away — small light-grey text on dark ground disappears. Body text should not go below ~15px effective at 1080p; keep contrast strong.
- Must also survive being opened on a phone (a teammate will read speaker notes on mobile) — keep the existing responsive breakpoint working, no horizontal page scroll ever, wide tables get their own `overflow-x: auto`.
- Content must never overflow a slide vertically on desktop. Some slides are dense; solve density with layout and scale, never by deleting content.

## Definition of done

Open the file and verify: 12 slides, every original string present, all four images referenced correctly, keyboard + swipe + notes + fullscreen all work, no console errors, nothing clipped at 1920×1080 or on a 390px-wide phone, version reads `v0.3.0`.

Work until done — do not stop early, do not ask questions.
