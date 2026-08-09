---
name: photo-to-postage-stamp
description: Transform an uploaded photo or a described scene into an authentic, collectible-looking postage-stamp image. Use when a user asks to turn a picture into a stamp, design a stamp, create a stamp-style image, or apply Chinese paper-cut, ink wash, retro travel, etching, woodcut, minimalist icon, or surreal pop stamp styling.
---

# Photo to Postage Stamp

Create a single finished raster stamp image. Use the available image-generation tool; for an uploaded photo, include the photo as the editing reference and preserve its identifiable subject, composition, and key visual details unless the user asks for a looser interpretation.

## Workflow

1. Inspect the supplied photo, or extract the visual subject from the description.
2. Choose a scheme. Honor the user's stated scheme; otherwise select one with the rules below.
3. Resolve the label and denomination. Honor values supplied by the user. If no label is given, use a conservative location/year label only when both are evident; otherwise use a concise subject label and the current year. Default denomination: `80`.
4. Build a focused generation prompt using the physical requirements, scheme language, and typography rules. Read [styles.md](references/styles.md) for the scheme text.
5. Generate the image and present it. Briefly state the selected scheme, label, and denomination. Do not claim uncertain location or date as fact.

## Scheme selection

- Architecture or industrial subjects: `SCHEME_TECH_INTA`; use `SCHEME_MINI_ICON` for highly graphic, simplified subjects.
- Animals, plants, flowers, and natural scenes: `SCHEME_INK_WASH`; use `SCHEME_CHIN_WOOD` for a bolder, more decorative result.
- People and everyday moments: `SCHEME_TRAV_VINT`; use `SCHEME_CHIN_PAPERCUT` when a celebratory Chinese folk-art treatment fits.
- Fashion, abstract, or high-contrast subjects: `SCHEME_SURR_POP`.

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
- Do not invent a specific city, country, era, or historical event from an ambiguous photo. For example, use `GARDEN 2026` rather than guessing a city.
- If location is clear from user context or visual evidence, use `LOCATION YEAR` in uppercase. Use the current year only when no era is requested.
- Ask one concise follow-up only when the user explicitly requires a precise label or denomination that cannot be inferred. Otherwise use the defaults and proceed.

## Examples

- “Make my cat photo a traditional Chinese paper-cut stamp, label it FU.” → `SCHEME_CHIN_PAPERCUT`, `FU`, `80`.
- “Turn this Eiffel Tower photo into a stamp.” → `SCHEME_TRAV_VINT`, `PARIS 2026` when the landmark is clear, `1.20$`.

