# Pulse — Understand-Anything dashboard

Interactive knowledge graph of the **Pulse (Productivity Tracking) developer guide**: the Developer Feature Guide, Data Model and Build Plan PDFs, the Build Tasks workbook, the database schema SQL and the 28 HTML wireframes (33 files).

The graph has 131 nodes, 674 links, 8 layers and a 14-step guided tour. It was generated on 29 Oct 2026 with the [Understand-Anything](https://github.com/Egonex-AI/Understand-Anything) Claude Code plugin (v2.9.8).

## What is in this repo

This is a **pre-built static site**, so there is no build step. The site lives in `public/`:

| Path | What it is |
|---|---|
| `public/index.html`, `public/assets/` | The Understand-Anything dashboard, built in demo (static) mode |
| `public/knowledge-graph.json` | The Pulse knowledge graph the dashboard loads |
| `public/meta.json`, `public/config.json` | Analysis metadata and settings |
| `netlify.toml` | Netlify settings: no build, publish `public/` |
| `vercel.json` | Vercel settings: no framework, output `public/` |
| `LICENSE` | Understand-Anything's MIT licence, which covers the dashboard code |

## Deploy on Netlify

Import the repository and deploy. `netlify.toml` overrides the build settings in the Netlify UI: it runs a no-op build command and publishes `public/`.

## Deploy on Vercel

1. In Vercel, choose **Add New → Project** and import this repository.
2. Set **Framework Preset** to **Other**, and leave the build command and output directory empty. `vercel.json` already points Vercel at `public/`.
3. Deploy. The dashboard opens at the site root.

## Update the graph

1. Re-run `/understand-anything:understand` on the developer guide folder.
2. Replace `public/knowledge-graph.json` and `public/meta.json` with the new files from `.ua/`.
3. Commit and push. Netlify or Vercel redeploys automatically.

## Caveats

- Links between screens and tables (*reads from* / *writes to*) were inferred by AI from what each wireframe shows. Treat them as pointers. The PDFs and the SQL file are the source of truth.
- The graph does not cover the 65 PNG screenshots, or the later database migrations (0003–0010) recorded in the Build Tasks log.
- The file viewer shows no source text, because the original files are not included in this repo.
