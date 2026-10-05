# Organization Profile Repository (`.github`)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green?logo=creativecommons&logoColor=white)](https://creativecommons.org/licenses/by/4.0/)
[![GitHub Pages](https://img.shields.io/badge/Pages-SFQ%20Paper%20Map-181717?logo=github)](https://single-flux-quantum.github.io/.github/)

Special GitHub organization repository for **[single-flux-quantum](https://github.com/single-flux-quantum)**:
1. The **`profile/README.md`** file automatically renders as the public organization landing page at `https://github.com/single-flux-quantum`.
2. The **`docs/`** directory is automatically deployed to **GitHub Pages** via GitHub Actions, providing an interactive, client-side searchable and sortable **SFQ Paper Map** (156+ analyzed papers).

---

## Live Links

- **Organization Homepage**: [https://github.com/single-flux-quantum](https://github.com/single-flux-quantum)
- **Interactive SFQ Paper Map**: [https://single-flux-quantum.github.io/.github/](https://single-flux-quantum.github.io/.github/)
- **Parent Lab Monorepo**: [single-flux-quantum/sfq-lab](https://github.com/single-flux-quantum/sfq-lab)

---

## Repository Architecture

| Path | Purpose |
| :--- | :--- |
| [`profile/README.md`](profile/README.md) | Organization landing page (curated intro, taxonomy, static paper table) |
| [`docs/index.html`](docs/index.html) | Interactive Paper Map web application (search, domain filter, column sort) |
| [`docs/papers.json`](docs/papers.json) | Structured catalog dataset of all analyzed papers |
| [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) | Automated GitHub Actions workflow deploying `docs/` to GitHub Pages |
| [`LICENSE`](LICENSE) | Creative Commons Attribution 4.0 International (CC BY 4.0) |

> [!NOTE]
> Do **not** hand-edit `profile/README.md` or `docs/papers.json` directly. They are generated and kept in sync from `sfq-lab` using `scripts/export_papers_catalog.py`.

---

## Quick Start & Deployment

### 1. Initial Setup in GitHub Organization
1. Create a new repository named `.github` in your GitHub organization (e.g., `single-flux-quantum/.github`).
2. Clone or push this `share/github` directory to the `main` branch of that repo:
   ```bash
   cd share/github
   git init
   git remote add origin git@github.com:single-flux-quantum/.github.git
   git add .
   git commit -m "feat: initial org profile and interactive paper map"
   git branch -M main
   git push -u origin main
   ```
3. Enable GitHub Pages:
   - Navigate to **Settings** → **Pages** in the `.github` repository.
   - Under **Build and deployment** → **Source**, select **GitHub Actions**.
   - The workflow `deploy-pages.yml` will automatically trigger and deploy the site to `https://<org>.github.io/.github/`.

### 2. Synchronizing Updates from `sfq-lab`
Whenever new papers are added or analyzed in the parent lab `sfq-lab`:
```bash
# In sfq-lab root:
python scripts/export_papers_catalog.py

# Review changes inside share/github:
git status share/github

# Commit & push to your .github org repo
```

---

## Features of the Interactive Paper Map

- **Instant Full-Text Search**: Search by paper title, author, venue, keyword, or innovation summary.
- **Categorical Filtering**: Filter by core SFQ domains:
  - *Circuits & Logic* (RSFQ, ERSFQ, AQFP, 4JL, clockless gates)
  - *Cryo-EDA & Timing* (qSTA, qSSTA, qGDR, InductEx, routing)
  - *Clocking & Power* (multiclock generators, splitters, current recycling)
  - *Hybrid CMOS Interfaces* (SQUID stacks, 4JL transceivers)
  - *Cryogenic Memory* (Cryo-RAM, Josephson-CMOS hybrid memory)
  - *Compute & Processors* (ALUs, floating-point units, microprocessors)
  - *Quantum & Detectors* (qubit control at mK, SNSPD readouts)
  - *Sensors & Metrology* (voltage standards, waveform synthesizers)
- **Interactive Multi-Column Sorting**: Sort ascending/descending by Paper Title, Authors, Year, or Venue.
- **Direct Publisher Links**: One-click navigation to DOI publisher links.
- **Zero-Dependency Architecture**: Pure static HTML/CSS/JS with zero build steps or heavy node dependencies, loading in milliseconds.

---

## License

Content and catalog documentation are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
Publisher metadata, DOIs, and paper citations remain under the copyright of their respective publishers (IEEE, AIP, APS, Elsevier). This repository does not host copyright-restricted PDFs.
