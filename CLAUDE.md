# Redline

A race-style focus timer for one task at a time. It's for ADHD-friendly focus: you type the single task you're doing right now, then race 3 rivals to the finish line. Martin keeps his todo lists on paper, so this app is only about the current task and a time log. Don't add planning features (projects, goals, checklists) unless asked; an earlier version had them and they were too heavy.

## Stack
- Plain `index.html` (inline CSS + JS), no build step. Keep it that way unless there's a clear reason to change.
- PWA: `manifest.webmanifest`, `sw.js` (network-first cache), `icon-192.png`, `icon-512.png`.
- State lives in `localStorage` key `redline.v2`. It imports real entries from `redline.v1` on first load.
- Hosting target: GitHub Pages from `main` / root.

## Behaviour to preserve
- Timer counts down, then keeps going into red minus time (overtime). Stopwatch mode has no finish line; everyone runs 25-min laps.
- Your racer moves with the clock and reaches the line at your planned time. Rivals move at fixed multiples of the plan (PACE: chill/normal/hard). Pressing Done early beats the rivals who haven't finished.
- +5 min extends only your time, not the rivals'.
- "Just log it" adds a finished entry (status `logged`) without starting a race.
- Breaks: countdown + move-around prompt, also run into minus time.
- Scenes: river (ducks), circuit (cars), space (rockets), calm (low stimulation, slow motion).
- Keyboard: Space pause, D done, + add 5 min, N brain dump.
- Brain dump (`S.queue`): a parked list for later tasks. Start buttons are hidden while a task runs, on purpose, so you do not jump tasks mid-race.
- Respect `prefers-reduced-motion`.

## When editing
- Whenever `index.html` changes, bump `VERSION` (semver: minor for features, patch for fixes) in BOTH `index.html` and `sw.js` so installed copies update and the Scene drawer's version check sees it. Tell Martin the new version number.
- Test with `npx serve .` and open http://localhost:3000.
