# Single-Flux-Quantum (SFQ) Lab

Open **superconducting digital electronics research**, **EDA tools**, a **beginner SFQ learning curriculum**, and a **curated map of SFQ research papers** — accelerating the transition to ultra-high-speed, energy-efficient cryogenic computing.

[![GitHub Pages](https://img.shields.io/badge/Pages-SFQ%20Paper%20Map-181717?logo=github)](https://single-flux-quantum.github.io/.github/)
[![SFQ Learn](https://img.shields.io/badge/Learn-SFQ%20Curriculum-0A7EA4?logo=readthedocs&logoColor=white)](https://single-flux-quantum.github.io/sfq-learn-public/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green?logo=creativecommons&logoColor=white)](https://creativecommons.org/licenses/by/4.0/)
[![Corpus: 1376+ Papers](https://img.shields.io/badge/Corpus-1376%2B%20Papers-blue)](https://github.com/single-flux-quantum/sfq-lab)
[![Org Followers](https://img.shields.io/github/followers/single-flux-quantum?label=followers&logo=github)](https://github.com/single-flux-quantum)

---

## Start Here

- **[SFQ Learning Curriculum](https://single-flux-quantum.github.io/sfq-learn-public/)** — Fundamentals → bridge → concepts → tracks (newcomer-friendly; more wording is intentional).
- **[Interactive SFQ Paper Map](https://single-flux-quantum.github.io/.github/)** — Search, filter by research domain, and sort across 1376+ curated papers with direct publisher links.

---

## Repository Structure & Synchronization

This organization profile repository is synchronized from the monorepo [single-flux-quantum/sfq-lab](https://github.com/single-flux-quantum/sfq-lab):
- `profile/README.md`: This landing page (generated from corpus analysis).
- `docs/index.html`: Interactive Paper Map web app deployed to GitHub Pages.
- `docs/papers.json`: Machine-readable catalog metadata.
- `.github/workflows/deploy-pages.yml`: Automated GitHub Pages deployment pipeline.

Learning curriculum lives in a sibling public repo: [sfq-learn-public](https://github.com/single-flux-quantum/sfq-learn-public) ([site](https://single-flux-quantum.github.io/sfq-learn-public/)).

To refresh the catalog, run `python scripts/export_papers_catalog.py` in `sfq-lab`.

---

## License

This catalog and organization profile documentation are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
Publisher metadata, DOIs, and paper citations remain under the copyright of their respective publishers (IEEE, AIP, APS, Elsevier). This repository does not host copyright-restricted PDFs.
