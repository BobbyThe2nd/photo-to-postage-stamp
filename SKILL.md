---
name: photo-to-postage-stamp
description: Transform uploaded photos, described scenes, or existing stamps into authentic collectible postage stamps, three-layout issue sets, and poetic front-and-back postcards with social presentation posters or source-versus-translation diptychs. Automatically select an artistic print style, derive country from verified photo location, and apply official postal-value conventions. Use when a user asks to turn pictures into stamps, design a stamp, create a souvenir sheet or stamp pane, compare stamp styles, build a postal issue, derive a postcard from a stamp, show a postcard front and back, make a postcard presentation poster, show before/after or original/artwork comparison, or apply blue-pencil field sketch, calm solid-wash doodle, vintage mixed-media collage, simplified paper-cut, ink wash, naive watercolor bestiary, retro travel, clear-line comic, Art Deco museum poster, minimalist icon, surreal pop, red pictogram, or ornate linework styling.
---

# Photo to Postage Stamp

Create finished raster stamp issues from uploaded photos or descriptions. For an uploaded photo, include it as the subject reference and preserve its identifiable subject, pose, and key visual details unless the user asks for a looser interpretation.

## Workflow

1. Inspect the supplied photo, or extract the visual subject from the description.
2. Choose the strongest scheme automatically from the subject, composition, mood, and visual era. Honor a user-specified scheme. Do not show the thirteen-style selector unless the user explicitly asks to preview or compare styles.
3. Resolve country and postal value. Use verified photo location when available; otherwise default the issuing country to the United States. Read [postal-conventions.md](references/postal-conventions.md) and follow official postal wording rather than guessing from currency alone.
4. Build a focused generation prompt using the physical requirements and scheme language. Read [styles.md](references/styles.md), [art-direction.md](references/art-direction.md), and [perforations.md](references/perforations.md).
5. Before rendering a formal issue, verify the country label and denomination convention with the country's official postal operator. Read [postal-conventions.md](references/postal-conventions.md).
6. When creating a final selection, preserve the chosen preview's visual language with **Style lock**. Read [style-lock.md](references/style-lock.md).
7. When the user requests a postcard, front/back design, or postcard presentation poster, follow [postcards.md](references/postcards.md) instead of the default three-layout issue output.
8. Unless the user requests another format, generate the complete three-layout issue set as three independent images. Present the selected artistic direction, country, and verified postal convention. Do not claim uncertain location or date as fact.

## Scheme selection

- Architecture or industrial subjects: `SCHEME_CLEAR_LINE_ADVENTURE`; use `SCHEME_MINI_ICON` for highly graphic, simplified subjects.
- Travel observations, boats, fish, tools, natural-history studies, or any subject that should feel intimate, exploratory, and free of digital polish: `SCHEME_BLUE_PENCIL_FIELD_SKETCH`.
- Everyday architecture, travel scenes, trees, interiors, objects, and subjects needing calm hand-drawn color without watercolor-filter softness: `SCHEME_CALM_SOLID_WASH_DOODLE`.
- Animals with expressive silhouettes or characterful poses: `SCHEME_NAIVE_WATERCOLOR_BESTIARY`; use `SCHEME_INK_WASH` for a quieter, atmospheric treatment.
- Plants, flowers, and natural scenes: `SCHEME_INK_WASH`; use `SCHEME_CALM_SOLID_WASH_DOODLE` for a lighter hand-drawn treatment.
- People and everyday moments: `SCHEME_TRAV_VINT`; use `SCHEME_CHIN_PAPERCUT` when a celebratory Chinese folk-art treatment fits.
- Fashion, abstract, or high-contrast subjects: `SCHEME_SURR_POP`.
- Playful food, animals, everyday objects, expressive portraits, and subjects that benefit from hot contrasting color, loose handwriting, tactile collage, and visibly imperfect mixed media: `SCHEME_VINTAGE_MIXED_MEDIA_COLLAGE`.
- Simple, emblematic, or mid-century subjects: `SCHEME_RED_PICTOGRAM`.
- Armor, sculpture, museum objects, historic interiors, formal exhibitions, and subjects suited to black, oxblood, antique gold, and architectural framing: `SCHEME_ART_DECO_MUSEUM_POSTER`.
- Formal, archival, or decorative subjects: `SCHEME_ORNATE_LINEWORK`.

`SCHEME_CHIN_WOOD` is a hidden legacy scheme. Do not auto-select it or include it in style selectors unless the user explicitly requests that scheme by name.

When the user explicitly names one scheme for a complete issue, keep that scheme consistent across all three sheet families. Vary crop, scale, pose, and study stage inside the variety pane instead of switching styles.

## Comparison sheets

When the user asks for a comparison sheet, create one lively 3:5 portrait research-board page. Read [comparison-layouts.md](references/comparison-layouts.md) and select a layout that suits the subject. Do not default to a rigid top-image/bottom-stamp stack.

Keep the unaltered original image and one full, readable new stamp as the two primary artifacts. Establish an intentional asymmetric hierarchy with a visible grid, generous breathing room, and a clear relationship between source and stamp. Add only subject-derived supporting material—such as a contour sketch, silhouette, crop detail, palette chips, perforation study, or fine callout arrows. Use concise handwritten notes and precise typographic labels for the scheme, material, print process, and verified metadata. Keep every annotation outside the source image and stamp, and never invent scientific measurements, place names, dates, specimen data, or illegible pseudo-language.

## Souvenir sheets and stamp panes

When the user asks for an issued sheet, a full stamp sheet, a postal pane, a souvenir sheet, or a three-layout issue set, read [souvenir-sheets.md](references/souvenir-sheets.md). Make the stamps, perforations, margins, and large supporting illustration feel physically coherent as a single print issue.

Choose each stamp's orientation from the source composition: use a horizontal stamp for a clearly landscape source and a vertical stamp for a clearly portrait source. Do not force a landscape subject into a vertical crop. Souvenir sheets and miniature sheets use a normal straight outer paper edge; apply perforations only to the stamp or stamp block inside the sheet.

1. **Integrated souvenir sheet:** Create one stamp within a single large themed background; the stamp is a deliberate part of the full illustration.
2. **Variety pane:** For one uploaded image, create a themed sheet with several stamps in clearly different chosen styles. For several uploaded images, use one chosen style consistently across the matching multi-stamp pane.
3. **Repeated definitive pane:** Repeat one identical stamp in an orderly grid, with a separate themed illustration occupying the remaining sheet area.

For an ordinary new upload, output all three sheet families as three independent final images, one generation per sheet. Do not use the style-preview flow unless the user explicitly asks to compare or choose styles. For one uploaded image, use the automatically selected primary scheme for sheets 1 and 3, and automatically select a restrained, compatible four-scheme set for sheet 2. For multiple images, use the primary scheme consistently across all stamps in sheet 2.

Do not mimic an existing postal authority, issue, logo, or copyrighted character. Use a neutral issue title and omit location/date when they are unavailable. Keep each sheet visually simple: one dominant theme, a restrained palette, and only necessary labels.

## Postcards

When the user asks for a postcard, postcard front and back, or a post-ready image showing both sides, read [postcards.md](references/postcards.md). Treat an uploaded stamp as a visual source system rather than a sticker: extract its subject, palette, line behavior, symbols, and implied motion, then compose a new postcard instead of merely enlarging or repeating the stamp.

For any postcard request, add a separate standalone comparison showcase image defined in [postcards.md](references/postcards.md): original photo on top, generated postcard front on the bottom, portrait `3:4` (reference size `100 × 150 mm / 4 × 6 in`), warm white/ivory paper background.

When the user asks to compare the original with the transformed artwork, add the source-versus-translation diptych defined in [postcards.md](references/postcards.md). Keep this comparison artifact separate from the functional postcard back; never replace the address side with a before/after panel.

Generate the front and back as the two sides of one physical object. They must use the same real-world aspect ratio and exactly the same visible dimensions in every presentation. Rotation and placement may differ, but scale may not. Make the finished cards the primary layer; let the design-process sheet remain subordinate and accept partial occlusion.

## Style preview mode

Use this two-stage selection flow only when the user explicitly asks to preview, compare, or choose styles.

1. Create a single portrait **style selector**: show the unaltered source image at the top and thirteen small stamp thumbnails below in a balanced grid with equal-size tiles. Include every visible scheme: `1 CHIN_PAPERCUT`, `2 INK_WASH`, `3 TRAV_VINT`, `4 CLEAR_LINE_ADVENTURE`, `5 ART_DECO_MUSEUM_POSTER`, `6 MINI_ICON`, `7 SURR_POP`, `8 RED_PICTOGRAM`, `9 ORNATE_LINEWORK`, `10 NAIVE_WATERCOLOR_BESTIARY`, `11 BLUE_PENCIL_FIELD_SKETCH`, `12 CALM_SOLID_WASH_DOODLE`, and `13 VINTAGE_MIXED_MEDIA_COLLAGE`. Use clean, high-contrast labels outside each thumbnail. Do not shrink the thirteenth tile into a subordinate add-on; use a 4×4 grid with three intentional empty cells or another balanced layout. This selector is a visual direction board, not the final stamp; keep text inside thumbnail stamps minimal. Keep `SCHEME_CHIN_WOOD` hidden unless the user explicitly requests it by name.
2. Ask the user to reply with the number or scheme name they prefer. Do not generate every option as a final-quality sheet unless the user explicitly asks for that.
3. After selection, create one final 3:5 portrait comparison sheet following the layout rules above. Apply the selected scheme at full detail, resolve verified stamp information, and include hand-drawn annotation elements.

If the user asks for full-detail previews before choosing, make one separate 3:5 page per requested scheme rather than packing several final designs into one page.

## Style lock

When a user selects one or more style-preview tiles, treat the selected tile as a binding visual reference rather than merely a scheme name. Include the preview board in the final image-generation inputs, identify the exact chosen tile numbers, and repeat its defining palette, mark density, and simplification level in the prompt. Do not substitute a more detailed, painterly, textured, or otherwise different interpretation of the chosen scheme. For multi-style panes, apply an independent style lock to every tile.

## Prompt requirements

Every prompt must include all of the following:

- `authentic postage stamp design`, an orientation matched to the source composition, and a clearly resolved subject. Use a horizontal stamp for landscape material and a vertical stamp for portrait material.
- Use the default `PUNCHED_HOLE_CONNECTOR_CUT` system from [perforations.md](references/perforations.md): round punched holes, short straight connector cuts between holes with very narrow paper bridges, and only a hairline recessed cut shadow. Keep the complete stamp perforation system and white stamp margin visible with no cropped holes. Do not add perforations to the outer edge of a souvenir sheet or miniature sheet.
- Subtle paper grain, matte finish, light surface scratches, and a faint black postal cancellation mark crossing one corner without hiding the subject or required text.
- The chosen scheme description from [styles.md](references/styles.md) and the authorship constraints from [art-direction.md](references/art-direction.md).
- A bold, legible `"{COUNTRY / POSTAL MARKING}"` and subject label, using the verified country's normal denomination or service-indicator convention and typographic hierarchy.

Treat required lettering as layout-critical: request exact spelling, high contrast, generous clearance from perforations, and no other competing text. If text is rendered incorrectly, regenerate or offer a corrected pass.

## Metadata rules

- Use a user-provided label verbatim, including language and capitalization.
- Read available EXIF/IPTC/XMP data before researching or asking. Treat GPS, capture timestamp, or supplied provenance as primary evidence.
- If a landmark, caption, or visible information identifies the place, verify it with reliable research before using it. When it cannot be verified, label the stamp with a subject title rather than an invented location.
- If country cannot be established from metadata, user context, or verified landmark evidence, use the United States as the issuing country and apply the current standard U.S. domestic convention from [postal-conventions.md](references/postal-conventions.md). Do not imply that the photo was taken in the United States.
- Use the verified capture date when available. If no date is verified, omit the date; do not substitute the current year. The only exception is when the user explicitly requests a contemporary commemorative issue.
- Ask one concise follow-up when the user requires factual location or date information and it cannot be verified. Otherwise proceed with subject-only text and state that the factual details were unavailable.

## Examples

- “Make my cat photo a traditional Chinese paper-cut stamp, label it FU.” → `SCHEME_CHIN_PAPERCUT`, `FU`, `80`.
- “Turn this Eiffel Tower photo into stamps.” → verify France from the landmark, select the strongest artistic direction, verify current La Poste denomination practice, and generate all three issue layouts.
- “Turn this rabbit stamp into a postcard and show both sides.” → derive a new front and functional back from the stamp's visual DNA, keep both sides exactly the same size, and present them over a subordinate annotated design-process sheet.
