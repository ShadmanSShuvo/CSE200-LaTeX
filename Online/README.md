# CSE200 LaTeX Online

This repository contains a set of standalone LaTeX write-ups for CSE200-style coursework. Each folder is its own mini project with a `main.tex` entry point, supporting source files, and its own bibliography. The documents are written as short, polished academic handouts rather than a single combined book.

## Project Layout

Each top-level folder can be compiled independently. Pre-compiled standalone PDFs as well as a merged master document are available in the [`all/`](./all/) directory.

| Folder | Topic | Entry Point | Pre-compiled PDF | Notes |
| --- | --- | --- | --- | --- |
| [`A1-knot/`](./A1-knot/) | Knot Theory | [`main.tex`](./A1-knot/main.tex) | [`Online_A1.pdf`](./all/Online_A1.pdf) | Multi-part article with shared [`preamble.tex`](./A1-knot/preamble.tex), section files `1.tex` through `7.tex`, and [`refs.bib`](./A1-knot/refs.bib). |
| [`A2-firefly/`](./A2-firefly/) | Fireflies in Union | [`main.tex`](./A2-firefly/main.tex) | [`Online_A2.pdf`](./all/Online_A2.pdf) | Article on synchronization in fireflies, split across `1.tex` through `6.tex`, with [`preamble.tex`](./A2-firefly/preamble.tex) and [`firefly_refs.bib`](./A2-firefly/firefly_refs.bib). |
| [`B1-laplace/`](./B1-laplace/) | Laplace Analysis and Applications | [`main.tex`](./B1-laplace/main.tex) | [`Online_B1.pdf`](./all/Online_B1.pdf) | Self-contained article with [`main.tex`](./B1-laplace/main.tex), [`laplace.bib`](./B1-laplace/laplace.bib), and the helper script [`rc_response.py`](./B1-laplace/rc_response.py). |
| [`B2-dna/`](./B2-dna/) | DNA Data Storage | [`main.tex`](./B2-dna/main.tex) | [`Online_B2.pdf`](./all/Online_B2.pdf) | Self-contained article with figures, [`main.tex`](./B2-dna/main.tex), and [`dna_storage_refs.bib`](./B2-dna/dna_storage_refs.bib). |
| [`C1-riemann/`](./C1-riemann/) | The Riemann Hypothesis | [`main.tex`](./C1-riemann/main.tex) | [`Online_C1.pdf`](./all/Online_C1.pdf) | Mathematical handout with table of contents, theorem-style formatting, and [`riemann_hypothesis_refs.bib`](./C1-riemann/riemann_hypothesis_refs.bib). |
| [`C2-solar/`](./C2-solar/) | The Solar System | [`main.tex`](./C2-solar/main.tex) | [`Online_C2.pdf`](./all/Online_C2.pdf) | Illustrated article with planets, tables, and [`solar_system.bib`](./C2-solar/solar_system.bib). |
| [`all/`](./all/) | Pre-compiled PDF Archive | — | [`Online_all.pdf`](./all/Online_all.pdf) | Central delivery folder containing all compiled individual PDFs and the combined document. |

## Pre-compiled Deliverables (`all/`)

The [`all/`](./all/) directory hosts all pre-compiled PDF artifacts for quick access without requiring a local LaTeX installation:

- **Unified Document**:
  - [`all/Online_all.pdf`](./all/Online_all.pdf) — Merged master document containing all six online write-ups in sequence.
- **Standalone Handouts**:
  - [`all/Online_A1.pdf`](./all/Online_A1.pdf) — Knot Theory
  - [`all/Online_A2.pdf`](./all/Online_A2.pdf) — Fireflies in Union
  - [`all/Online_B1.pdf`](./all/Online_B1.pdf) — Laplace Analysis and Applications
  - [`all/Online_B2.pdf`](./all/Online_B2.pdf) — DNA Data Storage
  - [`all/Online_C1.pdf`](./all/Online_C1.pdf) — The Riemann Hypothesis
  - [`all/Online_C2.pdf`](./all/Online_C2.pdf) — The Solar System

## What Is in Each Folder?

Most project folders follow the same pattern:

- `main.tex` is the document entry point.
- `preamble.tex`, when present, holds shared packages, colors, and custom commands.
- `*.bib` stores references for `biblatex`.
- Additional `.tex` files split the write-up into manageable sections.
- Image files, when used, live beside the document they belong to.
- `all/` contains pre-compiled individual and merged PDFs.

This layout makes it easy to compile, edit, and grade one assignment at a time.

## Requirements

To build the documents, install a LaTeX distribution such as:

- TeX Live
- MacTeX on macOS
- MiKTeX on Windows

You will also need `biber`, because the documents use `biblatex` with the `biber` backend.

For the `B1-laplace/` folder, `python3` may be useful if you want to run the helper script `rc_response.py`.

## How to Compile

The easiest way is to use `latexmk` from inside the folder you want to build:

```bash
cd A1-knot
latexmk -pdf main.tex
```

Repeat the same pattern for any other folder:

```bash
cd A2-firefly
latexmk -pdf main.tex
```

If you prefer to compile manually, use this sequence for documents that depend on bibliographies:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

The output PDF will be created in the same folder as `main.tex`.

## Suggested Workflow

1. Open the folder you want to work on.
2. Edit the relevant `.tex` files and any bibliography entries.
3. Rebuild the document with `latexmk -pdf main.tex`.
4. Check the PDF for layout issues, missing references, and figure placement.
5. Repeat until the document reads cleanly from start to finish.

## Notes for Students

- Keep each project self-contained so it can be compiled on its own.
- Use short section files when a document becomes long or easier to manage in pieces.
- Keep figure files in the same folder as the document that uses them.
- Re-run the build after changing citations, labels, or cross-references.

## Repository Purpose

The repository is organized as a collection of polished class-style handouts covering different mathematical and scientific topics. The focus is on clear presentation, structured exposition, and reproducible LaTeX builds.
