# AGENTS.md

## Architecture

This project is a single static HTML file (`index.html`) — a wedding invitation page. There is no build tooling, bundler, or framework: styles are in an inline `<style>` block, behavior is in an inline `<script>` block at the bottom of `<body>`, and all media (hero/family photos, background music track) are embedded as base64 `data:` URIs directly in the markup. `netlify.toml` publishes the repo root as-is.

## Key sections in `index.html`

- `#opening` — the full-screen intro overlay shown on load: a circular badge with the couple's initials that splits in half (rotateY) and two full-height `.gate-door` panels that slide apart left/right, revealing the page behind them like an opening gate.
- `#heroPanel` and the panels below it (`bismillah`, `love`, `family`, `date-panel`, `venue`, `dua`) — the scrollable invitation content, revealed with `IntersectionObserver`-driven fade/slide-in (`.reveal` / `.stagger` classes).
- `#musicBtn` / `#bgMusic` — background music control. The button icon (`.music-icon`) spins continuously via CSS animation regardless of play state; the underlying `<audio>` element is nudged to autoplay as early as possible (on script execution, `DOMContentLoaded`, and `load`), with a graceful fallback to the first user tap/click/scroll/key press since browsers block unmuted autoplay without a user gesture.

## Conventions

- Keep everything in one file unless a genuinely reusable asset needs extracting — this project is intentionally a single portable HTML document.
- CSS is unminified but written densely (no per-rule line breaks) to match the existing style; follow that when editing nearby rules rather than reformatting the whole block.
- Base64 media blobs are long single lines — avoid full-file reads/edits that touch them; target edits with `Edit` using surrounding non-data text as anchors.
