# AI Context — Bardo Thodol

## What this project is

A static mini site for studying the Bardo Thodol (中阴得度 / The Tibetan Book of the Dead), a Nyingma terma text on death, the intermediate state (bardo), and rebirth. Spoke 9 under The Dharma Gate portal. Same architecture as other DharmaGate spokes — HTML + external CSS, no frameworks — but content is **English-only** (no Chinese primary text or language toggle).

## Current state (as of 2026-06-13)

- All 11 section pages written and complete (sections 1–11), plus index.html
- index.html: complete, 11-card grid grouped into 5 sections following the three-Bardo structure
- Each card uses `.chapter-num` and `.chapter-zh` spans (no `.chapter-en` — single language)
- docs/ folder being created now (ai-context.md, architecture.md, plan.md, roadmap.md, readme.md, audit-config.json, reference.py)
- Remaining: local review (manual browser check of speech/TTS, layout, links), then update DharmaGate's index.html and docs to mark Bardo Thodol "Active"

## Card pattern (English-only, no toggle)

```html
<div class="explanation-card">
  <p class="line"><strong>Primary English text excerpt</strong></p>
  <p class="explanation">English commentary</p>
</div>
```

## Summary pattern

```html
<section class="summary">
  <h2>Summary</h2>
  <p class="summary-zh">English summary (class retained for CSS compatibility)</p>
</section>
```

## Content sources

- **Primary text**: Original English content written for this site, following the structure and content of the Bardo Thodol (Tibetan: བར་དོ་ཐོས་གྲོལ་), with reference to the Evans-Wentz translation (public domain) for tone and content basis. Not copied verbatim.
- **Commentary**: Written for this site — contextual, accessible explanations of Vajrayana concepts (Buddha families, wisdoms, six realms, Knowledge-Holders, wrathful Herukas, Lord of Death/Mirror of Karma, etc.)

## Section map

| Section | Stage | Title |
|---------|-------|-------|
| section1 | Introduction | Introduction |
| section2 | Stage 1 | Chikhai Bardo — The Bardo of the Moment of Death |
| section3 | Stage 2 · Overview | Chonyid Bardo — The Onset of Karmic Visions |
| section4 | Stage 2 · I | Peaceful Deities, Days 1–2 |
| section5 | Stage 2 · II | Peaceful Deities, Days 3–4 |
| section6 | Stage 2 · III | Peaceful Deities, Days 5–6 |
| section7 | Stage 2 · IV | Day 7: The Knowledge-Holders |
| section8 | Stage 2 · V | The Wrathful Deities |
| section9 | Stage 3 · I | Sidpa Bardo — The Judgment of Karma |
| section10 | Stage 3 · II | Signs of Rebirth & Closing the Womb-Door |
| section11 | Conclusion | Modern Relevance of the Bardo Teachings |

## Section page nav pattern

- section1.html: `Contents` only (no prev)
- section11.html: `← Signs of Rebirth` · `Contents` only (no next)
- All others: `← previous title` · `Contents` · `next title →`

## Speech button

🔊 Listen — targets en-US/en-GB voice (rate 0.9)

## Portal link

Portal bar and footer both link to: `https://lugh3456.github.io/DharmaGate/`

## GitHub repo

Live URL (when deployed): `https://lugh3456.github.io/BardoThodol/`
Repository: `https://github.com/Lugh3456/BardoThodol`

## Pending DharmaGate updates (do not perform without asking — existing project)

- Remove "Coming soon" badge from Bardo Thodol card in DharmaGate/index.html
- Add `<a href="https://lugh3456.github.io/BardoThodol/" class="card-link">Explore Bardo Thodol →</a>`
- Update DharmaGate/docs/roadmap.md and docs/ai-context.md to mark Bardo Thodol as "Active"
- Per working-preferences.md: create dated backup of DharmaGate files before editing
