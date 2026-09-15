# Editable PPT reconstruction QA checklist

Use this only during the final reconstruction and comparison stage.

## Content
- No missing slide, title, figure, table, label, or required conclusion.
- Source numbers and terminology remain correct.
- Chinese punctuation, units, and abbreviations are consistent.

## Geometry
- Slide is 16:9 unless the user requested another ratio.
- Major blocks match the approved visual draft in position and proportion.
- Repeated components use consistent dimensions and spacing.
- No accidental overflow, clipping, overlaps, or text outside cards.

## Typography
- Fonts follow the user's latest choices, including later font changes and language/slide/title/body scope. The default must never override an explicit choice.
- Only text without a user font choice or requested template-font preservation defaults to Microsoft YaHei (微软雅黑), including English, numbers, punctuation, and table/chart text.
- Check both Latin and East Asian font settings and inline runs; no unintended theme-font fallback.
- Title hierarchy is consistent.
- Body text is readable at presentation scale.
- Line breaks visually match the approved design as closely as practical.
- Text is native/editable unless it is part of an intentionally rasterized illustration.

## Editability
- Editable text remains text.
- Each paragraph or coherent content block, including a related list, is one text box rather than separate boxes per line or list item.
- Subheadings and body text may be separate boxes; distinct cards, labels, diagram nodes, and native table cells stay independent.
- Color/bold emphasis and English abbreviations are inline runs, not separate text boxes.
- Inspect object structure and try editing/resizing a representative multi-line block: its text should reflow together. Grouped line boxes do not pass this check.
- Data tables are native tables when practical.
- Charts are native charts when practical.
- Cards, separators, arrows, and process boxes are shapes.
- Full-slide screenshots are not used as a shortcut for editability.

## Visual match
- Compare each rendered slide with its approved draft.
- Check alignment, whitespace, color, card geometry, icon scale, chart proportions, and visual weight.
- Correct obvious differences before final delivery.
