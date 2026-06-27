# Webidian

![Webidian logo](./public/android-chrome-192x192.png)

A browser-based, local-first Markdown knowledge base — Obsidian's connected-notes
experience, with nothing to install and nothing to sign up for.

Your notes are plain `.md` files that stay on your device. Link them with
`[[wikilinks]]`, see automatic backlinks, and explore them as a graph — all in the
browser, fully offline.

> **Status:** early development (MVP). Single-device, desktop-browser first.
> Webidian is a clean-room project compatible with Obsidian's _file format and core UX_.
> It is not affiliated with or derived from Obsidian.

## Features (MVP)

- Open a local folder as a vault, or create an in-browser vault
- Markdown editor with live-preview-style editing + a reading view
- `[[wikilinks]]` with autocomplete and navigation
- Automatic backlinks panel
- Interactive graph view
- Client-side full-text search
- Light / dark themes
- Offline support (installable PWA) and `.zip` export

## Tech stack (Subject to change)

TypeScript · React 19 (React Compiler) · Vite · CodeMirror 6 · Zustand · d3-force ·
MiniSearch · vite-plugin-pwa. Linting with Oxlint, tests with Vitest.

## Getting started

Requires [Node.js](https://nodejs.org/) (LTS) and pnpm.

```bash
git clone https://github.com/webidian/webidian.git
cd webidian
pnpm install
pnpm run dev
```

Then open the printed local URL (usually http://localhost:5173).

> Folder-based vaults use the File System Access API, available in desktop
> Chromium browsers (Chrome / Edge). On Firefox and Safari, Webidian falls back
> to an in-browser vault — export regularly.

## Scripts

| Command         | What it does                 |
| --------------- | ---------------------------- |
| `pnpm run dev`   | Start the Vite dev server    |
| `pnpm run build` | Production build             |
| `pnpm test`      | Run tests (Vitest)           |
| `pnpm run lint`  | Lint with Oxlint (fast)      |
| `pnpm run check` | Type-check + type-aware lint |

## Project layout

```
src/
  core/        framework-agnostic engine (storage, markdown, indexing, search) — no React
  editor/      CodeMirror 6 setup + live-preview extensions
  features/    React panels (explorer, backlinks, graph, search)
  store/       Zustand state
docs/          spec and design notes
```

## Contributing

Early days — see `CONTRIBUTING.md` once it lands. For now: open an issue before
starting non-trivial work, and keep `src/core/**` free of React imports.

## License

MIT — see [LICENSE](LICENSE).
