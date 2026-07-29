# Rakesh Nursery

Website for **Rakesh Nursery** — plants, pots and garden accessories, Goregaon East, Mumbai.

- **Address:** Sadguru Tower, Near Satellite Tower, Film City Road, Goregaon East, Mumbai – 400063
- **Phone:** 7091544504 · 9006019155
- **Proprietor:** Rakesh Kumar Sah — Garden Contractor

## Structure

```
index.html      the whole site — markup, styles and catalogue data in one file
images/         every photo, as WebP (see "Images" below)
```

There is no build step and no external dependency. Open `index.html` in a browser,
or serve the folder with any static host (GitHub Pages works as-is).

## Sections

Four tabs, switched client-side, each with its own URL hash so links are shareable:

| Tab | Hash | Contents |
|---|---|---|
| Plants | `#plants` | 69 plants, filterable by Indoor / Flowering / Succulents & Cacti / Bonsai & Topiary / Outdoor & Landscape / Fruit & Herbs |
| Pots & Planters | `#pots` | 40 pot styles, filterable by Ceramic / Cement & Matka / FRP & Stone Finish / Troughs / Décor |
| Accessories | `#accessories` | Tools, stands, grow bags, hanging baskets, festival décor |
| Services & Gallery | `#services` | 6 services plus a 19-photo nursery gallery |

Tapping any card opens a popup with the large photo, description, care or spec
details, and a WhatsApp button pre-filled with that item's name. Arrow keys,
swipe, Esc and the browser back button all work inside the popup.

## Editing the catalogue

All content lives in plain JavaScript arrays near the top of the `<script>` block
in `index.html` — `PLANTS`, `POTS`, `ACCESSORIES`, `SERVICES`, `GALLERY`.
Add or edit an entry there and it appears on the site; the tab counts and the
hero statistics update themselves.

Field keys are short to keep the file readable:

| Key | Meaning |
|---|---|
| `s` | image slug — expects `images/<s>-t.webp` and `images/<s>.webp` |
| `n` | name |
| `b` | botanical name (plants) |
| `c` | category key, matching `PLANT_CATS` / `POT_CATS` |
| `d` | description |
| `L` / `W` | light / water (plants) |
| `m` / `z` / `u` | material / sizes / best-for (pots and accessories) |
| `p` | process steps (services) |
| `t` | tags shown as pills |

## Images

Every photo exists twice:

- `images/<slug>-t.webp` — 560×420 grid thumbnail, ~37 KB
- `images/<slug>.webp` — 1000 px long edge for the popup, ~73 KB

Grid thumbnails are lazy-loaded, so a phone downloads only what is on screen.
To add a photo, produce both sizes with the same slug and reference the slug
from the catalogue array.

## Prices

Deliberately not listed — every item shows "Price on request" and links to
WhatsApp, so rates can change with size and season without touching the site.
