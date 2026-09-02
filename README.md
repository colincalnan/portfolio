# Colin Calnan / Selected work

The portfolio page. One HTML file, no build step at runtime, no external requests.

## How it works

`index.src.html` is the source of truth. It carries `{{IMG:name}}` tokens. The build inlines every asset in `assets/` as a base64 data URI and writes `index.html`, so the published page loads nothing from anywhere.

```
node ../../scripts/portfolio/build.mjs
```

Build script lives at `scripts/portfolio/build.mjs` in the parent workspace, not in this repo.

To swap an image, drop a new `<name>.jpg` into `assets/` and rebuild. To resize one from the archive:

```
sips -s format jpeg -Z 900 <source> --out assets/<name>.jpg
```

## Design

Built on the Bold Talks design system: near-black ground, cobalt and electric blue, peach, cyan, orange, yellow. Zero radii, no shadows, committed dark, single theme. Bebas Neue cannot load here because the page makes no external requests, so the display role is a heavy tightly tracked uppercase grotesk reaching for the same energy.

## Versioning

`main` is what is published. Do experiments on a branch and merge only what survives.
