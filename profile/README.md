# Single-Flux-Quantum (SFQ) Lab

Open **superconducting digital electronics research**, **EDA tools**, a **beginner SFQ learning curriculum**, and a **curated map of SFQ research papers** — accelerating the transition to ultra-high-speed, energy-efficient cryogenic computing.

[![GitHub Pages](https://img.shields.io/badge/Pages-SFQ%20Paper%20Map-181717?logo=github)](https://single-flux-quantum.github.io/.github/)
[![SFQ Learn](https://img.shields.io/badge/Learn-SFQ%20Curriculum-0A7EA4?logo=readthedocs&logoColor=white)](https://single-flux-quantum.github.io/sfq-learn-public/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green?logo=creativecommons&logoColor=white)](https://creativecommons.org/licenses/by/4.0/)
[![Corpus: 1352+ Papers](https://img.shields.io/badge/Corpus-1352%2B%20Papers-blue)](https://github.com/single-flux-quantum/sfq-lab)
[![Org Followers](https://img.shields.io/github/followers/single-flux-quantum?label=followers&logo=github)](https://github.com/single-flux-quantum)

---

## Start Here

- **[SFQ Learning Curriculum](https://single-flux-quantum.github.io/sfq-learn-public/)** — Fundamentals → bridge → concepts → tracks (newcomer-friendly; more wording is intentional).
- **[Interactive SFQ Paper Map](https://single-flux-quantum.github.io/.github/)** — Search, filter by research domain, and sort across 1352+ curated papers with direct publisher links.

---

## Core Research Domains

```
   ┌────────────────────────────────────────────────────────────────────────┐
   │                  Superconducting Electronics Ecosystem                 │
   └───────────────────────────────────┬────────────────────────────────────┘
                                       │
         ┌───────────────────┬─────────┴─────────┬───────────────────┐
         ▼                   ▼                   ▼                   ▼
  [Logic & Cells]      [Cryo-EDA & STA]    [Clock & Power]    [Cryo-CMOS Links]
  RSFQ / ERSFQ / AQFP  qSTA / qGDR Routing Resistor-JTL / Damping 4JL / SQUID Stacks
  Clockless Dynamic    Yield Optimization  Current Recycling  Transimpedance
         │                   │                   │                   │
         └───────────────────┼───────────────────┼───────────────────┘
                             ▼                   ▼
                     [Cryogenic Memory]   [Quantum & Metrology]
                     Hybrid CMOS-RAM      Qubit Control at mK
                     0-π SQUID / CRAM     SNSPD Photon Readout
```

1. **Circuits & Logic Families**: Rapid Single Flux Quantum (RSFQ), Energy-Efficient RSFQ (ERSFQ), Adiabatic Quantum Flux Parametron (AQFP), 4JL, and Clockless Dynamic SFQ gates.
2. **Cryogenic Electronic Design Automation (EDA)**: Static Timing Analysis (`qSTA`, `qSSTA`), global & detailed routing (`qGDR`), inductive crosstalk extraction, and cell-library characterization.
3. **Clocking & Power Distribution Networks**: Resistor-JTL multiclock generators, GALS architectures, AC-biased splitters, passive damping, and current-recycling bias techniques.
4. **Superconductor–Semiconductor Interfaces**: 4JL drivers, SQUID stacks, Suzuki stacks, and high-bandwidth cryogenic CMOS-to-SFQ transceivers.
5. **Cryogenic Memory & Storage**: Josephson-CMOS hybrid memory, 64-kb Cryo-RAM, 0-π SQUID cells, and high-density shift registers.
6. **Microprocessors & Compute Architectures**: Gate-level pipelined SFQ ALUs, 50-GFLOPS floating-point processors, 64-GHz datapaths, and cryogenic neuromorphic accelerators.
7. **Quantum Computing Interfacing & Readout**: Millikelvin digital qubit controllers, proximal cryo-coprocessors, and SNSPD photon-counting interfaces.
8. **Sensors, Metrology & Mixed-Signal**: Quantum voltage synthesizers, time-to-digital converters (TDCs), and balanced Josephson comparators.

---

## Repository Structure & Synchronization

This organization profile repository is synchronized from the monorepo [single-flux-quantum/sfq-lab](https://github.com/single-flux-quantum/sfq-lab):
- `profile/README.md`: This landing page (generated from corpus analysis).
- `docs/index.html`: Interactive Paper Map web app deployed to GitHub Pages.
- `docs/papers.json`: Machine-readable catalog metadata.
- `.github/workflows/deploy-pages.yml`: Automated GitHub Pages deployment pipeline.

---

## License

This catalog and organization profile documentation are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
Publisher metadata, DOIs, and paper citations remain under the copyright of their respective publishers (IEEE, AIP, APS, Elsevier). This repository does not host copyright-restricted PDFs.
