# author-maps

Interactive combined co-authorship network for *Vespa* / EPF literature corpora curated in the [vespa-non-eu](https://github.com/marcory-hub/vespa-non-eu) project.

**Live map:** open [`index.html`](./index.html) (GitHub Pages: https://vespcv.github.io/author-maps/).

## What this is

- One self-contained HTML page (vis-network, layout precomputed; no server).
- Authors and edges from five source projects: vespa-non-eu, beauveria-bassiana, vespa-biocide, vespa-velutina-impact, vespa-velutina-toxine.
- Filter by `source_project`. Sibling corpora are **not** treated as non-EU includes.

## Identity merge

Runtime identity collapse uses only operator-approved rows in `author_aliases.csv` (in the source repo). Cross-project name-key matches are reviewed via a candidates CSV; nothing is auto-merged.

## What is not published

- Local PDF paths
- Funding / conflict-of-interest text
- Screening notes or private corpora

Affiliations appear only when stated on a source paper (not invented). Gaps stay empty.

## Rebuild / republish

From the vespa-non-eu repo:

```bash
.venv/bin/python 5_visualisation_reporting/network/scripts/build_merged.py
.venv/bin/python 5_visualisation_reporting/network/scripts/build_network_html.py
bash 5_visualisation_reporting/network/scripts/publish_author_maps.sh
```

Overwrite-only publish to fixed paths (`index.html`, `README.md`) on this repo’s default branch.

## License note

vis-network (Apache-2.0) is vendored/inlined in the HTML. Bibliographic metadata follows the underlying paper licenses / fair use for citation lists.
