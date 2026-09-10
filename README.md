# Selected work

Colin Calnan. Published at **https://colincalnan.github.io/portfolio/**

A 69KB HTML file with the design system inlined, and its images served alongside it
from `assets/`. Nothing is loaded from another domain.

Images used to be inlined as data URIs too. That capped how sharp any of them could
be, because everything had to be squeezed small enough to keep one file openable, so
the page ended up declaring sizes larger than the files it shipped and the browser
upscaled them. They are full resolution now, 5.9MB in total, which is fine to serve
and absurd to inline.

## Building

`index.src.html` is the source of truth. It carries `{{IMG:name}}` tokens for the
images in `assets/` and `{{CSS:name}}` tokens for the design system in
`projects/ground/`. The build inlines all of it and writes `index.html`.

```
node scripts/portfolio/assets.mjs     # regenerate images from their originals
node scripts/portfolio/build.mjs      # write index.html
```

`assets.mjs` holds the manifest: for each image, where the original lives, how the
composites are assembled, and the width it is written at. Every image is generated at
at least twice the size the page draws it, and `build.mjs` fails if the HTML declares
a size the file does not have.

The build script and the design system live in the parent workspace, not in this repo.

## Design

Built on Ground, a small design system: semantic tokens, three themes, and a
guidance document written for an agent to read. This page ships the night theme,
which is the Bold Talks palette: near-black ground, cobalt and electric blue,
peach, cyan, orange, yellow. Zero radii, no shadows.

## Build pages

`builds/` holds one live page per build: what it is, how it works, the media, and what it still gets wrong. Plain HTML sharing `builds/builds.css`, which is the Bold Talks structure in the teal palette from the loops tutorial (cream and teal in light, deep teal in dark). Unlike the main page, running text has no max-width, by choice.

- `builds/foot-stomper/`: wearable BLE-MIDI kick drum
- `builds/gig-splitter/`: gig video to per-song reels
