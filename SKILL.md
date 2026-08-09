---
name: photo-to-postage-stamp
description: Transform uploaded photos or described scenes into authentic collectible postage stamps and three-layout issue sets, automatically selecting an artistic print style, deriving country from verified photo location, and applying official postal-value conventions. Use when a user asks to turn pictures into stamps, design a stamp, create a souvenir sheet or stamp pane, compare stamp styles, build a postal issue, or apply paper-cut, ink wash, retro travel, clear-line comic, woodcut, minimalist icon, surreal pop, red pictogram, or ornate linework styling.
---

# Photo to Postage Stamp

Create finished raster stamp issues from uploaded photos or descriptions. For an uploaded photo, include it as the subject reference and preserve its identifiable subject, pose, and key visual details unless the user asks for a looser interpretation.

## Workflow

1. Inspect the supplied photo, or extract the visual subject from the description.
2. Choose the strongest scheme automatically from the subject, composition, mood, and visual era. Honor a user-specified scheme. Do not show the nine-style selector unless the user explicitly asks to preview or compare styles.
3. Resolve country and postal value. Use verified photo location when available; otherwise default the issuing country to the United States. Read [postal-conventions.md](references/postal-conventions.md) and follow official postal wording rather than guessing from currency alone.
4. Build a focused generation prompt using the physical requirements and scheme language. Read [styles.md](references/styles.md) and [art-direction.md](references/art-direction.md).
5. Before rendering a formal issue, verify the country label and denomination convention with the country's official postal operator. Read [postal-conventions.md](references/postal-conventions.md).
6. When creating a final selection, preserve the chosen preview's visual language with **Style lock**. Read [style-lock.md](references/style-lock.md).
7. Unless the user requests another format, generate the complete three-layout issue set as three independent images. Present the selected artistic direction, country, and verified postal convention. Do not claim uncertain location or date as fact.

## Scheme selection

- Architecture or industrial subjects: `SCHEME_CLEAR_LINE_ADVENTURE`; use `SCHEME_MINI_ICON` for highly graphic, simplified subjects.
- Animals, plants, flowers, and natural scenes: `SCHEME_INK_WASH`; use `SCHEME_CHIN_WOOD` for a bolder, more decorative result.
- People and everyday moments: `SCHEME_TRAV_VINT`; use `SCHEME_CHIN_PAPERCUT` when a celebratory Chinese folk-art treatment fits.
- Fashion, abstract, or high-contrast subjects: `SCHEME_SURR_POP`.
- Simple, emblematic, or mid-century subjects: `SCHEME_RED_PICTOGRAM`.
- Formal, archival, or decorative subjects: `SCHEME_ORNATE_LINEWORK`.

## Comparison sheets

When the user asks for a comparison sheet, create one lively 3:5 portrait research-board page. Read [comparison-layouts.md](references/comparison-layouts.md) and select a layout that suits the subject. Do not default to a rigid top-image/bottom-stamp stack.

Keep the unaltered original image and one full, readable new stamp as the two primary artifacts. Establish an intentional asymmetric hierarchy with a visible grid, generous breathing room, and a clear relationship between source and stamp. Add only subject-derived supporting material—such as a contour sketch, silhouette, crop detail, palette chips, perforation study, or fine callout arrows. Use concise handwritten notes and precise typographic labels for the scheme, material, print process, and verified metadata. Keep every annotation outside the source image and stamp, and never invent scientific measurements, place names, dates, specimen data, or illegible pseudo-language.

## Souvenir sheets and stamp panes

When the user asks for an issued sheet, a full stamp sheet, a postal pane, a souvenir sheet, or a three-layout issue set, read [souvenir-sheets.md](references/souvenir-sheets.md). Make the stamps, perforations, margins, and large supporting illustration feel physically coherent as a single print issue.

1. **Integrated souvenir sheet:** Create one stamp within a single large themed background; the stamp is a deliberate part of the full illustration.
2. **Variety pane:** For one uploaded image, create a themed sheet with several stamps in clearly different chosen styles. For several uploaded images, use one chosen style consistently across the matching multi-stamp pane.
3. **Repeated definitive pane:** Repeat one identical stamp in an orderly grid, with a separate themed illustration occupying the remaining sheet area.

For an ordinary new upload, output all three sheet families as three independent final images, one generation per sheet. Do not use the style-preview flow unless the user explicitly asks to compare or choose styles. For one uploaded image, use the automatically selected primary scheme for sheets 1 and 3, and automatically select a restrained, compatible four-scheme set for sheet 2. For multiple images, use the primary scheme consistently across all stamps in sheet 2.

Do not mimic an existing postal authority, issue, logo, or copyrighted character. Use a neutral issue title and omit location/date when they are unavailable. Keep each sheet visually simple: one dominant theme, a restrained palette, and only necessary labels.

## Style preview mode

Use this two-stage selection flow only when the user explicitly asks to preview, compare, or choose styles.

1. Create a single 3:5 portrait **style selector**: show the unaltered source image at the top and nine small stamp thumbnails below in a numbered 3×3 grid. Include every scheme: `1 CHIN_PAPERCUT`, `2 INK_WASH`, `3 TRAV_VINT`, `4 CLEAR_LINE_ADVENTURE`, `5 CHIN_WOOD`, `6 MINI_ICON`, `7 SURR_POP`, `8 RED_PICTOGRAM`, and `9 ORNATE_LINEWORK`. Use clean, high-contrast labels outside each thumbnail. This selector is a visual direction board, not the final stamp; keep text inside thumbnail stamps minimal.
2. Ask the user to reply with the number or scheme name they prefer. Do not generate every option as a final-quality sheet unless the user explicitly asks for that.
3. After selection, create one final 3:5 portrait comparison sheet following the layout rules above. Apply the selected scheme at full detail, resolve verified stamp information, and include hand-drawn annotation elements.

If the user asks for full-detail previews before choosing, make one separate 3:5 page per requested scheme rather than packing several final designs into one page.

## Style lock

When a user selects one or more style-preview tiles, treat the selected tile as a binding visual reference rather than merely a scheme name. Include the preview board in the final image-generation inputs, identify the exact chosen tile numbers, and repeat its defining palette, mark density, and simplification level in the prompt. Do not substitute a more detailed, painterly, textured, or otherwise different interpretation of the chosen scheme. For multi-style panes, apply an independent style lock to every tile.

## Prompt requirements

Every prompt must include all of the following:

- `authentic postage stamp design`, vertical stamp composition, and a centered subject.
- Clean perforated scalloped edges and a white outer border; keep the entire stamp visible with no cropped perforations.
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
