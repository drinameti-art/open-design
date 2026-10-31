---
name: language-learning-app
description: |
  A multi-frame language-learning mobile-app prototype — four phone frames on
  a warm showcase stage, with the interface written in the learner's native
  language. Frame 1: cover / value prop, Frame 2: today's lesson path with
  streak and daily goal, Frame 3: a working multiple-choice quiz, Frame 4: a
  script / alphabet explorer with native-language pronunciation hints. Use
  when the brief asks for a "language learning app", "vocabulary app",
  "flashcards", "kana / alphabet trainer", "learn Japanese", or a course
  aimed at speakers of a specific native language (e.g. Albanian learners
  of Japanese).
triggers:
  - "language learning app"
  - "learn japanese"
  - "japanese app"
  - "vocabulary app"
  - "flashcard app"
  - "hiragana"
  - "kana trainer"
  - "alphabet trainer"
  - "duolingo-style"
  - "mëso japonisht"
  - "aplikacion për gjuhë"
  - "语言学习"
od:
  mode: prototype
  platform: mobile
  scenario: education
  preview:
    type: html
    entry: index.html
  design_system:
    requires: true
    sections: [color, typography, layout, components]
  craft:
    requires: [state-coverage, animation-discipline]
  example_prompt: "Design a Japanese-learning app for Albanian speakers — multi-screen mobile prototype with the UI in Albanian: cover, today's lesson path with streak, a working quiz, and a hiragana explorer that spells Japanese sounds the Albanian way (chi → çi, tsu → cu)."
---

# Language Learning App Skill

Produce a multi-screen mobile prototype on a single showcase page. Four
phone frames side-by-side, each one a distinct moment in a learner's day.
The whole interface speaks the **learner's native language**; only the
target language appears as study material.

## Workflow

1. **Read the active DESIGN.md** (injected above). Language apps read as
   calm and encouraging — one confident accent, generous paper surfaces,
   and type that renders the target script beautifully.
2. **Pin the language pair** from the brief: the learner's native language
   (UI language) and the target language (study content). Everything the
   app *says* — buttons, tabs, feedback, tips — is in the native language,
   written with correct grammar and diacritics. Never leave UI copy in
   English when the brief names another native language.
3. **Pick fonts that cover both scripts.** For Japanese targets use a JP
   face (e.g. Noto Serif JP / Noto Sans JP) for kana and kanji; confirm the
   Latin face carries the native language's diacritics (ë, ç, ş, ő, …).
4. **Find the bridge.** The signature feature is a pronunciation hint that
   respells target-language sounds in the native orthography. For
   Albanian → Japanese: `chi → çi`, `tsu → cu`, `ji → xhi`, `ya/yo → ja/jo`,
   `w → u`, long vowels doubled (`arigatō → arigatoo`). Highlight the sounds
   where the native spelling differs from Hepburn romaji.
5. **Stage** — full-bleed warm page with a soft spotlight. A caption row
   above the phones: "HI-FI PROTOTYPE · IPHONE" left, brand wordmark right.
   When the brief supplies a logo, use it in the wordmark and the cover
   hero, and derive the accent / paper colors from it (the baked example,
   Shqiponisht, ships its torii mark as `assets/shqiponisht-mark.png`).
6. **Phones** — four 360×760 frames in a row (wrapping on narrow
   viewports): 12px black bezel, ~56px outer radius, dynamic-island notch,
   status bar, bottom tab bar with 4 tabs (Today, Script, Vocabulary,
   Profile — translated). Active tab in accent.
7. **Phone 1 — cover**: eyebrow, big headline in the native language,
   one large target-script glyph or word as the hero, a 1–2 sentence
   promise, primary CTA ("Start") and a secondary "I already know some".
8. **Phone 2 — today / lesson path**: greeting with the learner's name,
   streak flame + day count, daily-goal ring (e.g. 15 / 20 XP), then a
   vertical path of units (done / current / locked) with real unit names
   (Hiragana 1, Greetings, Numbers 1–10, Katakana, At the restaurant).
   One "Continue" CTA on the current unit.
9. **Phone 3 — quiz (must work)**: progress bar + question counter, a
   prompt in the native language, four answer options showing the target
   script, romaji and the native respelling. Selecting + "Check" shows
   correct / wrong feedback with an explanation; "Continue" advances
   through 4–5 real questions and ends on a result card with XP earned.
10. **Phone 4 — script explorer**: a large glyph card (glyph, reading,
    native respelling, mnemonic, two example words with translations) above
    a grid of the first rows of the syllabary. Tapping a cell updates the
    card. Cells whose native spelling differs from romaji get an accent dot.
11. **Write** a single HTML document:
    - `<!doctype html>` through `</html>`, CSS and JS inline.
    - No images — CSS gradients and inline SVG for icons.
    - `data-od-id` on the stage, each phone, and each phone's regions.
    - Interactive states use `aria-pressed` / `aria-live` so feedback is
      announced; buttons are real `<button>` elements.
12. **Self-check**:
    - Four frames, four different purposes — not copies of one screen.
    - Every UI string is in the native language; every target-language
      item is accurate (script, reading, meaning).
    - The quiz cannot get stuck: every question has exactly one correct
      answer and the flow reaches its result card.
    - Encouraging, adult tone — playful, not childish.

## Output contract

Emit between `<artifact>` tags:

```
<artifact identifier="app-slug" type="text/html" title="Mobile — App Name">
<!doctype html>
<html>...</html>
</artifact>
```

One sentence before the artifact, nothing after.
