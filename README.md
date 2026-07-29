# מי ישן איפה? · Kid Place Decider

A single-page Hebrew web app for randomizing where the kids sleep at grandma and grandpa's house.

**Live:** https://liorn.github.io/kid-place-decider/

## What it does

1. **ילדים** — enter the kids' names.
2. **מקומות** — enter the sleeping spots as *zone · spot* (e.g. `מיטה תחתונה · צד ימין`). The zone is what makes constraints like "not together on the lower bed" possible.
3. **אילוצים** — pick the kind of rule first, then fill in the sentence:
   - 👫 **ילדים שלא ישנים יחד במיקום מסוים** — two kids who can't share a zone (a specific zone, or none at all).
   - 🚫 **ילד שלא ישן במקום מסוים** — a kid ruled out of a whole zone or a single spot.
   - 📌 **מקום קבוע לילד** — a spot reserved for one kid; nobody else can get it.
4. **הגרלה** — a ~10 second colorful full-screen show: countdown, drumroll, spinning names, one-by-one reveal with confetti and sound, then a final celebration screen that stays up until you close it.

## Notes

- Single file, no build step, no dependencies (fonts come from Google Fonts).
- All sound is synthesized with the Web Audio API — no audio files. Toggle it with the 🔊 button.
- Kids, spots, constraints and the sound preference are stored in `localStorage`. The drawn result is **not** persisted — every reload starts fresh.
- The randomizer draws uniformly at random and rejects arrangements that break a constraint; if the constraints are tight it falls back to a backtracking search, and it says so clearly when no valid arrangement exists.
