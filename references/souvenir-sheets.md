# Souvenir sheets and stamp panes

Create a single coherent printed issue, not a dashboard or an ordinary contact sheet. Use the default `PUNCHED_HOLE_CONNECTOR_CUT` system from [perforations.md](perforations.md), consistent paper grain, and enough clean margin around every stamp.

## Perforation structure

Treat perforation as a physical cut system rather than a decorative dotted outline. Show circular punched voids connected by short straight incision segments, with very narrow paper bridges keeping an attached pane coherent. Give every hole only a microscopically narrow compressed rim, exposed paper fiber, and a hairline recessed shadow tightly confined to the cut edge. Do not create a broad white halo, glow, bloom, or thick embossed ring. Shared interior rows must form one common boundary between adjacent stamps; never draw two parallel perforation rows or a blank gutter between them.

The perimeter of a souvenir sheet or miniature sheet is not a stamp edge. Keep it as a normal straight-cut rectangular paper edge with no holes, scallops, or connector cuts. Only the inset stamp or stamp block receives perforations.

## Stamp orientation

Choose stamp orientation from the source image and the subject's dominant visual flow:

- For a landscape source or a subject whose identity depends on horizontal breadth, use a horizontal stamp and preserve the wide composition.
- For a portrait source or a subject whose identity depends on vertical height, use a vertical stamp.
- For a square or ambiguous source, choose the orientation that preserves the subject with the least destructive cropping and the clearest postal-text hierarchy.
- Apply this decision independently to the inset stamp in an integrated souvenir sheet and to stamps in variety or definitive panes. Do not default to vertical merely because it is a traditional stamp format.

## Three-layout issue set

For a normal photo upload, create exactly three independent final sheets by default, using a separate image-generation call for each:

1. Integrated souvenir sheet
2. Variety or uniform-style pane
3. Repeated definitive pane

For one uploaded image, use it as the hero subject in all three sheets. Use the automatically selected primary scheme in sheets 1 and 3; in sheet 2, choose four compatible schemes that suit the subject without making the pane noisy. For multiple uploaded images, use the first image as the hero subject in sheets 1 and 3; use every uploaded image in sheet 2 with one consistent primary scheme. State this default briefly and let the user override the hero image.

## 1. Integrated souvenir sheet

Use one full-page illustration as the thematic background. Choose the inset stamp's orientation from the source: horizontal for landscape material and vertical for portrait material. Perforate that stamp directly from the same background so the landscape, colors, and perspective continue seamlessly inside and outside its boundary. Keep the surrounding sheet perimeter straight and unperforated. Never paste a separate stamp panel beside the background or show a duplicate hero subject outside the stamp. Add only a small neutral issue title and optional `PHOTO DETAILS: UNVERIFIED` outside the stamp when facts are unavailable.

## 2. Variety pane

Use a large shared thematic background that remains plainly visible across at least 35% of the inner sheet. Place the 4–6 stamp block within that world; do not let a plain-paper stamp grid consume the full sheet. For one source photo, make the stamps visibly different selected styles while preserving the same subject; label styles outside the stamps only when legible. For multiple uploaded photos, keep one selected style consistent and assign one image per stamp. Maintain even gutters, all perforations, and a visually meaningful background field.

## 3. Repeated definitive pane

Use a simple 2×2, 2×3, or 3×3 grid of identical stamps. Place a separate, larger thematic illustration in the remaining part of the sheet rather than inside any stamp. Keep the repeated stamp identical in subject, label, denomination, palette, and print treatment.

## Country and denomination

For a realistic issue, derive country from verified photo location. If country remains unavailable, default the issuing country to the United States without claiming a U.S. capture location. Verify the country label and denomination convention with a current official postal-operator source before generating. Match the official symbol or service indicator, decimal separator, symbol placement, local country-name form, numeral treatment, and typographic hierarchy. Do not copy a nominal value blindly when it conflicts with official practice; standard U.S. domestic stamps use `USA FOREVER`, not a fixed numeric price. Do not use a real postal-authority logo unless the user provides permission and an appropriate asset.

## Composition constraints

- Avoid real postal authority names, flags, cancellation dates, and official-looking serial claims unless the user provides verified information.
- Use a neutral issue line such as `WHITE DUCK ISSUE` only when useful.
- Do not make the sheet look like a product UI, stamp album, or collage. Use one visual theme and restrained supporting typography.
- Preserve the uploaded subject faithfully, but do not place the unaltered original photo on the sheet unless the user explicitly asks for it.
- Match stamp orientation to the source composition, and keep the outer edge of souvenir sheets and miniature sheets straight and free of perforations.
- Reject any visible white glow or broad pale ring around perforation holes; tactile depth must remain microscopic and local to the cut edge.
