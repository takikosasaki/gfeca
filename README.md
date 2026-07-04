# Supplementary Data — Generalized FDNF Fuzzification of Elementary Cellular Automata

Numerical data and Wolfram Language / Mathematica code for the quantitative figures,
appendix checks, and reproducibility information of the manuscript:

> **Generalized FDNF fuzzification of elementary cellular automata and its nonlinear pattern dynamics**
> (revised manuscript `elsarticle-tn_v2.tex`)

<!-- After you publish to Zenodo, replace the line below with the real DOI badge. -->
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)

---

## Overview

This repository accompanies the revised manuscript. In the revision, the convex-mixing
experiment was moved out of the main contribution list and is treated as an illustrative
appendix extension beyond the single-rule GFDNF setting. As a result, the Rule 210 figures
formerly numbered **Figs. 17–20** are now the main-text **Figs. 14–17**, and file names have
been updated accordingly (see the table below).

| Old file name | New file name |
| --- | --- |
| `rule210_fig17_20_threeclass_revised_v2.wl` | `rule210_fig14_17_threeclass_revised_v3.wl` |
| `fig19_threeclass_uncertainty_fit_summary.csv` | `fig16_threeclass_uncertainty_fit_summary.csv` |
| `fig19_threeclass_uncertainty_pooled.csv` | `fig16_threeclass_uncertainty_pooled.csv` |
| `fig20_threeclass_main_values.csv` | `fig17_threeclass_main_values.csv` |
| `fig20_threeclass_entropy_summary.csv` | `fig17_threeclass_entropy_summary.csv` |

---

## Software and environment

All calculations were performed with **Wolfram Mathematica / Wolfram Language**.
The per-experiment version is recorded in the `*_metadata.json` files:

- **Wolfram Mathematica 14.0.0 for Microsoft Windows (64-bit)**

Random seeds are recorded in the metadata files. Unless otherwise stated,
**periodic boundary conditions** were used and initial conditions are drawn
i.i.d. from `Uniform[0, 1]`.

**File types in this repository**

| Extension | Description |
| --- | --- |
| `.nb` | Mathematica notebooks (interactive; open and evaluate) |
| `.wl` | Wolfram Language scripts (batch; load with `Get[...]`) |
| `.csv` | Numerical data (per-initial-condition raw values and ensemble summaries) |
| `.json` | Metadata: rules, sizes, times, parameter grids, seeds, Wolfram version |
| `.pdf` | Supplementary tables (`Supplementary_Material_GFDNF_breakable_tables.pdf`) |

---

## Repository structure

```
.
├── README.md
├── REVISION_LOG.md
│
├── fig08_RB.nb                              # Fig. 8: q_a deformation
├── fig08_metadata.json
├── fig08_RB_summary.csv
├── fig08_RB_raw_by_initial_condition.csv
│
├── fig10_gap_RB.nb                          # Fig. 10: gap function r_a
├── fig10_metadata.json
├── fig10_gap_initial_conditions_metadata.json
├── fig10_gap_metric_initial_conditions.csv
├── fig10_gap_pattern_initial_condition.csv
├── fig10_gap_RB_summary.csv
├── fig10_gap_RB_raw_by_initial_condition.csv
├── fig10_gap_RB_sd_summary.csv
│
├── moment_order_robustness_support_exponent_v2.wl   # Support-exponent robustness
├── support_moment_order_metadata.json
├── support_moment_order_summary.csv
├── support_moment_order_raw.csv
│
├── rule210_fig14_17_threeclass_revised_v3.wl        # Rule 210: Figs. 14–17
├── rule210_make_submission_figures.wl
├── rule210_interval_verification.wl
├── rule210_metadata.json
├── rule210_slice_grid_class_counts.csv
├── rule210_class_fractions.csv
├── rule210_uncertainty_summary.csv
├── rule210_uncertainty_by_seed.csv
├── rule210_entropy_summary.csv
├── rule210_entropy_resolution_sweep.csv
├── fig16_threeclass_uncertainty_fit_summary.csv
├── fig16_threeclass_uncertainty_pooled.csv
├── fig17_threeclass_main_values.csv
├── fig17_threeclass_entropy_summary.csv
│
└── Supplementary_Material_GFDNF_breakable_tables.pdf
```

---

## Contents by experiment

### Fig. 8 — Contrast and fuzziness for the `q_a` deformation

**Files:** `fig08_RB.nb`, `fig08_metadata.json`, `fig08_RB_summary.csv`,
`fig08_RB_raw_by_initial_condition.csv`

Reproduces the contrast and fuzziness curves for the `q_a`-deformation experiments.

| Setting | Value |
| --- | --- |
| Rules | 30, 90, 184 |
| System size `N` | 100 |
| Final time `T` | 100 |
| Parameter grid | `a = 0, 0.01, …, 1.00` |
| Initial conditions | 50, i.i.d. `Uniform[0,1]` |
| Random seed | 20260316 |
| Boundary condition | periodic |
| Fuzzification | `g = id`, `u = v = w = q_a` |
| Metrics | contrast `R_k(a;T)`, fuzziness `B_k(a;T)` |

- `fig08_RB_summary.csv` — ensemble means and standard deviations per rule and parameter value.
- `fig08_RB_raw_by_initial_condition.csv` — contrast/fuzziness for each individual initial condition.

### Fig. 10 — Contrast and fuzziness for the gap function `r_a`

**Files:** `fig10_gap_RB.nb`, `fig10_metadata.json`,
`fig10_gap_initial_conditions_metadata.json`, `fig10_gap_metric_initial_conditions.csv`,
`fig10_gap_pattern_initial_condition.csv`, `fig10_gap_RB_summary.csv`,
`fig10_gap_RB_raw_by_initial_condition.csv`, `fig10_gap_RB_sd_summary.csv`

Reproduces the contrast and fuzziness curves for the gap-function experiments. The
initial-condition CSVs record the random conditions used for the ensemble metrics and
for the representative pattern panels.

| Setting | Value |
| --- | --- |
| Rules | 102, 184 |
| System size `N` | 50 |
| Final time `T` | 200 |
| Metric window | `100 ≤ t ≤ 200`, `0 ≤ j < N` |
| Parameter grid | `a = 1.00, 1.01, …, 2.00` |
| Initial conditions | 30, i.i.d. `Uniform[0,1]` |
| Random seed | 20260316 |
| Boundary condition | periodic |
| Fuzzification | `g = u = v = w = r_a` |
| Metrics | contrast `R_k(a)`, fuzziness `B_k(a)` |

- `fig10_gap_RB_summary.csv` — ensemble means and standard deviations.
- `fig10_gap_RB_raw_by_initial_condition.csv` — per-initial-condition values.
- `fig10_gap_RB_sd_summary.csv` — standard-deviation summary.
- `fig10_gap_metric_initial_conditions.csv` — the 30 initial conditions used for the metrics.
- `fig10_gap_pattern_initial_condition.csv` — representative initial condition for the pattern panels.

### Moment-order robustness of the finite-resolution support exponent

**Files:** `moment_order_robustness_support_exponent_v2.wl`,
`support_moment_order_metadata.json`, `support_moment_order_summary.csv`,
`support_moment_order_raw.csv`

Robustness check for the finite-resolution support exponent at moment orders
`p = 8, 16, 32, 64`, together with the amplitude normalization `S_2 / M`. The `q_a`
and gap-function cases correspond to the main-text support-exponent calculations; the
convex-mixing case is retained only as an appendix-level illustrative extension.

| Setting | Value |
| --- | --- |
| Moment orders | `p = 8, 16, 32, 64` |
| Rounding threshold | `1e-12` |
| `q_a` experiments | rules 30, 90, 184; `N = 100`; `T = 100`; window start 50; 50 samples |
| Gap experiments | rules 102, 184; `N = 50`; `T = 200`; window start 100; 30 samples |
| Appendix convex mixing | rules 184, 90; `N = 50`; `T = 500`; window start 450; single localized IC |

- `support_moment_order_summary.csv` — mean support exponents, standard deviations, mean `S_2/M`.
- `support_moment_order_raw.csv` — raw values per experiment, parameter value, sample, and moment order.

### Rule 210 — Three-class finite-resolution classification (Figs. 14–17)

**Code:** `rule210_fig14_17_threeclass_revised_v3.wl`, `rule210_make_submission_figures.wl`,
`rule210_interval_verification.wl`

- `rule210_fig14_17_threeclass_revised_v3.wl` — three-class slice classification, uncertainty
  calculation, and class-entropy calculation for revised Figs. 14–17.
- `rule210_make_submission_figures.wl` — redraws publication figures from computed CSV/WXF output.
- `rule210_interval_verification.wl` — verifies the period-six orbit and local stability
  information used in Appendix A.

**Data:** `rule210_metadata.json`, `rule210_slice_grid_class_counts.csv`,
`rule210_class_fractions.csv`, `rule210_uncertainty_summary.csv`,
`rule210_uncertainty_by_seed.csv`, `rule210_entropy_summary.csv`,
`rule210_entropy_resolution_sweep.csv`, `fig16_threeclass_uncertainty_fit_summary.csv`,
`fig16_threeclass_uncertainty_pooled.csv`, `fig17_threeclass_main_values.csv`,
`fig17_threeclass_entropy_summary.csv`

| Setting | Value |
| --- | --- |
| Slices | `z = 1/2` and `z = 0.3` |
| Cycle convergence tolerance | `δ = 1e-6` |
| Maximum iteration time | `n_max = 20000` |
| Consecutive period-six checks | 20 |
| Line-set tolerance | `1e-10` |
| Slice image grid | `800 × 800` |
| Uncertainty pairs per ε per seed | 10000 |
| Uncertainty seeds | 20260316–20260320 |
| Fit ε range | `1e-4` to `1e-1` |
| Entropy boxes | 40, 80, 160 |
| Samples per box | 10, 20, 50 |
| Main entropy setting | `80 × 80` boxes, 20 samples per box |

> **Note on Fig. 14 / Fig. 15 slice images.** The WXF label arrays used to redraw the
> slice images (`fig14_15_labels_z0p5.wxf`, `fig14_15_labels_z0p3.wxf`) are **not** included.
> Regenerate them by running `rule210_fig14_17_threeclass_revised_v3.wl`; this takes
> substantially longer than redrawing figures from the existing CSV files.

---

## Reproducing the results

**Fig. 8** — open and evaluate `fig08_RB.nb`, then compare with `fig08_RB_summary.csv`
and `fig08_RB_raw_by_initial_condition.csv`.

**Fig. 10** — open and evaluate `fig10_gap_RB.nb`, then compare with
`fig10_gap_RB_summary.csv`, `fig10_gap_RB_raw_by_initial_condition.csv`, and
`fig10_gap_RB_sd_summary.csv`.

**Support-exponent robustness**

```wolfram
quickTest = False;
Get["moment_order_robustness_support_exponent_v2.wl"]
```

**Rule 210 revised Fig. 14–17 data**

```wolfram
quickTest = False;
Get["rule210_fig14_17_threeclass_revised_v3.wl"]
```

Then redraw the submission figures from the resulting directory:

```wolfram
resultDir = "<path to rule210 output directory>";
Get["rule210_make_submission_figures.wl"]
```

**Rule 210 interval verification**

```wolfram
Get["rule210_interval_verification.wl"]
```

---

## Random seeds and initial conditions

The random seeds and protocol metadata are included, so all initial conditions can be
regenerated by the notebooks and scripts. Providing the initial-condition matrices
directly as CSV is also useful for exact independent reproduction across environments;
the following optional files are **not** required to reproduce the summaries included here:

```
fig08_initial_conditions.csv
qa_initial_conditions.csv
gap_initial_conditions.csv
fig14_15_labels_z0p5.wxf
fig14_15_labels_z0p3.wxf
rule210_interval_verification_output.txt
rule210_interval_verification_metadata.json
```

---

## How to cite

If you use this data or code, please cite both the manuscript and the archived dataset.

<!-- Fill in once the paper and the Zenodo record are finalized. -->

**Dataset (Zenodo):**

```bibtex
@dataset{gfdnf_supplementary_2026,
  author    = {<Author list>},
  title     = {Supplementary data for "Generalized FDNF fuzzification of
               elementary cellular automata and its nonlinear pattern dynamics"},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.XXXXXXX},
  url       = {https://doi.org/10.5281/zenodo.XXXXXXX}
}
```

**Manuscript:** see the citation details in the published paper.

---

## License

<!-- Choose a license before publishing. Common choices:
     - Code (.wl / .nb): MIT or BSD-3-Clause
     - Data (.csv / .json): CC-BY-4.0 or CC0-1.0
     Add the corresponding LICENSE file(s) to the repository. -->

License to be specified. See the `LICENSE` file once added.

---

## Contact

For questions about the numerical data or scripts, please contact the corresponding
author listed in the main manuscript.
