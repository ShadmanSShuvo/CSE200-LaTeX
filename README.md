# CSE 200: Technical Writing and Presentation (LaTeX)

This repository serves as a centralized collection of LaTeX source documents, research paper reproductions, presentation slide decks, and academic evaluations for the **CSE 200: Technical Writing and Presentation** course.

---

## 📁 Repository Structure

| Directory | Type | Description | Key Deliverables |
| :--- | :--- | :--- | :--- |
| [`Assignment/`](./Assignment/) | Research Paper | Full ACM-formatted (`acmart`) reproduction of *"Migrating Code At Scale With LLMs At Google"*, split into modular section files with figures and citations. | [`Assignment/main.pdf`](./Assignment/main.pdf) |
| [`Online/`](./Online/) | Academic Handouts | Collection of 6 independent mathematical and scientific write-ups (Knot Theory, Fireflies, Laplace, DNA Storage, Riemann Hypothesis, Solar System). | [`Online/all/Online_all.pdf`](./Online/all/Online_all.pdf)<br>*(See [`Online/README.md`](./Online/README.md))* |
| [`Presentation/`](./Presentation/) | Beamer Slide Deck | Comprehensive presentation on *Segment Trees* (A1-Group 8), utilizing TikZ vector diagrams and modern Beamer visual styling. | [`Presentation/Segment Tree - CSE200 Presentation.pdf`](./Presentation/Segment%20Tree%20-%20CSE200%20Presentation.pdf) |
| [`Report/`](./Report/) | Technical Report | Formal report on *Segment Trees: Fast Range Queries and Dynamic Updates*, featuring TikZ data structure visualizations, algorithmic listings, and styled PDF variants. | [`Report/segment-tree-report-v2.pdf`](./Report/segment-tree-report-v2.pdf) |

---

## 📑 Detailed Component Breakdown

### 1. Research Paper Assignment ([`Assignment/`](./Assignment/))
- **Format**: ACM Conference / Manuscript (`acmart.cls`, `manuscript,review`)
- **Topic**: *Migrating Code At Scale With LLMs At Google* (Celal Ziftci et al.)
- **Structure**:
  - [`main.tex`](./Assignment/main.tex): Master entry point containing document metadata and author affiliations.
  - Section files: `0-abstract.tex`, `1-intro.tex`, `2-related.tex`, `3-method.tex`, `4-findings.tex`, `5-discussion.tex`.
  - [`references.bib`](./Assignment/references.bib): BibTeX reference database formatted in `ACM-Reference-Format`.
  - Figures and workflow schematics (`system-overview.png`, `code-diff.png`, `sample-language-context.png`, etc.).
  - Output PDF: [`Assignment/main.pdf`](./Assignment/main.pdf).

### 2. Online Handouts ([`Online/`](./Online/))
For comprehensive documentation on the online evaluations, refer to [`Online/README.md`](./Online/README.md).

- **Modules**:
  - [`A1-knot/`](./Online/A1-knot/): Knot Theory (multi-part article with shared preamble and knot diagrams).
  - [`A2-firefly/`](./Online/A2-firefly/): Fireflies in Union (synchronization dynamics in biological systems).
  - [`B1-laplace/`](./Online/B1-laplace/): Laplace Analysis and Applications (circuit analysis and Python helper script).
  - [`B2-dna/`](./Online/B2-dna/): DNA Data Storage (synthetic biology & digital archives).
  - [`C1-riemann/`](./Online/C1-riemann/): The Riemann Hypothesis (critical strip, zeros, and zeta function).
  - [`C2-solar/`](./Online/C2-solar/): The Solar System (illustrated planetary guide, tables, and celestial physics).
- **Compiled Deliverables ([`Online/all/`](./Online/all/))**:
  - [`Online_all.pdf`](./Online/all/Online_all.pdf): Unified master PDF containing all six online write-ups in sequence.
  - Individual pre-compiled PDFs: [`Online_A1.pdf`](./Online/all/Online_A1.pdf) through [`Online_C2.pdf`](./Online/all/Online_C2.pdf).

### 3. Presentation Slides ([`Presentation/`](./Presentation/))
- **Format**: LaTeX Beamer (`beamer`, `aspectratio=169`)
- **Topic**: *Segment Trees: Representation, Range Queries, Point Updates, and Lazy Propagation*
- **Highlights**:
  - Built with custom color palettes and modular slide decks.
  - Native TikZ drawings of tree structures, recursive splits, range intervals, and array representations.
  - Primary deck: [`Presentation/Segment Tree - CSE200 Presentation.pdf`](./Presentation/Segment%20Tree%20-%20CSE200%20Presentation.pdf) (compiled from [`main.tex`](./Presentation/main.tex) / [`segment tree-v2.tex`](./Presentation/segment%20tree-v2.tex)).

### 4. Technical Report ([`Report/`](./Report/))
- **Topic**: *Segment Tree: Fast Range Queries and Dynamic Updates*
- **Authors**: Shayan Un Noor (2305024), Md. Shadman Shahriyar Shuvo (2305025), Md. Wasif Haque (2305029)
- **Source Files**:
  - [`segment-tree-report-v2.tex`](./Report/segment-tree-report-v2.tex): Main report source with navy/cream color palette matching the presentation, TikZ tree node styling, C++ algorithmic code listings (`listings`), and hyperref configuration.
  - [`segment-tree-report.tex`](./Report/segment-tree-report.tex): Baseline technical report implementation.
- **Compiled PDF Variants**:
  - [`segment-tree-report-v2.pdf`](./Report/segment-tree-report-v2.pdf): Standard LaTeX article layout.
  - [`segment-tree-report-v2-scrartcl.pdf`](./Report/segment-tree-report-v2-scrartcl.pdf): KOMA-Script article layout.
  - [`segment-tree-report-v2 -scrartcl-toc.pdf`](./Report/segment-tree-report-v2%20-scrartcl-toc.pdf): KOMA-Script layout including Table of Contents.
  - [`segment-tree-report-v2 -scrartcl-toc-textsc.pdf`](./Report/segment-tree-report-v2%20-scrartcl-toc-textsc.pdf): KOMA-Script layout with Table of Contents and small-caps headers.
  - [`segment-tree-report-v2-prism.pdf`](./Report/segment-tree-report-v2-prism.pdf): Styled variant featuring prism syntax highlighting aesthetics.

---

## 🛠️ Prerequisites & Requirements

To compile the documents in this repository, ensure a full LaTeX distribution is installed:

- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Linux**: TeX Live (`sudo apt install texlive-full` or distribution equivalent)
- **Windows**: [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/)

### Required Engines & Tools
- `pdflatex` (or `latexmk` for automated dependency and pass resolution)
- `bibtex` (used for the [`Assignment/`](./Assignment/) ACM format)
- `biber` (used for `biblatex` in [`Online/`](./Online/) write-ups)
- `python3` (optional, for auxiliary plotting scripts such as `Online/B1-laplace/rc_response.py`)

---

## 🚀 Compilation Instructions

### Using `latexmk` (Recommended)
`latexmk` automatically resolves cross-references, index generation, and bibliography passes:

```bash
# 1. Compile Research Paper Assignment
cd Assignment
latexmk -pdf main.tex

# 2. Compile Presentation Slides
cd ../Presentation
latexmk -pdf main.tex

# 3. Compile an Online Handout (e.g., A1-knot)
cd ../Online/A1-knot
latexmk -pdf main.tex

# 4. Compile Technical Report
cd ../Report
latexmk -pdf segment-tree-report-v2-2.tex
```

### Manual Compilation Sequences

#### For `Assignment/` (ACM Format with BibTeX):
```bash
cd Assignment
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

#### For `Online/` Handouts (BibLaTeX with Biber):
```bash
cd Online/A1-knot
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

#### For `Presentation/` (Beamer with TikZ):
```bash
cd Presentation/A1-Group8
pdflatex segment-tree.tex
pdflatex segment-tree.tex
```

#### For `Report/` (LaTeX Article with TikZ & Listings):
```bash
cd Report/A1-Group8
pdflatex segment-tree.tex
pdflatex segment-tree.tex
```

---

## 💡 Best Practices for Contributors

1. **Modular Source Files**: Split lengthy documents into logical section files (`\input{...}`) for easy collaboration and diff inspection.
2. **Co-located Assets**: Keep figures, bib files, and helper scripts in the same folder as their corresponding `.tex` documents.
3. **Build Artifact Hygiene**: Keep git commits clean by relying on `.gitignore` for auxiliary LaTeX files (`*.aux`, `*.bbl`, `*.bcf`, `*.blg`, `*.log`, `*.nav`, `*.out`, `*.run.xml`, `*.snm`, `*.toc`).
