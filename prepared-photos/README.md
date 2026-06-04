# Prepared Photo Library

This folder contains pre-cropped assets for agents to use when generating Whiskey Red Saloon hero slides, cards, event sections, proof-of-life sections, and campaign mockups.

The goal is to prevent future agents from doing lazy or incorrect cropping. Use these files before going back to `raw-facebook-export/`.

## Use This First

- Machine-readable manifest: `prepared-photos/manifest.json`
- Source facts and campaign context: `strategy/facebook-programming-source.md`
- Original/raw sources: `raw-facebook-export/` and selected root-level image files

## File Naming

Files are named by subject, use case, and dimensions:

```txt
prepared-photos/<category>/<descriptive-subject>-<variant>-<width>x<height>.png
```

Examples:

```txt
prepared-photos/people/bartender-pouring-don-julio-desktop-1200x600.png
prepared-photos/events/line-dancing/crowded-dance-floor-green-light-mobile-900x1200.png
prepared-photos/food-drink/pizza-wings-on-bar-card-600x450.png
```

## Variants

- `desktop-1200x600`: Wide 2:1 crops for desktop hero slides and wide bands.
- `mobile-900x1200`: Vertical 3:4 crops for mobile heroes, mobile cards, and stacked layouts.
- `card-600x450`: 4:3 crops for cards, tiles, and proof-of-life sections.
- `square-900x900`: Square crops for grids, social-style cards, and flexible layouts.

Most photo entries have all four variants. `event-graphics` entries usually have only desktop, mobile, and card variants because they are flyers/graphics rather than photographs.

## Categories

- `atmosphere`: Busy bar, crowd, room energy, and general proof-of-life backgrounds.
- `people`: Bartenders, patrons, community groups, social moments, and recognizable human proof.
- `people/ticket-winners`: Giveaway winners and prize proof.
- `events/line-dancing`: Real line-dancing crowd and room shots.
- `events/opening-day`: Opening Day/mechanical bull material.
- `events/private-events`: Private line-dance and event-center evidence.
- `events/sports`: Sports/event partner material.
- `food-drink`: Food, drinks, menu, bar top, local libations.
- `game-room`: Game-room features from the Facebook export.
- `venue`: Exterior, interior, room, poster wall, empty bar.
- `event-graphics`: Cropped flyers and graphics. These are useful references, but they are not photos.

## Agent Selection Rules

- Prefer a real photo over an `event-graphics` file when the design needs proof of life.
- Use `desktop` files for desktop heroes and `mobile` files for mobile heroes; do not make future agents recrop unless absolutely necessary.
- For cards, prefer `card-600x450` or `square-900x900`.
- If overlaying text, inspect the chosen crop and place text in an area that does not cover faces, hands, drinks, signs, or the primary action.
- Do not use an old event graphic as if the date is current. Treat `event-graphics` as visual source material unless the event has been confirmed.
- Do not infer offers, times, cover charges, or event recurrence from images alone. Use `strategy/facebook-programming-source.md`.
- If a crop includes people, do not crop faces, bodies, hands holding tickets, drinks, or the main action out of frame.

## Search Examples

Find line-dancing crops:

```bash
find prepared-photos -type f | rg 'line-dancing|dance-floor'
```

Find mobile-ready people photos:

```bash
find prepared-photos/people -type f | rg 'mobile-900x1200'
```

Find food/drink card crops:

```bash
find prepared-photos/food-drink -type f | rg 'card-600x450'
```

Search the manifest by concept:

```bash
rg '"ticket giveaway"|"game day"|"local libations"|"bartender"' prepared-photos/manifest.json
```

## Current Inventory

- 170 PNG crops
- 45 source entries
- 35 photo entries
- 10 event/flyer graphic entries

The manifest records source image, source dimensions, tags, intended use, generated outputs, and crop coordinates for each entry.
