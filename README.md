# Shlokas & Mantras

A tap-to-play mantra board for kids. Tap a god, hear the mantra.

Nine deities — Ganesh, Shiv, Ram, Krishna, Hanuman, Balaji, Vitthal, Laxmi and Saraswati —
laid out in a fan, like the tabs on a sound book. No build step, no dependencies, one HTML file.

## Run it locally

Double-click `index.html`. That's it.

Or serve it, which is closer to how it behaves when hosted:

```
python3 -m http.server 8000
```

then open `http://localhost:8000`.

## Publish it

See [DEPLOY.md](DEPLOY.md) for GitHub Pages, start to finish.

## How it works

- Tap a god in the fan → the mantra plays and that deity takes the center stage.
- Tap the same one again, or the gold button, to pause and resume.
- Picking a new god stops the previous mantra automatically.
- The gold ring around the play button fills as the mantra progresses.
- Arrow keys move between gods; spacebar plays and pauses.

## Layout

One wide arc on laptops and tablets. On narrow phones it splits into a two-row bouquet so
every face stays big enough for small fingers. Sizes are measured from the live window, so
nothing clips in portrait or landscape, from 320px up.

## Adding another god

1. Add `assets/img/Name.webp` (about 640px square, transparent background),
   `assets/img/Name-sm.webp` (about 260px), and `assets/audio/Name.mp3`.
2. Add one line to the `GODS` array in the `<script>` block of `index.html`:

```js
{id:'Durga', en:'Durga', dev:'दुर्गा', color:'#E0483F'},
```

`id` must match the filenames. `color` is the glow behind the deity on the center stage.

## Assets

Images are cut out to transparent PNG-alpha WebP at 640px and 260px. Audio is 96 kbps mono
MP3 — plenty for spoken mantras and light enough to stream over a phone connection. The whole
site is about 16 MB.
