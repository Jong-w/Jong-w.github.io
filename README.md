# Jongwon Kim Academic Homepage

This is a complete Jekyll / GitHub Pages site based on the official `yaoyao-liu/minimal-light` remote theme, with a custom homepage layout inspired by the user-provided Hanchu Zhou homepage screenshot.

## Deploy

1. Upload **the contents** of this folder to the root of the `Jong-w.github.io` repository.
2. Delete old root `index.html`, if present. The site uses `index.md`.
3. In Settings → Pages, use **Deploy from a branch**, `main`, `/(root)`.
4. Wait for the GitHub Pages Actions build to complete, then visit `https://jong-w.github.io/`.

## Edit

- `_layouts/homepage.html` — profile and section structure.
- `assets/css/custom.css` — all design and responsive styling.
- `_data/publications.yml` — publication data, Paper links and representative images.
- `assets/` — portrait, figures, CV, and paper PDF.
- `_config.yml` — Jekyll settings and contact information.

The homepage is intentionally a custom layout, not the unmodified upstream Minimal Light appearance. It keeps the upstream remote theme setting while overriding the layout and CSS.

AROMMA Paper points to arXiv; TH-EFUN Paper points to DBpia. Other papers have no Paper button unless a verified URL is supplied.
