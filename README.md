# Organization Profile & SFQ Paper Map (`.github`)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green?logo=creativecommons&logoColor=white)](https://creativecommons.org/licenses/by/4.0/)
[![GitHub Pages](https://img.shields.io/badge/Pages-SFQ%20Paper%20Map-181717?logo=github)](https://single-flux-quantum.github.io/.github/)
[![SFQ Learn](https://img.shields.io/badge/Learn-SFQ%20Curriculum-0A7EA4?logo=readthedocs&logoColor=white)](https://single-flux-quantum.github.io/sfq-learn-public/)
[![Corpus: 1352+ Papers](https://img.shields.io/badge/Corpus-1352%2B%20Papers-blue)](https://github.com/single-flux-quantum/sfq-lab)

Special GitHub organization repository for **[Single-Flux-Quantum](https://github.com/single-flux-quantum)**: [`profile/README.md`](profile/README.md) renders as the organization's public homepage, and [`docs/`](docs/) deploys to **GitHub Pages** as an interactive, client-side searchable and sortable **SFQ Paper Map** covering 1352+ curated research papers on superconducting digital electronics.

- **Repository**: https://github.com/single-flux-quantum/.github
- **Organization homepage**: https://github.com/single-flux-quantum
- **Interactive paper map**: https://single-flux-quantum.github.io/.github/
- **SFQ learning curriculum**: https://single-flux-quantum.github.io/sfq-learn-public/
- **Parent lab monorepo**: [single-flux-quantum/sfq-lab](https://github.com/single-flux-quantum/sfq-lab) (syncs this tree from `share/github`)
- **License**: CC BY 4.0 (see [`LICENSE`](LICENSE))

## TL;DR

- **Topic**: Single Flux Quantum (SFQ) and superconducting digital electronics research
- **Total papers**: 1352 curated catalog entries (export from `sfq-lab/papers`)
- **Modality**: Structured bibliographic database (`papers.json`), static org homepage (`profile/README.md`), and client-side web application (`docs/index.html`)
- **Learning**: Beginner curriculum in [sfq-learn-public](https://github.com/single-flux-quantum/sfq-learn-public)
- **Research domains**: 9 core categories (Circuits & Logic, Cryo-EDA, Clocking & Power, Hybrid CMOS Interfaces, Cryo-Memory, Compute/Processors, Quantum & Detectors, Sensors & Metrology, Cell Libraries)
- **Deployment**: Zero-dependency static site hosted on GitHub Pages via Actions or direct branch deployment
- **Synchronization**: Automated regeneration from parent lab via `python scripts/export_papers_catalog.py`
- **Citation**: See [Citation](#citation) below

## Table of contents

- [Features](#features)
- [Project Layout](#project-layout)
- [Catalog Schema](#catalog-schema)
- [Stats and Distribution](#stats-and-distribution)
  - [Temporal distribution](#temporal-distribution)
  - [Publication venues](#publication-venues)
  - [Research domain coverage](#research-domain-coverage)
- [Quick Start](#quick-start)
  - [1. Standalone clone](#1-standalone-clone)
  - [2. Activating GitHub Pages](#2-activating-github-pages)
  - [3. Running locally](#3-running-locally)
  - [4. Synchronizing from parent lab](#4-synchronizing-from-parent-lab)
- [Datasheet](#datasheet)
  - [Motivation](#motivation)
  - [Composition](#composition)
  - [Collection and curation process](#collection-and-curation-process)
  - [Maintenance](#maintenance)
- [Known Issues and Limitations](#known-issues-and-limitations)
- [License](#license)
- [Citation](#citation)
- [References](#references)
- [Contact](#contact)

## Features

| Path | Role |
| :--- | :--- |
| [`profile/README.md`](profile/README.md) | Organization landing page (curated intro, taxonomy diagram, and full static paper catalog) |
| [`docs/index.html`](docs/index.html) | Interactive Paper Map web application (instant search, domain filter pills, multi-column sort, theme switcher) |
| [`docs/papers.json`](docs/papers.json) | Structured JSON dataset containing complete metadata, DOIs, and innovation summaries |
| [`docs/.nojekyll`](docs/.nojekyll) | Bypasses Jekyll processing on GitHub Pages for fast and reliable static asset delivery |
| [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) | GitHub Actions deployment pipeline for GitHub Pages |
| [`LICENSE`](LICENSE) | Creative Commons Attribution 4.0 International license |

> [!NOTE]
> Do **not** manually edit `profile/README.md` or `docs/papers.json`. Refresh them from the parent lab using `python scripts/export_papers_catalog.py`.

## Project Layout

```text
.github/
├── .github/
│   └── workflows/
│       └── deploy-pages.yml      # GitHub Actions deployment to Pages
├── docs/
│   ├── .nojekyll                 # Disables Jekyll build engine on Pages
│   ├── index.html                # Interactive Paper Map single-page app
│   └── papers.json               # 156-paper catalog database
├── profile/
│   └── README.md                 # Public GitHub org homepage
├── LICENSE                       # CC BY 4.0 license deed notice
└── README.md                     # Repository documentation
```

## Catalog Schema

Each item in [`docs/papers.json`](docs/papers.json) contains the following fields:

- `slug` (*string*): Unique URL-safe identifier matching the directory in `sfq-lab/papers/<slug>/`.
- `title` (*string*): Clean full paper title without LaTeX formatting artifacts.
- `authors` (*string*): Semicolon-delimited list of author names.
- `year` (*string*): Four-digit publication year (1989–2026).
- `venue` (*string*): Normalized journal or conference venue name.
- `category` (*string*): Primary and secondary human-readable category slugs.
- `categories` (*array of strings*): Multi-label list of matching domain categories.
- `innovation` (*string*): 1–2 sentence summary of core contribution or experimental demonstration.
- `url` (*string*): Direct DOI resolver link (`https://doi.org/...`) or fallback analysis link.
- `doi` (*string*): Digital Object Identifier string.

### Minimal Real Example

```json
{
  "slug": "single-source-sfq-multiclock-generator-using-resistor-jtl-branches",
  "title": "Single Source SFQ Multiclock Generator Using Resistor–JTL Branches",
  "authors": "Tejumadejesu Oluwadamilare, Shay Hacohen-Gourgy; Eby G. Friedman",
  "year": "2026",
  "venue": "IEEE Trans. Appl. Supercond.",
  "category": "clocking-and-power, hybrid-interfaces",
  "categories": [
    "clocking-and-power",
    "hybrid-interfaces",
    "compute-architectures",
    "quantum-and-detectors"
  ],
  "innovation": "A compact, scalable, and energy-efficient on-chip SFQ multiclock generation architecture capable of generating multiple, independent, stable clock frequencies simultaneously from a single constant DC voltage source.",
  "url": "https://doi.org/10.1109/TASC.2025.3630889",
  "doi": "10.1109/TASC.2025.3630889"
}
```

## Stats and Distribution

### Temporal distribution

The 156 papers span foundational milestones through 2026 state-of-the-art:

| Timeframe | Paper Count | Representative Focus |
| :--- | :---: | :--- |
| **2023–2026** | 50 | Millikelvin qubit controllers, 50-GFLOPS FPUs, InductEx crosstalk mitigation, 4-Nb cell libraries |
| **2019–2022** | 68 | qSTA/qSSTA timing analysis, current recycling, hybrid CMOS memory interfaces, PTL routing |
| **2015–2018** | 24 | ERSFQ low-power benchmarking, sub-flux feedback SQUIDs, gate-level pipelining |
| **Prior to 2015** | 14 | Foundational RSFQ logic families, early Josephson DAC/ADCs, latching drivers |
| **Total** | **156** | **Complete corpus** |

### Publication venues

| Venue | Count | Share |
| :--- | :---: | :---: |
| IEEE Transactions on Applied Superconductivity (*IEEE Trans. Appl. Supercond.*) | 151 | 96.8% |
| IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems (*IEEE TCAD*) | 2 | 1.3% |
| IEEE Transactions on Very Large Scale Integration Systems (*IEEE TVLSI*) | 2 | 1.3% |
| Superconductor Science and Technology (*Supercond. Sci. Technol.*) | 1 | 0.6% |

### Research domain coverage

Papers are classified using multi-label tagging across 9 core SFQ sub-disciplines:

| Domain Slug | Display Name | Papers Tagged |
| :--- | :--- | :---: |
| `quantum-and-detectors` | Quantum Control & Detector Readout | 144 |
| `clocking-and-power` | Clocking & Power Distribution Networks | 131 |
| `cryo-memory` | Cryogenic Memory & Storage Systems | 129 |
| `circuits-and-logic` | Logic Families (RSFQ, ERSFQ, AQFP, 4JL) | 116 |
| `compute-architectures` | Microprocessors & Digital Compute | 98 |
| `cell-library-and-fabrication` | Cell Libraries & Fabrication Processes | 77 |
| `hybrid-interfaces` | Superconductor–Semiconductor Interfaces | 72 |
| `cryo-eda` | Cryogenic Electronic Design Automation (EDA) | 57 |
| `sensors-and-metrology` | Sensors, Metrology & Voltage Standards | 24 |

## Quick Start

### 1. Standalone clone

```bash
git clone git@github.com:single-flux-quantum/.github.git
cd .github
```

### 2. Activating GitHub Pages

GitHub Pages must be enabled in the repository settings:

- **Method A: Deploy from a branch (Fastest, zero workflow overhead)**:
  1. Open [https://github.com/single-flux-quantum/.github/settings/pages](https://github.com/single-flux-quantum/.github/settings/pages).
  2. Under **Build and deployment** → **Source**, select **Deploy from a branch**.
  3. Under **Branch**, select `main` and folder `/docs`.
  4. Click **Save**. The map is live in ~30 seconds.

- **Method B: Deploy using GitHub Actions**:
  1. Under **Build and deployment** → **Source**, select **GitHub Actions**.
  2. The workflow [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) will trigger on push to `main` and publish `docs/`.

### 3. Running locally

Because `docs/index.html` has zero build steps and uses standard ES6 JavaScript:

```bash
# Python 3
python -m http.server 8000 --directory docs

# Open in browser:
# http://localhost:8000
```

### 4. Synchronizing from parent lab

From the parent monorepo [`sfq-lab`](https://github.com/single-flux-quantum/sfq-lab):

```bash
# 1. Regenerate papers.json and profile/README.md from analyzed papers:
python scripts/export_papers_catalog.py

# 2. Review staged changes in share/github:
git status share/github

# 3. Commit and push from share/github:
cd share/github
git commit -am "chore: sync papers catalog"
git push origin main
```

## Datasheet

### Motivation

Superconducting electronics operates in an extreme domain of picosecond gate delays ($>50\text{ GHz}$) and sub-microwatt power consumption, but literature is dispersed across physics, device fabrication, cryogenics, and VLSI EDA venues. This catalog provides a unified, structured taxonomy to make SFQ research discoverable for computer architects, quantum hardware engineers, and circuit designers.

### Composition

The dataset includes:
- Machine-readable records (`docs/papers.json`) containing DOIs, complete author rosters, verified venues, and TL;DR innovations.
- An interactive client-side web application (`docs/index.html`) supporting full-text search, domain filtering, and multi-column sorting.
- An accessible static snapshot table in `profile/README.md` for environments without JavaScript execution.

### Collection and curation process

- **Sources**: Peer-reviewed publications extracted from IEEE Xplore, Crossref, and publisher repositories.
- **Verification**: Cross-referenced with the parent lab's BibTeX index (`docs/tas.bib`) and structured analyses (`papers/*/analysis.md`).
- **Classification**: Tagged into 9 domain taxonomies based on circuit topology, clocking methodology, interface type, and application target.

### Maintenance

The catalog is maintained as an export artifact of [single-flux-quantum/sfq-lab](https://github.com/single-flux-quantum/sfq-lab). Any corrections or additions to papers under `papers/` are propagated via `scripts/export_papers_catalog.py`.

## Known Issues and Limitations

- **PDF hosting**: In compliance with publisher copyrights, this repository does not host full-text PDFs. Every entry links directly to its publisher DOI resolver.
- **Single-page scope**: The catalog is tuned for low-latency in-browser filtering of hundreds of papers; large corpora (>5,000 papers) would require server-side pagination or search indexing.

## License

This documentation, dataset catalog, and organization profile are licensed under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license. See [`LICENSE`](LICENSE).

**Third-Party Terms**: Publisher metadata, paper titles, author attributions, and DOIs remain the property of their respective copyright holders (IEEE, IOP Publishing, etc.).

## Citation

If you use this literature catalog or interactive paper map in your research or tooling, please cite:

```bibtex
@misc{sfqlab2026catalog,
  title        = {Single-Flux-Quantum (SFQ) Research Literature Map and Catalog},
  author       = {{Single-Flux-Quantum Lab Contributors}},
  year         = {2026},
  howpublished = {\url{https://single-flux-quantum.github.io/.github/}},
  note         = {GitHub Organization Profile and Curated Research Map}
}
```

## References

- **Parent Lab Monorepo**: [`sfq-lab`](https://github.com/single-flux-quantum/sfq-lab)
- **Open Problems Roadmap**: [`docs/PROBLEM.md`](https://github.com/single-flux-quantum/sfq-lab/blob/main/docs/PROBLEM.md)
- **Interactive Portal**: [https://single-flux-quantum.github.io/.github/](https://single-flux-quantum.github.io/.github/)

## Contact

- **Organization**: [https://github.com/single-flux-quantum](https://github.com/single-flux-quantum)
- **Issues and Inquiries**: [https://github.com/single-flux-quantum/.github/issues](https://github.com/single-flux-quantum/.github/issues)
- **Monorepo Discussions**: [https://github.com/single-flux-quantum/sfq-lab/issues](https://github.com/single-flux-quantum/sfq-lab/issues)
