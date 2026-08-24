# SOLYNTO Website

Static marketing site for SOLYNTO — a premium Nordic programmatic advertising platform (DSP) built for independent media agencies.

## Stack

Pure static HTML/CSS. No JavaScript, no build step, no cookies, no third-party analytics. The directory deploys as-is.

## Pages

| File | Purpose |
|---|---|
| `index.html` | Main single-page site: hero, platform, supply, agencies, white-label, CTA |
| `about.html` | Company story and founder background |
| `privacy.html` | Privacy policy (scoped to this website; the advertising platform is governed by separate client agreements) |
| `terms.html` | Terms of use |

Supporting files: `style.css` (design system), `favicon.svg` (Target mark), `og-image.png` (1200×630 social share card), `sitemap.xml`, `robots.txt`.

## Design system

- CSS variables in `:root` define the palette (warm off-white, sage green, ink) and spacing tokens
- Unified primitives: `.container` (+ `--mid` / `--narrow`), `.section` (+ `--soft` / `--tint` / `--dark`), `.section-head` (+ `--center` / `--narrow`)
- One responsive breakpoint at 900px
- Sticky header with `scroll-margin-top` anchor compensation

## Local preview

```bash
open index.html
```

or serve the directory with any static file server, e.g.:

```bash
python3 -m http.server 8000
```

## Deployment

GitHub Pages (repo must be public):

1. Repo settings → Pages → Source: Deploy from a branch → `main` / (root) → Save
2. The `CNAME` file in this repo pins the custom domain `solynto.com`
3. In Cloudflare DNS (solynto.com zone), add a CNAME: `solynto.com` → `boris-tang.github.io` (apex works via CNAME flattening)
4. GitHub issues the HTTPS certificate automatically after domain verification

`og:url`, `og:image` and `sitemap.xml` already reference `https://solynto.com/`.

## Notes

- All CTAs are `mailto:` links to `info@solynto.com` with prefilled subjects.
- The site intentionally uses no cookies or trackers; the privacy policy states this and scopes itself to the website only.
- `og-image.png` was rendered from a 1200×630 HTML template via headless Chrome; keep it in sync with brand assets (logo mark, tagline).
- Social platforms cache og data aggressively — finalize `og-image.png` before sharing links widely.
