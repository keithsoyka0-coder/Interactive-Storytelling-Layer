# GestaltView Visual Story

A self-contained static guide to the diagrams and figures in the GestaltView Master Wiki v4.0. The host-ready entry point is [`index.html`](index.html).

## Host it

There is **no frontend build step**: no Node install, package manager, backend, API key, database, or external image/font/script dependency. The 54 visuals and the story data are embedded in `index.html`.

Publish the repository root as a static site document root. The single file required at runtime is `index.html`; the remaining files provide source provenance, editable template/builder code, tests, and extracted assets. If your host asks for a build command, leave it empty; set the publish/output directory to the repository root (`.`).

For a local preview from this directory:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`. You may also open `index.html` directly in a modern browser.

## What readers get

The opening screen offers three levels: **Get oriented**, **Understand the system**, and **Explore the architecture**. The guide includes seven narrative chapters, a searchable visual atlas, source page references, depth-specific explanations, image zoom, keyboard navigation, and selectable key-idea explanations on the 13 curated diagrams.

The key-idea selectors are reading aids, not spatial hotspots: the source PDF does not provide reliable node coordinates for all the preserved figures. The page crop remains the visual authority.

## Repository contents

- `index.html` — complete, self-contained static site
- `story_template.html`, `build_story_artifact.py` — editable HTML template and source builder
- `story_assets/` — 54 source-page crops / Mermaid renders and the two Mermaid text files
- `diagram_inventory.json`, `diagram_index.csv` — source references, explanations, provenance, part labels, and asset map
- `tests/` — acceptance checks for coverage, attribution, depth lenses, assets, and navigation
- `docs/` — approved design and implementation/provenance notes
- `requirements-build.txt` — Python libraries used by the optional PDF rebuild workflow

## Rebuild the site from the PDF

The PDF is intentionally **not included**. It is not needed to host the current guide; keeping it separate avoids bundling the full wiki when the rendered guide is all that is required. To rebuild, provide your own copy of `GestaltView_Master_Wiki_v4.0.pdf` either in this directory or as the builder's argument:

```bash
python3 -m pip install -r requirements-build.txt
python3 build_story_artifact.py /path/to/GestaltView_Master_Wiki_v4.0.pdf
python3 -m unittest discover -s tests -v
```

The builder writes refreshed `index.html`, `diagram_inventory.json`, and `story_assets/`. It uses `manus-render-diagram` to render the two Mermaid snippets; that utility is separate from the Python requirements and must be available in the rebuild environment. The shipped `index.html` and rendered assets are ready to host without running the builder.

## Validation

Run the acceptance test from the repository root:

```bash
python3 -m unittest discover -s tests -v
```

The inventory records 13 curated opening diagrams, 39 later captioned figures, and two printed Mermaid source snippets (54 visuals total). Read [`docs/SOURCE_PROVENANCE.md`](docs/SOURCE_PROVENANCE.md) before making claims about source coverage or diagram status.

## Rights and publication

No open-source license is assigned by this package. Before public hosting or redistribution, confirm that you have the necessary rights for the wiki content and derived visual crops. See [`LICENSE-NOTICE.md`](LICENSE-NOTICE.md).
