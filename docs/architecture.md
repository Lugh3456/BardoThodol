# Architecture — Bardo Thodol

## Overview

Bardo Thodol (The Tibetan Book of the Dead) is a **static multi-page mini site** hosted on GitHub Pages. It is spoke 9 in the hub-and-spoke model under The Dharma Gate portal, following the same architecture as other DharmaGate scripture sites — but content is **English-only** (no Chinese primary text or toggle).

- The **hub** is [The Dharma Gate](https://lugh3456.github.io/DharmaGate/)
- This **spoke** is a standalone repository with its own index and 11 section pages
- The hub links to this site; this site links back via portal bar and footer

HTML + external CSS only. No frameworks, no build tools.

---

## Folder Structure

```
BardoThodol/
  index.html         <- intro page with 11 section cards, grouped by the 3 bardos
  section1.html       <- Introduction
  section2.html       <- Chikhai Bardo
  section3.html       <- Chonyid Bardo overview
  section4.html       <- Peaceful Deities, Days 1–2
  section5.html       <- Peaceful Deities, Days 3–4
  section6.html       <- Peaceful Deities, Days 5–6
  section7.html       <- Day 7: The Knowledge-Holders
  section8.html       <- The Wrathful Deities
  section9.html       <- Sidpa Bardo — The Judgment of Karma
  section10.html      <- Signs of Rebirth & Closing the Womb-Door
  section11.html      <- Conclusion — Modern Relevance
  css/
    style.css         <- all styles (copied from SuttaNipata, shared DharmaGate tokens)
  docs/
    readme.md
    architecture.md   <- this file
    ai-context.md
    plan.md
    roadmap.md
    audit-config.json
    reference.py
  Backup/             <- dated backups
```

---

## Page Structure — Index

```
<portal-bar>           <- link back to DharmaGate
<header.site-header>   <- "Bardo Thodol" title, English subtitle, tradition label
<section.intro>        <- English description of the text
<main>
  <section.vagga-section> x5   <- one per group:
    h2                          <- group name (e.g. "Chonyid Bardo")
    .chapter-grid               <- section cards for that group
      a.chapter-card            <- chapter number + title (no Chinese)
<footer>
```

---

## Page Structure — Section Pages

```
<portal-bar>                <- link back to DharmaGate
<header.section-header>     <- section title, header-zh subtitle (English), nav links
<main.section-container>
  section.full-text         <- full English text + 🔊 Listen button
  section.line-explanation
    h2                      <- "Reading the Text"
    .explanation-card       <- one per passage:
      p.line                <- primary English text excerpt (bold)
      p.explanation         <- English commentary
  section.summary
    h2                      <- "Summary"
    p.summary-zh            <- English summary (class retained for CSS compatibility)
<script>                    <- speak() only (no toggleDetail — single-language)
<footer>
```

---

## CSS Architecture

All styles in `css/style.css` — copied verbatim from SuttaNipata. Same design tokens throughout.

---

## Chapter Grid (index.html)

Grouped layout following the three-Bardo structure:
1. Introduction (section1)
2. Chikhai Bardo (section2)
3. Chonyid Bardo (section3–8)
4. Sidpa Bardo (section9–10)
5. Conclusion (section11)

Each card shows:
- `.chapter-num` — section number / stage label
- `.chapter-zh` — section title (English; class retained for CSS compatibility)

---

## Design Tokens

Same as all DharmaGate spokes.

| Token | Value | Usage |
|-------|-------|-------|
| `--red` | `#b83232` | Primary accent, translations |
| `--red-light` | `#d44e4e` | Hover states, headings |
| `--saffron` | `#c8820a` | Chapter number labels |
| `--saffron-lt` | `#e09c2a` | Portal bar links |
| `--ink` | `#1c0f0f` | Header/footer backgrounds |
| `--bg` | `#f7f0e6` | Page background |
| `--text` | `#2d1f1f` | Body text |
| `--muted` | `#7a6060` | Secondary text |
| `--border` | `#e0d0c8` | Card borders, dividers |

---

## Nav Pattern

- section1.html: `Contents` only (no prev)
- section11.html: `← Signs of Rebirth` · `Contents` only (no next)
- All others: `← previous section` · `Contents` · `next section →`

---

## Speech Synthesis

🔊 Listen button reads the full primary text via `speechSynthesis`. Targets an en-US/en-GB voice, rate 0.9.

---

## External Dependencies

Google Fonts:
- Noto Serif SC — headings (retained for visual consistency with other DharmaGate spokes)
- Noto Sans SC — body text, buttons

No other external dependencies.

---

## Hosting

GitHub Pages via `lugh3456` account.
Repository name: `BardoThodol`
Live URL (when deployed): `https://lugh3456.github.io/BardoThodol/`
