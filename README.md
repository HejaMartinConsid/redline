# Redline

A focus timer that turns the one task you're doing right now into a race.

- Type the task, pick a length (or Stopwatch), and race three rivals to the finish line.
- When time is up, the clock keeps running as red minus time.
- Take breaks with prompts to get up and move around.
- A time log shows what you did today and can be copied as CSV. Use "Just log it" for tasks you forgot to time.
- Scenes: Duck pond, Grand prix, Rocket run, Quiet lake.

It's plain HTML with no build step. Data is saved in `localStorage`, and it installs as a PWA (manifest + service worker).

## Run locally

```sh
npx serve .
```

## Deploy (GitHub Pages)

Go to Settings → Pages → Deploy from branch → `main` / root. Then open the Pages URL in Chrome and click the install icon in the address bar.

When you change `index.html`, bump `CACHE` in `sw.js` so installed copies update.
