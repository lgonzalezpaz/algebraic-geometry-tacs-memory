# Algebraic Bifurcation Dynamics of Fronto-Parietal Theta Oscillations Account for Phase-Specific Modulation of Human Episodic Sequence Memory

**Authors:** Lenin González-Paz*, Arlene Cardozo-Urdaneta, Carla Lossada, Ariana Delgado, Máximo Quintero, Ysaías J. Alvarado*  
**Correspondence:** `lgonzalezpaz@gmail.com` (L.G.-P.); `alvaradoysaias@gmail.com` (Y.J.A.)  
**License:** MIT ([`LICENSE`](LICENSE)) · **Version:** `1.0.0`

---

## Overview

This repository contains the complete theoretical, computational, empirical-reanalysis, and manuscript-generation package accompanying our paper modeling fronto-parietal–hippocampal theta transcranial alternating current stimulation (tACS) via Weierstrass–Kuramoto algebraic varieties, Bernstein–Kushnirenko–Khovanskii (BKK) Newton polytopes, codimension-2 cusp discriminant singularities, and 68-region human structural connectome (`dk68`) stochastic simulations validated against open-access human behavioral and resting-EEG datasets (OSF `4xwkj`; `N = 42`, `126` sessions, `8,032` temporal-order judgment trials).

---

## Repository Structure

```text
algebraic-geometry-tacs-memory/
├── README.md                               # Reproduction & repository documentation
├── FILE_LIST_GitHub_Zenodo.txt             # Complete manifest of archive files
├── LICENSE                                 # MIT License
├── CITATION.cff                            # Citation File Format metadata
├── .zenodo.json                            # Zenodo archive metadata
├── requirements.txt                        # Python dependencies
├── environment.yml                         # Conda environment specification
├── data/
│   ├── dk68/                               # 68-region human Desikan–Killiany structural connectome (weights, tract lengths, regions, centres, orientations)
│   └── osf/                                # Cached OSF 4xwkj behavioral workbook, 8,032-trial RAW_TOJ.zip archive, and original MATLAB/R analysis scripts
├── src/
│   ├── empirical_analysis.py               # Re-analysis of OSF 4xwkj human dataset (N=42, 126 sessions, 8,032 trials, LMM/ANCOVA) & dk68 extraction
│   ├── algebraic_kuramoto_memory.py        # Weierstrass–Kuramoto solver, BKK mixed volume, homotopy continuation, dk68 debiased wPLI MC, AIC/LOSO-CV, ±25% sweep
│   ├── independent_math_audit.py           # Independent symbolic/numerical mathematical audit script (atol/rtol = 1e-12)
│   ├── generate_figures.py                 # Publication figure generator (Figures 1–6 and S1–S2 at 600 DPI PNG + PDF)
│   ├── omml_equations.py                   # Native Word OMML XML equation generator for Eqs. (1)–(18) and (S1)–(S6)
│   ├── build_manuscript_docx.py            # Automated DOCX compiler
│   └── verify_manuscript.py                # Automated structural & sequential order verifier
├── figures/
│   ├── Figure1.png / Figure1.pdf           # Fronto-parietal connectome geometry & Weierstrass–Kuramoto cusp discriminant variety
│   ├── Figure2.png / Figure2.pdf           # Newton polytope capacity (MV = 8, MV = 48), temporal scaling, & chiral potential landscapes
│   ├── Figure3.png / Figure3.pdf           # Resolution of the debiased wPLI connectivity paradox on the algebraic variety & dk68 connectome
│   ├── Figure4.png / Figure4.pdf           # Empirical validation of TOJ, free recall dissociation, & competing model ΔAIC comparison (N=42)
│   ├── Figure5.png / Figure5.pdf           # Hessian Morse curvature separation predicts empirical metacognitive collapse (8,032 trials)
│   ├── Figure6.png / Figure6.pdf           # Polynomial homotopy continuation, individualized inverse control law, & responder stratification
│   └── FigureS1–S2 (.png / .pdf)           # ±25% biophysical sensitivity sweeps, HCA/LCA accuracy, resting ITF stability, & RT asymmetry
└── results/
    ├── dk68_connectome_summary.csv         # Extracted left fronto-parietal and hippocampal structural connectome parameters
    ├── empirical_*.csv                     # Replicated LMM/ANCOVA omnibus tests, contrasts, cell means, session & trial summaries
    ├── homotopy_continuation_path.csv      # 61-step predictor–corrector path with polynomial/trigonometric residuals & Jacobian determinants
    ├── model_6condition_predictions.csv    # Algebraic & dk68 connectome predictions across all 6 stimulation cells
    ├── model_comparison_aic_cv.csv         # OLS / AIC / BIC / 5,000-permutation / LOSO-CV comparison against null models
    ├── participant_model_validation.csv    # Session-level individualized algebraic predictions matched to human outcomes
    ├── sensitivity_sweep_25pct.csv         # ±25% single-parameter perturbation summary (12/12 sign preservation)
    ├── verified_references.json            # CrossRef/PubMed bibliographic verification & SHA-256 dataset checksums
    └── math_audit_report.json              # Independent mathematical verification log
```

---

## Key Quantitative Benchmarks (Reproduced End-to-End)

1. **Human Structural Connectome (`dk68`):** Weighted left fronto-parietal tract length $L_{\mathrm{FP}} = 93.64\ \mathrm{mm}$, conduction delay $\tau_{\mathrm{FP}} = 13.38\ \mathrm{ms}$ (at $v_{\mathrm{cond}} = 7.0\ \mathrm{m/s}$).
2. **Exact BKK Mixed Volumes & Homotopy Continuation:** Total 2-node isolated algebraic root count $\mathrm{MV} = 8.0$; 3-node fronto-parietal–hippocampal triad $\mathrm{MV} = 48.0$. Across a 61-step homotopy continuation path in the pole-free gauge $(\varphi_{\mathrm{LF}} = -\pi/2,\ \varphi_{\mathrm{LP}} = +\pi/2 - \alpha_{\mathrm{FP}})$, maximum polynomial residual $= 3.90 \times 10^{-15}$, maximum trigonometric residual $= 1.86 \times 10^{-15}$, and minimum Jacobian determinant $= 453.60$.
3. **68-Region Connectome Debiased wPLI Simulations (`dk68`):** Under slow-theta anti-phase stimulation ($\mathrm{ITF}-1\ \mathrm{Hz},\ \Delta\phi = \pi$), $\Delta\mathrm{wPLI}_{\mathrm{sim}} = +0.4994$ vs. $-0.1367$ under fast-theta anti-phase stimulation ($\mathrm{ITF}+1\ \mathrm{Hz},\ \Delta\phi = \pi$).
4. **Empirical Open-Access Validation (`OSF 4xwkj`, $N = 42$, $126$ sessions, $8,032$ trials):**
   - **Temporal-order accuracy (`dAcc`, $n = 126$):** Algebraic discriminant model predicts observed accuracy changes ($r = +0.2234,\ P = 0.0119,\ P_{\mathrm{perm}} = 0.0140$, $\mathrm{LOSO}\ R^2 = +0.0103$), outperforming both Zero-Lag Synchrony ($\Delta\mathrm{AIC} = 6.39$) and Frequency-Detuning-Only ($\Delta\mathrm{AIC} = 3.49$) null models.
   - **Metacognitive discrimination (`Sep_post`, $n = 120$):** Algebraic Morse curvature index $M_{\mathrm{sep}}$ predicts post-stimulation metacognitive separation ($r = +0.2750,\ P = 0.0024,\ P_{\mathrm{perm}} = 0.0012$, $\mathrm{LOSO}\ R^2 = +0.0453$), outperforming both Null 1 ($\Delta\mathrm{AIC} = 7.40$) and Null 2 ($\Delta\mathrm{AIC} = 3.57$).
5. **Parameter Robustness (`±25%` across 6 biophysical parameters):** $12/12$ perturbation regimes preserve every qualitative predicted ordering across `dk68` wPLI, $M_{\mathrm{sep}}$, and $\Delta\mathrm{Acc}_{\mathrm{pred}}$.

---

## Reproducing the Complete Pipeline

Install dependencies via `pip install -r requirements.txt` (or `conda env create -f environment.yml`) and run from the repository root:

```bash
python src/empirical_analysis.py
python src/algebraic_kuramoto_memory.py
python src/independent_math_audit.py
python src/generate_figures.py
```

### Empirical Data & Attribution Note

Raw behavioral and participant spectral summary data (`SubjectInfo_and_BehavioralData.xlsx`, `RAW_TOJ.zip`, original MATLAB/R analysis scripts) originate from the open-access OSF repository [`4xwkj`](https://osf.io/4xwkj/) (Aktürk & Sack, *Cortex*, 2026). As documented transparently in the Discussion, resting-state debiased wPLI comparisons rely on simulated `dk68` cortical dynamics using the exact FieldTrip debiased wPLI estimator from `rest_connectivity_ITF_pipeline.m` because individual raw BrainVision `.eeg` files (multi-gigabyte archives) were not downloaded locally.
