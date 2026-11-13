# Design system

One visual language for two READMEs: the Soma18 showcase and Taha Saiyed's profile. Every graphic is a file in this folder, generated from the tokens below. No scripts, no outside services, no outside fonts.

## Colour (five tokens per theme)

| Token | Dark (on `#0d1117`) | Light (on `#ffffff`) | Used for |
|---|---|---|---|
| Surface | `#0F151B` · hsl(210 29% 8%) | `#F6F7F3` · hsl(75 20% 96%) | Panels (obsidian / alabaster) |
| Primary accent | `#5FC2C6` · hsl(182 47% 57%) | `#0E6569` · hsl(183 76% 23%) | Active lines, icons, lit states |
| Kinetic accent | `#F0B33C` · hsl(40 86% 59%) | `#B4730A` · hsl(37 89% 37%) | Motion highlights, check marks |
| Structural hairline | `#2A3742` · hsl(207 22% 21%) | `#CFD6CF` · hsl(120 8% 83%) | 1px structure |
| Typography | `#E8EAE5` · hsl(84 11% 91%) | `#16211F` · hsl(169 20% 11%) | Text |

Derived tints, mixed from the five: a raised surface (`#161F27` / `#FFFFFF`), secondary text (`#9AA7A6` / `#55625F`), and two signal tints for the four data paths (`#A6E6E8`, `#F7C462` / `#1F9197`, `#8A5606`). The teal and the amber echo the colours of the public Soma18 site.

## Line, corner and depth

- Structural hairlines are 1px. Active vectors are 1.5px.
- Outer containers have a 12px radius. Inner nodes and icon tiles have a 6px radius.
- Every panel carries a 1px specular top edge: a horizontal `linearGradient` that fades in from both ends.
- Depth is a flat plate 5 to 8px below a card, not a blur. Blur is kept for light: glows, the aurora and halos.
- Icons are generic 24px stroke glyphs. No brand marks.

## Type

System fonts only. Sans: `-apple-system, BlinkMacSystemFont, 'Inter', 'Segoe UI', Roboto, sans-serif`. Mono for labels: `ui-monospace, SFMono-Regular, 'SF Mono', Menlo, Consolas, monospace`. Text widths change a little between systems, so every label has room to spare.

## Timing

Loops run on 3, 6, 9, 12, 18 and 36 seconds, so they drift in and out of step instead of pulsing together. Entrances and reveals use `cubic-bezier(0.22, 1, 0.36, 1)`; breathing and sweeps use a symmetric ease.

## Motifs

- **Soma18: the breathing "18" ring.** Counter-rotating dashed rings and two tilted orbits around the number 18. The core swells and settles once every 18 seconds, for the daily 18-minute practice.
- **Taha Saiyed: the telemetry lattice.** Points joined by lines on a drifting grid, with light travelling along the lines. The same strokes, corners and specular edge as the ring.

## Motion and accessibility

- CSS `@keyframes` drive most motion. SMIL drives motion along a path, spline-eased rotation and the slow change in the noise filter.
- Every SVG has a `@media (prefers-reduced-motion: reduce)` block. It stops all CSS animation, hides the SMIL-driven layer and shows a still copy in its place. The resting state of every graphic is the finished, readable state.
- Dark and light are separate files, chosen in Markdown with `<picture>` and `prefers-color-scheme`.
- Every image has alt text, and both READMEs read in order with images off.

## Rules for the files

No `<script>`, no event handlers, no `<foreignObject>`, no outside links, images or fonts inside any SVG (the only address is the SVG namespace itself). The phone frame embeds its screenshot as data inside the file. Each file is under 2 MB and each repository under 8 MB.
