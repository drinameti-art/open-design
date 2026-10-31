# Language learning app checklist

Run this before emitting `<artifact>`. P0 = must pass; P1 = should pass; P2 = nice to have.

## P0 — must pass

- [ ] **The interface speaks the learner's language.** Every button, tab, instruction, feedback line and tip is in the native language named in the brief (e.g. Albanian), with correct grammar and diacritics. Only study material is in the target language. No stray English UI strings.
- [ ] **Target-language content is accurate.** Every kana/kanji/word shows the right script, reading and meaning. When unsure of a word, use a simpler one you are sure of; never invent vocabulary or readings.
- [ ] **Respelling follows the native orthography.** Pronunciation hints spell target sounds the way the learner reads them (Albanian ← Japanese: `chi → çi`, `tsu → cu`, `ji → xhi`, `ya/yu/yo → ja/ju/jo`, `wa → ua`, long vowels doubled). Sounds whose respelling differs from romaji are marked.
- [ ] **The quiz works end to end.** Every question has exactly one correct option (watch for homophones such as お/を, both read "o"); selecting + Check shows correct/wrong feedback with an explanation in the native language; Continue advances; the flow reaches a result card. It cannot get stuck.
- [ ] **Fonts cover both scripts.** A Japanese face (e.g. Noto Serif JP / Noto Sans JP) for kana and kanji; the Latin face renders the native diacritics (ë, ç…). Inter / Roboto / system sans never serve as the display face for headlines.
- [ ] **No invented metrics.** Streaks, XP and progress are clearly in-app example state for the learner; no marketing claims like "learn Japanese in 30 days" or "10× faster".
- [ ] **No emoji as feature icons.** Use inline SVG icons or a single kana/kanji glyph as the mark.
- [ ] **No filler copy.** No lorem ipsum, no "Lesson 1 / Lesson 2" placeholders: use real unit names (greetings, numbers, a kana row).
- [ ] **`data-od-id` on the stage, each phone and each phone's regions.**
- [ ] **No `scrollIntoView()` calls.** It breaks the OD preview iframe.
- [ ] **Interactive controls are real `<button>`s**, with `aria-pressed` / `aria-live` where state or feedback changes.

## P1 — should pass

- [ ] **Four frames, four purposes:** cover, today/lesson path, quiz, script explorer. Not four copies of one screen.
- [ ] **One accent colour** (taken from the brand logo or DESIGN.md) used for the primary action and the current step; success uses green, errors use the accent or red, nothing else competes.
- [ ] **The script explorer updates in place:** tapping a cell changes the detail card (glyph, reading, respelling, tip, example words).
- [ ] **Encouraging, adult tone.** Playful, not childish.
- [ ] **Brand logo used if supplied** in the stage wordmark and the cover hero; colours derived from it.

## P2 — nice to have

- [ ] **A pronunciation hint per tricky sound** (`chi`, `tsu`, `fu`, `r`) in the explorer.
- [ ] **Example words reuse vocabulary from the lesson path**, so the frames tell one story.
- [ ] **Respects `prefers-reduced-motion`.**
