# MolineHome-Assets

Static branding assets for customizing the [Authentik](https://goauthentik.io/) login UI for MolineHome. The repo contains only static files under `public/` (logo SVG/PNG, banners, background images, and `public/assets/css/authentik.css`). There is no application source, package manager, build step, or test/lint tooling.

## Cursor Cloud specific instructions

- This repo has no dependencies, build, lint, or test tooling. There is nothing to install; the update script is intentionally a no-op.
- The "product" is the static assets in `public/`, intended to be served at `/assets/...` and consumed by an Authentik instance (System → Brands / custom CSS). `authentik.css` references assets by absolute paths (e.g. `/assets/backgrounds/Highway-Aerial.JPG`), so any preview must be served from a server rooted at `public/` for those paths to resolve (opening files via `file://` will not resolve them).
- To run/preview locally in development, serve the assets with the built-in Python server (Python 3 and Node are preinstalled):
  - `cd public && python3 -m http.server 8080`
  - Then assets are available at e.g. `http://localhost:8080/assets/logos/molinehome-logo.svg` and `http://localhost:8080/assets/css/authentik.css`.
- Fully testing the theme in its real context (a styled Authentik login flow) requires a separate, running Authentik stack (server + worker + PostgreSQL + Redis), which is not part of this repo.
