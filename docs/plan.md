# Plan — Bardo Thodol

## Approved plan (executed)

1. Set up project folder & css (copied shared DharmaGate design tokens from SuttaNipata) — done
2. Draft index.html — done, then rewritten English-only
3. Write section1 (Introduction) and section2 (Chikhai Bardo) — done, then rewritten English-only after CK's request to go fully English
4. Review with CK before continuing — done, approved
5. Write remaining sections 3–11 (English-only template) — done
6. Build docs/ folder (this step) — in progress
7. Local review / verification before deployment — pending
8. Update DharmaGate's index.html + docs/roadmap.md + docs/ai-context.md to mark Bardo Thodol "Active" — pending, requires asking CK first (existing project, dated backup required)
9. Deploy to GitHub Pages — pending

## Key decision: English-only

CK requested ("Can change totally to english?") that the site be English-only rather than bilingual Chinese-primary/English-toggle, while remaining part of the DharmaGate portal (portal bar/footer links retained). Sections 1–2 and index.html were rewritten accordingly; sections 3–11 followed the same template from the start.

## Notes

- No Chinese Tripitaka version of this Tibetan text exists, so the original bilingual approach (writing new Chinese explanations alongside an existing Chinese source, as with SuttaNipata's non-T0198 vaggas) was not applicable — this became moot once the English-only decision was made.
- Card pattern: `.explanation-card` with `p.line` (bold excerpt) and `p.explanation` (commentary), no toggle.
- Summary uses `p.summary-zh` class (retained for CSS compatibility) but contains English text.
