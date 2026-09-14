# @konneal/ui-starter

The minimal branded frontend for a Konneal publisher deployment. It
consumes [`@konneal/client`](https://github.com/konneal/client) — the
wire types, the SSE ask client, the escape-first markdown renderer, the
citation chips, the typed unit blocks, the document pane — and leaves
everything visual to you.

    npm install
    npm run dev

## What is yours

- `src/styles/global.css` — the theme tokens (paper, ink, rule,
  accent, mono font). Every contract renderer reads these; swap them
  and the whole UI rebrands.
- `src/pages/index.astro` — the page chrome (header, credit line,
  layout). Replace `PUBLISHER` with your name.
- `src/components/Chat.vue` — the conversation state and layout. The
  whole contract surface is three imports from `@konneal/client`; the
  rest of the file is ordinary Vue you own.

## Wiring to your deployment

The chat calls the engine's API at `/api/ask` (same origin). Deploy
the built `dist/` as the worker's assets (the
`create-publisher` scaffold's wrangler template already points at
`site/dist` — clone this starter there, or set
`[assets] directory` to this build).

BSD-3-Clause. Part of the Konneal engine ecosystem
(github.com/konneal).
