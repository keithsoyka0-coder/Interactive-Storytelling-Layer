# Source provenance and inventory scope

## Source

The guide was built from `GestaltView_Master_Wiki_v4.0.pdf` (116 pages). The PDF itself is not included in this host bundle. The page references in `diagram_index.csv` and `diagram_inventory.json` point back to that version.

## What is included

| Source form | Count | Handling |
|---|---:|---|
| Opening curated diagram layer | 13 | Preserved from PDF page crops; the PDF text does not print Mermaid source for these diagrams |
| Later captioned figures | 39 | Preserved as source-page crops, not redrawn |
| Printed Mermaid source blocks | 2 | Both occur on PDF page 78; reproduced from the printed source text and rendered |
| **Total visuals** | **54** | Each item has a page reference, source form, confidence note, and story chapter |

A search across the extracted text of all 116 pages found two raw Mermaid graph blocks. Their printed line wrapping is normalized in the `.mmd` files so they render, while their labels and edge relationships are retained. The two Mermaid source and render files are in `story_assets/`.

The 13 curated cards add selectable key-idea explanations at each reading depth. These controls are explanatory text, not pixel-position overlays. No node coordinates are asserted where the source PDF does not provide reliable geometry.

## Limits

The inventory covers the explicit opening diagram set, the 39 later `Figure` captions, and the Mermaid syntax blocks discoverable in extracted PDF text. It is not a claim that every uncaptioned illustration or decorative graphic in the PDF has been catalogued. Some page crops retain nearby text for attribution and context. A source diagram indicates a documented relationship; it does not prove that every depicted path is live in a runtime.

Use the source PDF as the authority for exact wording and visual context. Each item in the CSV and JSON has a PDF page reference. No source-PDF files, credentials, deployment secrets, or external-service keys are included in this repository.
