# vectorvaultai

Marketing site for VectorVaultAI ("Persistent Memory for AI Apps" — vector memory layer positioned vs. Pinecone). Static HTML, no build step, deployed to Vercel.

## Structure
- `index.html` (~1374 lines) — landing page. Inline `<style>` + inline `<script>`, no external JS framework.
- `docs.html` (~342 lines) — docs page with sidebar nav, same inline-style pattern, separate `:root` color vars from index.html (don't assume shared styles).
- `.vercel/project.json` — Vercel project link (projectId, orgId, projectName: vectorvaultai). Deploys via Vercel, not a custom build script.
- No `package.json`, no `node_modules`, no build dir — this is plain static HTML/CSS/JS edited directly.
- Git remote: `github.com/mkam2599/vectorvaultai`, branch `main`.

## Working in this repo (token-saving notes)
- Both HTML files are self-contained (CSS + JS inline in the same file) — never need to hunt across multiple files for styling or behavior.
- Read only the relevant section via `offset`/`limit` instead of the whole file when making a small edit (files are 300–1400 lines).
- No `node_modules`/`dist`/`build` dirs exist here, so the project-wide "don't read massive build dirs" rule is moot for this repo — just don't read both full HTML files unless doing a full-page edit.
- Color tokens are CSS custom properties under `:root` near the top of each file's `<style>` block — check there first before grep'ing for color values.
- GA tag (`G-JNSXM77P5L`) is duplicated in both files' `<head>` — if changing analytics, update both.
