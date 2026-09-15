---
name: visual-first-editable-ppt
description: "Create polished PowerPoint decks with a visual-first workflow: analyze source material, plan slide structure, generate 16:9 slide visual drafts for approval, then rebuild the approved design as an editable PPTX with native text, tables, charts, shapes, and hybrid image assets. Use whenever the user wants a PPT that must be both visually strong and editable, especially when direct PPT generation looks worse than image-based slide mockups."
---

# Visual-First Editable PPT

Use this skill for presentations where design quality matters and the final `.pptx` must remain editable.

The user's explicit instructions override defaults in this skill. Do not collapse the workflow into direct PPT generation unless the user explicitly asks to skip visual drafting.

## Core workflow

Follow this sequence:

`source analysis -> slide plan -> 2-3 representative visual drafts -> user design approval -> full visual draft set -> user final visual approval -> editable PPT rebuild -> render-and-compare QA -> final PPTX`

The two approval gates are intentional. Avoid extra interruptions unless a missing fact would materially change the deck.

## 1. Analyze the source material

Read all supplied Word, PDF, Excel, image, screenshot, or text material before designing.

Extract:
- presentation objective and audience;
- narrative order and page count;
- facts, figures, tables, charts, diagrams, and images that must be preserved;
- recurring terminology and source wording that should not be altered;
- visual references, brand cues, logos, and color constraints.

Do not mechanically paste source text into slides. Convert content into presentation logic while preserving factual meaning.

If the source material is sufficient, continue without asking routine questions. Ask only when a missing decision would materially affect accuracy, page count, or overall direction.

## 2. Plan the deck

Prepare a concise slide plan with:
- slide number;
- slide title;
- core message;
- content blocks;
- recommended layout or visualization.

Prefer one clear message per slide. Split overloaded pages rather than shrinking text excessively.

Unless the user asks for a review of the outline first, proceed from the slide plan directly to representative visual drafts.

## 3. Generate representative visual drafts first

Before building the actual PowerPoint, generate 2-3 representative slide images that establish the visual system. Choose pages that collectively cover different layout types, normally:
- cover or section opener;
- core content / information-dense slide;
- process, comparison, data, or diagram slide.

Use the best available image-generation capability in the current environment. The output must look like a real 16:9 presentation slide, not a poster, webpage, long infographic, or concept-art image.

Default visual direction when the user gives no other style:
- 16:9 widescreen;
- white background;
- restrained blue government / technology style;
- professional, clean, high information hierarchy;
- strong alignment and whitespace;
- consistent card radii, spacing, icon style, and title hierarchy;
- no decorative effects that do not support the content.

If a reference image is supplied, treat it as the primary visual language. Match composition, spacing, hierarchy, card structure, and overall tone rather than merely copying its colors.

### Visual-draft rules

- Use correct Chinese text where possible; do not accept meaningless pseudo-text as a final design draft.
- Keep all important text inside safe margins.
- Use realistic slide density and readable font sizes.
- Build layouts that can later be reconstructed with native PowerPoint objects.
- Avoid visual effects that would force the entire final slide to become a flattened image.

Stop after the representative pages and wait for the user to approve the visual direction or request changes.

## 4. Produce the full visual draft set

After the user approves the representative style, create the remaining slide visual drafts with the same design system.

Keep these consistent across the deck:
- page grid and margins;
- title positions and hierarchy;
- type scale;
- primary / secondary colors;
- card geometry;
- icon family;
- chart treatment;
- footer, page marker, and section conventions if used.

Revise visual drafts based on user feedback. Do not build the final `.pptx` until the user clearly approves the visual draft set or asks to start editable reconstruction.

## 5. Rebuild the approved visual draft as editable PPTX

Treat the approved visual images as design references, not as slide backgrounds.

Reconstruct the slide using native objects wherever editing is likely to matter.

### Font selection: user choice first, Microsoft YaHei by default

Font choice is configurable. Apply this priority order:
1. The user's latest explicit font instruction takes precedence, including a later request to change a previously selected font. Apply it to the specified scope (the whole deck, a slide, titles, body text, Chinese, or English). Do not reject a requested font change or force Microsoft YaHei because it is the default.
2. For text outside that scope, preserve template fonts only when the user requests font preservation.
3. Use **Microsoft YaHei (微软雅黑)** for remaining text with no font instruction, including Chinese, English, numbers, and punctuation.

Apply the resolved font choices to titles, body text, labels, table cells, chart text, and footers as appropriate. Set Latin and East Asian font settings, theme defaults, and inline runs to respect the chosen language/scope; do not overwrite an explicitly chosen English font with Microsoft YaHei.

Examples: with no font specified, use Microsoft YaHei throughout. If the user says “全部改为宋体”, use SimSun throughout. If they say “中文微软雅黑，英文 Arial”, use that language-specific combination. If they later say “标题改成黑体”, change only the titles and retain the other font choices.

If a selected font is unavailable for rendering, explain the limitation and offer an available alternative. Use an alternative when the user chooses it or has authorized substitution; never silently replace their choice. This availability check does not prohibit the user from choosing or changing fonts.

### Text boxes follow semantic content blocks

- Keep each paragraph or coherent content block in one text box, with wrapping, line breaks, paragraph spacing, and list formatting inside that box. A multi-line paragraph or a related numbered/bulleted list must not become one text box per visual line or list item.
- Separate boxes are appropriate for distinct content blocks, such as a paragraph's subheading and its body, different cards, independent labels, or separately positioned diagram nodes. Native table cells remain separate cells.
- Keep inline emphasis, red keywords, bold text, English abbreviations, and numbers as formatted runs within the same text box. A style change alone is not a reason to split a content block.
- For screenshot reconstruction, use OCR lines only to recover reading order; merge lines into semantic paragraphs or lists before creating text boxes. Do not create text boxes by looping over screenshot lines, and do not treat grouping many line boxes as equivalent to one editable text box.
- Preserve layout through box width, internal margins, line spacing, and paragraph spacing. Do not split a paragraph into line boxes just to match pixel positions. Editing a sentence or resizing its box should reflow the whole content block.

Example: a subheading “监测要求” and three related requirements use two text boxes: one for the subheading and one containing all three requirements as native list paragraphs. A wrapped requirement stays in that second box; “CEMS” and highlighted words stay as inline runs.

### Native editable objects

Must normally be editable:
- titles, subtitles, body copy, labels, annotations, and numbers -> PowerPoint text boxes;
- structured tabular content -> native PowerPoint tables;
- bar, line, pie, and similar data visualizations -> native PowerPoint charts when practical;
- cards, panels, pills, borders, separators, arrows, labels, process boxes -> PowerPoint shapes;
- process relationships -> shapes plus connectors;
- simple icons -> SVG/vector assets when available.

May remain image assets:
- photos;
- complex illustrations;
- detailed maps;
- highly textured decorative backgrounds;
- complex light effects;
- visual elements whose native reconstruction would add substantial complexity without useful editability.

Use a hybrid editable model: preserve editability for content the user or leadership is likely to change; preserve image assets only for complex decorative or illustrative components.

Never satisfy an "editable PPT" request by placing a full-slide screenshot as the background and adding little or no editable content on top.

## 6. Preserve the approved composition

When rebuilding, prioritize the approved visual draft's:
- relative positions;
- alignment;
- whitespace;
- card dimensions;
- text block widths;
- visual hierarchy;
- icon scale;
- chart proportions;
- balance of left/right and top/bottom visual weight.

Use the draft as an underlay or measurement reference during reconstruction if useful, then remove the full-slide underlay before final delivery unless the user explicitly asks to retain it.

## 7. Render-and-compare QA

After generating the editable `.pptx`, render every slide back to an image and compare it with the approved visual draft. Use [the QA checklist](references/qa-checklist.md) to inspect typography and content-block editability as well as visual appearance.

Check:
- slide aspect ratio;
- title and body placement;
- fonts match the user's latest choices and their scope; Microsoft YaHei applies only where no font choice or requested template preservation applies; check font size and line breaks;
- one text box per semantic paragraph/content block, with inline emphasis retained as runs;
- card width and height;
- object alignment;
- spacing and margins;
- color consistency;
- icon size and placement;
- chart geometry;
- overall visual center of gravity.

When tooling permits, use side-by-side comparison, semi-transparent overlay, or image-difference inspection to find obvious drift. Correct visible discrepancies before final delivery.

Do not treat "file opens successfully" or "objects are editable" as sufficient QA. The final deck must remain visually close to the approved draft.

## 8. Deliverables

Final delivery should normally include:
- editable `.pptx`;
- optional rendered slide previews when useful for review;
- optional PDF only when requested.

Briefly state which elements remain raster images if that matters to editing.

## Design and editing priorities

When trade-offs occur, use this order:

1. factual accuracy and completeness;
2. approved visual composition;
3. editability of content likely to change;
4. consistency across the deck;
5. efficiency of implementation.

Do not sacrifice the approved visual design merely to make every decorative detail editable.

## Default working style

For government, environmental, supervision, engineering, information-system, and technical-report decks, default to a polished white-and-blue professional style unless the user specifies otherwise. Favor clear diagrams, native tables, structured cards, and restrained technology motifs over flashy gradients or generic AI aesthetics.
