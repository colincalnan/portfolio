# Selected work

Colin Calnan. Published at **https://colincalnan.github.io/portfolio/**

One HTML file. Every image is inlined as a data URI, so the page makes zero external
requests and works offline.

## Building

`index.src.html` is the source of truth. It carries `{{IMG:name}}` tokens for the
images in `assets/` and `{{CSS:name}}` tokens for the design system in
`projects/ground/`. The build inlines all of it and writes `index.html`.

```
node scripts/portfolio/build.mjs
```

The build script and the design system live in the parent workspace, not in this repo.

## Design

Built on Ground, a small design system: semantic tokens, three themes, and a
guidance document written for an agent to read. This page ships the night theme,
which is the Bold Talks palette: near-black ground, cobalt and electric blue,
peach, cyan, orange, yellow. Zero radii, no shadows.
