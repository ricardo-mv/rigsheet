# RigSheet

**Bulk preset editor for multi-effects units.**
Live at **[rigsheet.rocks](https://rigsheet.rocks)**

Read, edit and reorder all 256 presets of a Valeton GP-200, R, X, JR or LT by
working on `.prst` files. Everything runs in the browser: nothing is uploaded,
and it works offline.

---

## Why

256 presets is a lot. Sorting them one at a time was miserable — getting the
pedal ready before a gig ate hours. All I wanted at first was two things: put
the night's setlist in order, and set the FX Loop to match the conditions on
stage.

The official editor does everything one preset at a time. RigSheet shows them
as a spreadsheet: pick twenty and change them in one go.

## What it does

- **Full view** of all 256 slots with their effect chain, author, style and notes
- **Cross-field search** — name, slot, author, note, comment, style, effect and modelled gear
- **Fine editing** of the 11 modules: effect, on/off and parameters with their real ranges
- **Bulk editing** of author, style and pedal note
- **Personal comments**, unlimited, kept outside the pedal
- **Bulk FX Loop** — change the wiring scenario of dozens of presets at once
- **Ordering** — drag, move in blocks, compact, alphabetical or by style
- **Management** — copy, paste, rename, delete, insert empty slots
- **Export** to `.prst` in a dated ZIP, to CSV, and to a move plan
- **Printing** of the recall sheet
- Seven languages, nine palettes, responsive

## Supported devices

| Device | Effects | Footswitches |
|---|---|---|
| Valeton GP-200 / R / X / JR | 305 | 8 |
| Valeton GP-200LT | 277 | 4 |

More devices — and other brands — are planned. If you own a different
multi-effects unit and want it supported, see *What's next* in the in-app manual.

## The files

| File | Purpose |
|---|---|
| `index.html` | The entire application. Self-contained, no dependencies. |
| `card.png` | Link preview image |
| `_headers` | Security headers, including a policy that forbids network requests |
| `robots.txt`, `sitemap.xml` | For search engines |
| `LICENSE.txt` | Proprietary licence and trademark notice |

## Deploying

Static hosting, nothing to build. `rigsheet.rocks` runs on Cloudflare Pages
connected to this repository: every commit on `main` publishes on its own, with
no manual step between what is stored here and what is served. The page you get
from the site is the `index.html` in this repository — read it, diff it, keep it.

To host it elsewhere, connect the repository and set the build output directory
to the repository root, with no build command.

## About the data

The `.prst` format was reverse engineered byte by byte and verified against the
official editor. Each file is 1224 bytes with a checksum recalculated on write.
The names, parameters, ranges, units and descriptions of all 305 effects are
generated from the `algorithm.xml` and `description_en.xml` files Valeton ships
with its desktop editor (editor software 1.8.1, device firmware 1.8.0).

## Licence

Copyright © 2026 RicardoMV. All rights reserved. See `LICENSE.txt`.

Free to use. Redistribution, resale and derivative works require written
permission.

**Not affiliated with Valeton.** Valeton, GP-200 and all device, amplifier,
cabinet and effect names referenced are trademarks of their respective owners,
used solely to identify compatibility.

## Contact

**hey@rigsheet.rocks** — bug reports welcome. If you own a GP-200LT, a single
`.prst` file from you would let RigSheet detect the model on its own.
