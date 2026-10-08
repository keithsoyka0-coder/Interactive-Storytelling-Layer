# Visual Story Layer — Implementation Plan

**Source design:** `docs/superpowers/specs/2026-10-07-visual-story-design.md`  
**State:** Complete — 2026-10-07

## Completed work

### 1. Source inventory

- Indexed 13 diagrams in the opening curated visual layer, 39 later figure captions, and the 2 raw Mermaid graph source blocks printed on PDF page 78: 54 visuals total.
- Recorded title/caption, PDF page, source form, confidence notes, chapter, and asset path for each item.
- Searched the extracted text of all 116 PDF pages for Mermaid syntax markers; the two page-78 snippets were the only raw Mermaid blocks found.
- Kept the older 98-block project exhibit out of the source corpus; it was not merged.
- No exceptions were identified within the discovered 54-item inventory.

### 2. Extraction and validation

- Preserved the 13 opening diagrams and 39 captioned figures as source-page crops rather than redrawing them.
- Reproduced and rendered the two Mermaid snippets from the printed PDF text, normalizing line wrapping for rendering while keeping labels and edge relationships.
- Inspected the PDF’s candidate figure pages and checked representative crops and a rendered Mermaid card visually.

### 3. Standalone experience

- Built a single-file HTML guide with three entry depths, seven story chapters, a searchable visual atlas, global previous/next navigation, depth tabs, image zoom, and source/page attribution.
- Added selectable key-idea explanations to the 13 curated cards. These controls are explicitly explanatory text, not coordinate-level hotspots; the PDF does not supply reliable node geometry across the preserved figures.
- Embedded all 54 images. The standalone HTML contains no external script, stylesheet, or image dependencies.

### 4. Verification

- `python3 -m unittest discover -s tests -v` — passed.
- Browser smoke checks — entry-depth selection, atlas search, Mermaid-card navigation, key-part selection, depth-dependent part explanation, image zoom/keyboard dismissal, arrow-key story navigation, mobile drawer, and no horizontal overflow at 390px; browser console reported no errors.
- Opened the HTML directly with headless Chrome and received the rendered page title and entry screen.
- Source-pack ZIP integrity and the 54-row CSV index verified; preview endpoint returned HTTP 200.

## Scope and limitations

The verified count is based on the 13 explicit diagrams in the opening visual layer, the 39 later `Figure` captions, and all Mermaid syntax blocks found in the PDF text. It is not a claim that every uncaptioned illustration or decorative graphic anywhere in the wiki has been catalogued. PDF crops can include adjacent text to preserve context. Where Mermaid source was absent, the original PDF rendering—not an inferred reconstruction—is the visual source of record.
