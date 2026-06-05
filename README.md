# Whiskey Red Saloon — deploy bundle

Static site. No build step. Drop these into the repo root and connect Cloudflare Pages.

## Structure
```
index.html              → public site (whiskeyredsaloon.com)
demo/index.html         → Tier Demo / sales tool (whiskeyredsaloon.com/demo/)
prepared-photos/        → image library (referenced by index.html, relative paths)
```
- Photo paths are relative (`prepared-photos/...`) and resolve from the root `index.html`.
- The demo references no local images — safe to move/rename/gate independently.
- Fonts load from Google Fonts CDN (Oswald, Caveat, Courier Prime). No local font files needed.

## Cloudflare Pages settings
- Framework preset: **None**
- Build command: **(blank)**
- Build output directory: **/** (root)

## Custom domain
Pages project → Custom domains → add `whiskeyredsaloon.com` + `www`.
DNS is already in Cloudflare, so records + SSL auto-provision.

## Open decisions (make in Claude Code)
- Whether `/demo/` should be public, moved to an unguessable path, or gated behind Cloudflare Access.
- Optional: `404.html`, a `/tier-demo` → `/demo` redirect, self-hosting the fonts.
