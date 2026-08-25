# Punched-hole connector-cut perforations

Use `PUNCHED_HOLE_CONNECTOR_CUT` as the default physical perforation system for postage stamps and the boundaries between stamps in a pane. On a souvenir sheet or miniature sheet, perforate only the stamp or stamp block inside the sheet. The sheet itself keeps a normal straight-cut paper edge with no outer scallops or punched holes.

## Scope boundary

- A standalone stamp has perforations around its complete outside edge.
- Stamps inside a pane share one perforation row at each internal boundary.
- A souvenir sheet or miniature sheet has a plain rectangular outer paper edge. Only its inset stamp or stamp block is perforated.
- Never extend a stamp's perforation treatment to the perimeter of the supporting sheet merely to make the sheet look more postal.

## Geometry

- Place equal-size circular punched holes on one consistent centerline with regular spacing.
- Connect each neighboring pair with a short, fine, straight incision aligned to the tear axis.
- Leave a very narrow paper bridge or tab so an attached pane still reads as one physical sheet.
- Form the outer edge of each stamp from the same holes and connector cuts, producing a clean scalloped stamp silhouette rather than a decorative dotted border.
- Use one shared perforation row between adjacent stamps. Never use double rows, blank gutters, or overlapping scallops.
- Resolve crossings as one clean four-way junction with consistent hole size and spacing.
- Preserve a generous white safety margin between perforations and artwork or postal text.

## Tactile cut character

- Make the holes true voids that reveal the sheet or background beneath, not printed dots.
- Show only a microscopically narrow compressed paper rim around each hole, a trace of exposed paper fiber, and a hairline recessed shadow immediately inside the cut.
- Keep the rim highlight and shadow confined to the cut edge. At normal viewing size they should be barely perceptible and must never spread into a broad white halo, soft glow, bloom, or thick embossed ring.
- Give connector cuts a hairline separation shadow and minute pressure indentation. They must read as cuts in paper, not gray rules drawn on top.
- Keep the light direction and depth consistent across the complete pane.
- Use restrained relief: tactile at full resolution but quiet at normal viewing size.
- Allow only minute organic variation in pressure and fiber. Keep spacing, scale, and alignment mechanically coherent.

## Prompt lock

Include this language in every stamp-generation prompt:

> physically die-punched postage perforations using the PUNCHED_HOLE_CONNECTOR_CUT system: evenly spaced round holes joined by short straight connector incisions, extremely narrow remaining paper bridges, true cut-through voids revealing the background, microscopically narrow compressed paper rims, traces of exposed paper fiber, and hairline recessed shadows confined tightly to the cut edges with no white halo, glow, bloom, or thick embossed ring; one shared perforation row between adjacent stamps; complete uncropped stamp silhouette; plain straight outer paper edge for any surrounding souvenir sheet or miniature sheet

## Reject and regenerate when

- holes look like printed circles, beads, pearls, rivets, lace, or a dotted line;
- the edge is only a generic wave, zigzag, sawtooth, or cookie-cutter scallop;
- connector cuts are absent, dashed, too dark, or visibly drawn with ink;
- the holes have black outlines or metallic embossing;
- interior boundaries use two perforation rows or leave a blank strip;
- spacing changes arbitrarily, holes become ovals, or junctions collapse;
- shadows are heavy enough to resemble floating stickers or laser-cut foam;
- white highlights or shadows spread beyond the immediate cut edge and form a visible halo, glow, bloom, or thick ring;
- the outer edge of a souvenir sheet or miniature sheet is perforated instead of remaining a normal straight paper edge;
- any outer holes are cropped by the image boundary.

## Final inspection

Inspect at full resolution and normal viewing size. Confirm that circular voids, connector cuts, narrow bridges, exposed fibers, and hairline micro-shadows are present; no broad white halo is visible at normal size; shared rows are singular and aligned; the pane remains visually attached; perforations do not obscure artwork or typography; every stamp edge remains complete; and any surrounding souvenir-sheet or miniature-sheet perimeter remains straight and unperforated.
