# Whiskey Red Saloon — deploy bundle

Static site. No build step, no images, no dependencies beyond Google Fonts (CDN). Drop into the repo root and connect Cloudflare Pages.

## Structure

```
index.html              → Tier Demo / sales tool  (whiskeyredsaloon.com)
site/index.html         → public landing page     (whiskeyredsaloon.com/site/)
```

- All photo slots are intentional on-page placeholders — there are no image files to ship.
- Fonts load from Google Fonts (Oswald, Caveat, Courier Prime). Nothing else external.
- The landing page at `/site` is self-contained and references no local assets.

## Cloudflare Pages settings

- Framework preset: **None**
- Build command: **(blank)**
- Build output directory: **/** (root)

## Custom domain

Pages project → Custom domains → add `whiskeyredsaloon.com` + `www`.
DNS already lives in Cloudflare, so records + SSL auto-provision.
