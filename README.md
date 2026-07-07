# Wedding Invitation — Anfas & Ijasa

A single-page digital wedding invitation for Mohamed Anfas and Fathima Farhath Ijasa. It is a self-contained static HTML page (all styles, script, images, and background music are inlined) with a floral, botanical theme, scroll-triggered reveals, and an animated opening sequence.

## Tech

- Plain HTML/CSS/JavaScript — no build step or framework
- Google Fonts (Cormorant Garamond, Montserrat, Noto Naskh Arabic)
- Images and audio embedded as base64 data URIs directly in `index.html`

## Running locally

Open `index.html` directly in a browser, or serve the folder with any static server, e.g.:

```bash
npx serve .
```

## Deployment

Deployed as a static site on Netlify (`netlify.toml` publishes the project root, no build command needed).
