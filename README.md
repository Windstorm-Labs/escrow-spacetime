# Paper 14: Escrow Spacetime — Reproduction Code

**Spacetime as Escrow Bookkeeping: A Conceptual Translation of General Relativity into the Static Entropy Escrow Vocabulary**

[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20126091-blue)](https://doi.org/10.5281/zenodo.20126091)
[![License: MIT](https://img.shields.io/badge/Code-MIT-green)](https://opensource.org/licenses/MIT)
[![License: CC BY 4.0](https://img.shields.io/badge/Data-CC_BY_4.0-lightgrey)](https://creativecommons.org/licenses/by/4.0/)
[![Track: Entropic Bounds](https://img.shields.io/badge/Track-2_·_Entropic_Bounds-8b5cf6)](https://windstorminstitute.org/#track2)

> **Track 2 of the Windstorm Institute — Entropic Bounds in Analog Systems.** Companion code to the paper's *§IV.C Modular Hamiltonian* section and to [Paper 13 — Lattice QFT Test](https://github.com/Windstorm-Institute/lattice-qft-test).

---

## Published paper

- **[Windstorm-Institute/escrow-spacetime](https://github.com/Windstorm-Institute/escrow-spacetime)** — paper PDF, article HTML, submission scaffolds
- **Website article:** [windstorminstitute.org/articles/escrow-spacetime.html](https://windstorminstitute.org/articles/escrow-spacetime.html)
- **Zenodo:** [10.5281/zenodo.20126091](https://doi.org/10.5281/zenodo.20126091)

## Contents

This repository contains the **canonical reference implementations** of the modular-Hamiltonian lattice computations referenced in §IV.C of the paper. They are the same computations published in [Paper 13](https://github.com/Windstorm-Institute/lattice-qft-test), reproduced here as Paper 14's supplementary code so that anyone reading the GR-to-escrow translation can independently verify the 1/30 prefactor result and the 3+1D peaked-then-decay structure.

```
experiments/
├── lattice_1d_modular.py    Canonical 1+1D lattice; recovers the BW linear
│                            asymptote with prefactor ≈ 1/30 in the small-d₁
│                            window. Reproduces §IV.C result 1 of the paper.
└── lattice_3d_modular.py    Canonical 3+1D lattice; finds peaked-then-decaying
                             functional form within the resolvable d₁ range.
                             Reproduces §IV.C result 2 of the paper.
```

## Quick start

```bash
git clone https://github.com/Windstorm-Labs/escrow-spacetime
cd escrow-spacetime
python -m venv .venv && source .venv/bin/activate
pip install numpy scipy matplotlib

# 1+1D — reproduces the 1/30 prefactor in the small-d₁ window
python experiments/lattice_1d_modular.py

# 3+1D — reproduces the peaked-then-decay functional form
python experiments/lattice_3d_modular.py
```

Both scripts are self-contained: they construct the free scalar Hamiltonian on a 1+1D or 3+1D lattice, compute the bipartition entanglement entropy via correlator-matrix eigenvalue methods, and compare against the Bisognano–Wichmann linear asymptote.

## Hardware

- **Hardware:** Current-generation Nvidia GPU (32 GB VRAM, CUDA), Intel Core Ultra 9 285K, 256 GB RAM
- **Note:** GPU is *optional* for these scripts; CPU is sufficient. GPU acceleration is used in the larger lattice-survey sweeps documented in Paper 13's `Windstorm-Labs/lattice-qft-test` repo.

## Why this code lives in two repos

Paper 13 (the standalone lattice paper) and Paper 14 (the GR-translation paper) both reference these computations. Rather than have either repo depend on the other for reproduction, both repos ship the canonical scripts directly. The scripts are byte-identical across the two repos and produce the same outputs.

## In the Series

### Track 2 — Entropic Bounds in Analog Systems · 7 papers (Papers 10–16)

| # | Paper | DOI | Labs mirror |
|---|---|---|---|
| 10 | [Phonon Extraction Bound (BEC Analog Gravity)](https://github.com/Windstorm-Institute/phonon-extraction-bound) | [10.5281/zenodo.20014391](https://doi.org/10.5281/zenodo.20014391) | [Labs](https://github.com/Windstorm-Labs/phonon-extraction-bound) |
| 11 | [Gravitational Entropy Escrow](https://github.com/Windstorm-Institute/gravitational-entropy-escrow) *(framework paper)* | [10.5281/zenodo.20032023](https://doi.org/10.5281/zenodo.20032023) | [Labs](https://github.com/Windstorm-Labs/gravitational-entropy-escrow) |
| 12 | [C8 Clarification Note](https://github.com/Windstorm-Institute/c8-clarification-note) *(companion to Paper 11)* | [10.5281/zenodo.20041992](https://doi.org/10.5281/zenodo.20041992) | [Labs](https://github.com/Windstorm-Labs/c8-clarification-note) |
| 13 | [Lattice QFT Test of the Static Escrow Postulate](https://github.com/Windstorm-Institute/lattice-qft-test) *(supplement to Paper 11)* | [10.5281/zenodo.20057538](https://doi.org/10.5281/zenodo.20057538) | [Labs](https://github.com/Windstorm-Labs/lattice-qft-test) |
| 14 | [Spacetime as Escrow Bookkeeping](https://github.com/Windstorm-Institute/escrow-spacetime) *(this paper — translation of standard GR results)* | [10.5281/zenodo.20126091](https://doi.org/10.5281/zenodo.20126091) | [Labs](https://github.com/Windstorm-Labs/escrow-spacetime) |
| 15 | [The 𝒩<sub>esc</sub> Recipe](https://github.com/Windstorm-Institute/nesc-recipe) | Formalizes the 𝒩<sub>esc</sub> notation from Paper 14 as a two-argument function 𝒩<sub>esc</sub>(*E*, *L*) ≡ 2π*EL*/(ℏ*c*) plus a regime-specific recipe extracting (*E*, *L*) from \|*U*\|/*T*. Observes that the same one-function recipe, applied across three qualitatively distinct settings — test mass in Schwarzschild, Bekenstein–Hawking via Smarr, and Casini's QFT bound in a Rindler wedge — evaluates to the Bekenstein-bound saturation form in each. Lattice verification at *N* ∈ [200, 1200]: boost-generator BW identification at 0.087% mean accuracy; Casini–BW inequality verified within max 5.4% saturation. Theorem 1 conditional on BW, Casini, and moment-positivity. Five pre-registered retractions. Continuation of Paper 14. | [10.5281/zenodo.20145106](https://doi.org/10.5281/zenodo.20145106) | [Labs](https://github.com/Windstorm-Labs/nesc-recipe) |
| 16 | [The Compton Corollary](https://github.com/Windstorm-Institute/compton-corollary) | [10.5281/zenodo.20163451](https://doi.org/10.5281/zenodo.20163451) | [Labs](https://github.com/Windstorm-Labs/compton-corollary) |
---

## License

Code: MIT · Data/figures: CC BY 4.0 · Paper text: CC BY 4.0 (see [Windstorm-Institute/escrow-spacetime](https://github.com/Windstorm-Institute/escrow-spacetime) for the paper)
