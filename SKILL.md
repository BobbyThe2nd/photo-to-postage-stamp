---
name: photo-to-postage-stamp
description: Transform an uploaded photo or a described scene into an authentic, collectible-looking postage-stamp image, souvenir sheet, stamp pane, or annotated stamp comparison sheet. Use when a user asks to turn a picture into a stamp, design a stamp, create a stamp-style image, compare stamp designs, create a stamp sheet or postal issue, or apply Chinese paper-cut, ink wash, retro travel, clear-line adventure comic, woodcut, minimalist icon, surreal pop, red pictogram, or ornate linework styling.
---

# Photo to Postage Stamp

Create a single finished raster stamp image. Use the available image-generation tool; for an uploaded photo, include the photo as the editing reference and preserve its identifiable subject, composition, and key visual details unless the user asks for a looser interpretation.

## Workflow

1. Inspect the supplied photo, or extract the visual subject from the description.
2. Choose a scheme. Honor the user's stated scheme. If the user asks to preview or select a style—or has not supplied a style—start with **Style preview mode**. Use the automatic rules below only when the user asks for a quick, immediate stamp.
3. Resolve the label and denomination. Honor values supplied by the user. When factual place or date information is requested, verify it from embedded image metadata, user-provided context, clearly identifiable landmark evidence, or reliable research. Do not treat an AI visual inference as verification. Default denomination: `80`.
4. Build a focused generation prompt using the physical requirements, scheme language, and typography rules. Read [styles.md](references/styles.md) for the scheme text.
5. Generate the image and present it. Briefly state the selected scheme, label, and denomination. Do not claim uncertain location or date as fact.

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

When the user requests all issue formats, output all three sheet families as three independent final images, one generation per sheet. Do not use the style-preview flow first unless the user also asks to choose a style.

Do not mimic an existing postal authority, issue, logo, or copyrighted character. Use a neutral issue title and omit location/date when they are unavailable. Keep each sheet visually simple: one dominant theme, a restrained palette, and only necessary labels.

## Style preview mode

Use this two-stage selection flow when the user wants to compare styles or has not named one.

1. Create a single 3:5 portrait **style selector**: show the unaltered source image at the top and nine small stamp thumbnails below in a numbered 3×3 grid. Include every scheme: `1 CHIN_PAPERCUT`, `2 INK_WASH`, `3 TRAV_VINT`, `4 CLEAR_LINE_ADVENTURE`, `5 CHIN_WOOD`, `6 MINI_ICON`, `7 SURR_POP`, `8 RED_PICTOGRAM`, and `9 ORNATE_LINEWORK`. Use clean, high-contrast labels outside each thumbnail. This selector is a visual direction board, not the final stamp; keep text inside thumbnail stamps minimal.
2. Ask the user to reply with the number or scheme name they prefer. Do not generate every option as a final-quality sheet unless the user explicitly asks for that.
3. After selection, create one final 3:5 portrait comparison sheet following the layout rules above. Apply the selected scheme at full detail, resolve verified stamp information, and include hand-drawn annotation elements.

If the user asks for full-detail previews before choosing, make one separate 3:5 page per requested scheme rather than packing several final designs into one page.

## Prompt requirements

Every prompt must include all of the following:

- `authentic postage stamp design`, vertical stamp composition, and a centered subject.
- Clean perforated scalloped edges and a white outer border; keep the entire stamp visible with no cropped perforations.
- Subtle paper grain, matte finish, light surface scratches, and a faint black postal cancellation mark crossing one corner without hiding the subject or required text.
- The chosen scheme description from [styles.md](references/styles.md).
- A bold, legible `"{TEXT LABEL}"` integrated along a border or stacked vertically, plus a distinct corner denomination `"{DENOMINATION}"`.

Treat required lettering as layout-critical: request exact spelling, high contrast, generous clearance from perforations, and no other competing text. If text is rendered incorrectly, regenerate or offer a corrected pass.

## Metadata rules

- Use a user-provided label verbatim, including language and capitalization.
- Read available EXIF/IPTC/XMP data before researching or asking. Treat GPS, capture timestamp, or supplied provenance as primary evidence.
- If a landmark, caption, or visible information identifies the place, verify it with reliable research before using it. When it cannot be verified, label the stamp with a subject title rather than an invented location.
- Use the verified capture date when available. If no date is verified, omit the date; do not substitute the current year. The only exception is when the user explicitly requests a contemporary commemorative issue.
- Ask one concise follow-up when the user requires factual location or date information and it cannot be verified. Otherwise proceed with subject-only text and state that the factual details were unavailable.

## Examples

- “Make my cat photo a traditional Chinese paper-cut stamp, label it FU.” → `SCHEME_CHIN_PAPERCUT`, `FU`, `80`.
- “Turn this Eiffel Tower photo into a stamp.” → `SCHEME_TRAV_VINT`, `PARIS 2026` when the landmark is clear, `1.20$`.
