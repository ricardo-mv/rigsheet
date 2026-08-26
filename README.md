# RigSheet

**Bulk preset editor for multi-effects units.**
Live at **[rigsheet.rocks](https://rigsheet.rocks)**

Edit, reorder and manage every preset on your unit at once, instead of one at a
time. It was born on a Valeton GP-200 and today works with that family — GP-200,
R, X, JR and LT — over `.prst` files or by connecting the pedal over USB.

The hard part of adding a new unit is working out its format. Everything else —
the table, the bulk edits, the ordering, the export — is already built and tied
to no brand. Everything runs in the browser: nothing is uploaded, and it works
offline.

---

## Why

My pedal holds 256 presets, and that is a lot. Sorting them one at a time was
miserable — getting the pedal ready before a gig ate hours. All I wanted at
first was two things: put the night's setlist in order, and set the FX Loop to
match the conditions on stage.

The official editor does everything one preset at a time. RigSheet shows them
as a spreadsheet: pick twenty and change them in one go.

## Two ways to work

**On files.** Export your presets from Valeton's editor, drop them on the page,
work, and download the result as a dated ZIP. Any modern browser.

**Over USB.** Press *Connect the pedal* and RigSheet fetches its 256 presets into
the table. Everything then behaves the same, except that changes to the preset
the pedal currently has loaded are heard straight away. When you are done, only
what you touched is written back — with a backup downloaded first and every slot
verified by reading it back afterwards. Needs Chrome or Edge, the browsers that
implement Web MIDI.

Applying and saving are deliberately separate. Moving a knob goes to the pedal's
edit buffer: it sounds immediately and touches nothing in memory. Nothing is
stored until you press save.

## What it does

- **Full view** of all 256 slots with their effect chain, author, style and notes
- **Cross-field search** — name, slot, author, note, comment, style, effect and modelled gear
- **Fine editing** of the 11 modules: effect, on/off and parameters with their real ranges
- **Bulk editing** of author, style, pedal note and **parameters** — the knob is
  matched by name on each preset, because the same control sits at a different
  position depending on the amp model
- **USB connection** — fetch the pedal's 256 presets, hear changes as you make
  them, and write back only what changed
- **Personal comments**, unlimited, kept outside the pedal
- **Bulk FX Loop** — change the wiring scenario of dozens of presets at once
- **Ordering** — drag, move in blocks, compact, alphabetical or by style
- **Management** — copy, paste, rename, delete, insert empty slots
- **Export** to `.prst` in a dated ZIP, to CSV, and to a move plan
- **Printing** of the recall sheet, limited to the selection when there is one
- Eight languages, nine palettes, responsive

## Supported so far

| Device | Effects | Footswitches |
|---|---|---|
| Valeton GP-200 / R / X / JR | 305 | 8 |
| Valeton GP-200LT | 277 | 4 |

That list is where it starts, not where it ends. Adding a manufacturer means
decoding its preset format — the same work already done once here. If you own a
different multi-effects unit and want it supported, get in touch: exported
factory presets and the desktop editor's own files are what make it possible.

The USB features are specific to the GP-200 family, since they depend on that
pedal's own protocol. File editing has no such limit.

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

The `.prst` format and the GP-200's USB MIDI protocol were both reverse
engineered byte by byte and verified against the official editor. Each file is 1224 bytes with a checksum recalculated on write.
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
