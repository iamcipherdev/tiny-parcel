# choti khushi — a tiny parcel of joy, made slowly by hand

An original virtual-gift website: hand-craft 1–5 tiny digital gifts in playful
maker minigames, seal a virtual parcel, and share it as a link. The whole
parcel (names, gift payloads, wrapping) is encoded as compact JSON → base64 in
the URL hash — **no backend, no account, free forever.**

Live: https://iamcipherdev.github.io/tiny-parcel/

## the gifts

| gift | maker | stored as |
|------|-------|-----------|
| ✉️ letter | envelope opens/shuts (CSS), ruled paper, 5 colours | `{e, x}` — envelope idx + text |
| ⭐ sticker | draw canvas (6 inks, 3 brushes, undo) → die-cut preview + matte/gloss/holo finish | strokes as int point arrays |
| 🎵 tune | 16-step × 5-note (A/G/E/D/C) grid sequencer, WebAudio, 3 presets | 80-char bitstring |
| 🔑 keychain | oval/rect charm, 5 resins, star/heart/sprinkle filling, foil-emboss drawing, shake | shape/resin/fill idx + emboss strokes |
| 🧵 stitch | 11×11 cross-stitch grid, flower/star/heart motifs or free, unpick | coordinate list |

## routes (hash SPA, single `index.html`)

- `#/` — home
- `#/make` — the making table
- `#/seal` — wrap + tape picker
- `#/sent` — share link + torn packing receipt (time spent per gift)
- `#/b/<base64>` — open a parcel

## design

paper-craft, warm & handmade: cream `#faf7f2`, ink `#1a1a1a`, pastel
accents, tilted cards, pill buttons, dotted details. fonts: Pinyon Script
(wordmark), Oswald (headlines), Special Elite (typewriter labels).
mostly-lowercase aesthetic.

## run locally

```sh
cd tiny-parcel && python3 -m http.server 8000
# open http://localhost:8000/
```

## notes

- all payloads are vector-based (strokes, coordinates, bitstrings) so links stay short.
- a corrupt link shows "this parcel got lost in the mail" instead of crashing.
- original work — concept inspired by the "tiny internet parcel" idea, all
  name/branding/microcopy written from scratch.
