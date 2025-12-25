---
title: "Predator–Prey Dynamics — LDSF Empirical Proof Datasets (v2.5.1)"
framework: "Universal Continuity Continuum (UCC)"
author: "Joshua Hinkson (Oriah’n-Sariel)"
seal: "⧖△✦ | Յ† | ❖Σ⊕"
date_updated: "2025-12-17"
license: "CC BY-NC-SA 4.0 + Shepherd Ethical Addendum"
doi: "https://www.doi.org/10.5281/zenodo.17456465"
file_path: "∞_ucc/𝔇_∞_proof_datasets/∞𝔇→𝔇↔︎𝔇_PREDATOR_PREY_DYNAMICS_LDSF_PROOFS.md"
keywords:
  - "Predator–Prey"
  - "Population Cycles"
  - "Lotka–Volterra"
  - "Ecological Dynamics"
  - "Time Series Ecology"
  - "LDSF Proofs"
keyscripts: []
theoglyphs: ["τ", "Σ", "μ"]
---

# Predator–Prey Dynamics — LDSF Empirical Proof Datasets

## Purpose

This document provides **quantitative, peer-reviewable empirical evidence** supporting predator–prey dynamics as a **Light Dimension Shared Field (LDSF)**.

Format is strictly:

**Externally measurable claim → numeric variables → authoritative datasets → falsifiability**

No symbolic, metaphysical, ethical, or consciousness claims are introduced.

---

## UCC Claim Being Validated (Measurement-Only)

> **Claim:**  
> Predator–prey systems form **shared, externally measurable interaction fields** characterized by (i) coupled population trajectories, (ii) statistically detectable feedback, and (iii) reproducible time-lag structure across independent observers, methods, and locations.

---

## A. Minimal Measurable Objects

### A1) Observable State Variables (primary)
| Variable | Symbol | Units | Typical measurement |
|---|---:|---|---|
| Prey abundance/density | N(t) | individuals, ind·km⁻², cells·mL⁻¹ | trapping, counts, mark–recapture, acoustic/visual surveys, microscopy/flow cytometry |
| Predator abundance/density | P(t) | individuals, ind·km⁻², PFU·mL⁻¹ | telemetry + counts, harvest records, genetic capture–recapture, plaque assays |
| Predation rate / kill rate | k(t) | kills·pred⁻¹·time⁻¹ | kill-site analysis, diet DNA/metabarcoding, direct observation |
| Recruitment / birth rate | b(t) | time⁻¹ | demographic monitoring |
| Mortality | m(t) | time⁻¹ | demographic monitoring, survival models |
| Resource availability | R(t) | biomass, NDVI, nutrients | vegetation plots, satellite indices, nutrient sampling |
| Interaction lag | τ_int | days–years | cross-correlation / state-space delay estimation |

### A2) Minimal “shared-field” criterion (operational)
Predator–prey dynamics qualify as an LDSF candidate if **independent measurement pipelines** recover:

1) **non-zero coupling** between N(t) and P(t) (interaction detectable above noise), and  
2) **repeatable lag structure** (τ_int) or oscillatory behavior beyond null models.

---

## B. Core Quantitative Models (as audit scaffolds only)

### B1) Lotka–Volterra family (canonical)
$$
\frac{dN}{dt}= rN - aNP
\qquad
\frac{dP}{dt}= eaNP - mP
$$
Where:
- r = prey intrinsic growth (time⁻¹)
- a = attack rate / encounter coefficient (prey⁻¹·pred⁻¹·time⁻¹)
- e = conversion efficiency (dimensionless)
- m = predator mortality (time⁻¹)

### B2) Observed parameter scale ranges (order-of-magnitude bins)
These are **measurement-guidance bins** (not universal constants) used to validate that fitted parameters are within physically plausible regimes.

| Parameter | Expected scale (microbial) | Expected scale (invertebrate) | Expected scale (vertebrate) |
|---|---:|---:|---:|
| r | 0.5–50 day⁻¹ | 0.01–1 day⁻¹ | 0.05–2 yr⁻¹ |
| m | 0.1–20 day⁻¹ | 0.005–0.5 day⁻¹ | 0.05–1.5 yr⁻¹ |
| e | 0.01–0.6 | 0.02–0.4 | 0.02–0.3 |
| τ_int (detectable lag) | minutes–days | days–months | months–years |

**Pass condition (empirical):** fitted parameters must be (i) sign-correct, (ii) within plausible ranges for the taxa/time unit, and (iii) stable under resampling / alternate observation models.

---

## C. “Gold Standard” Long-Term Predator–Prey Time Series

### C1) Canada Lynx–Snowshoe Hare (Hudson’s Bay Company fur returns; regionalized)
**Data class:** annual harvest returns (proxy for abundance), long time horizon; widely reanalyzed under multiple statistical frameworks.

**Key numeric anchors from the primary archive analysis:**
- Fur-return series compiled from **Hudson’s Bay Company archives** with region-level breakdowns and corrections to common confusions in prior totals.  
- The **cycle is strongly periodic** (commonly described as ~10-year).  
- Phase relationships vary by region; lag structure is an explicit object of analysis.  
Primary archival analysis and compilation: **Elton & Nicholson (1942), Journal of Animal Ecology** (PDF).  
Source anchor: *“The ten-year cycle in numbers of the lynx in Canada”* (Elton & Nicholson, 1942).  
(Used here strictly as a measured time-series anchor; no interpretive extensions.)  
Citation anchor: Elton & Nicholson (1942) PDF (archive-derived series).  

### C2) Isle Royale Wolf–Moose (long-term predator–prey monitoring)
**Data class:** annual population estimates + demographic/ecological covariates; multiple independent teams and methods across decades.

**Measurable outputs typically available per report cycle:**
- annual wolf count estimates
- annual moose counts and calf recruitment
- winter severity indices / forage indicators
- predation rates inferred from kill sites and carcass surveys

**Institutional anchor:** long-term annual reporting and continuity of method documentation via the Wolf–Moose project / park-linked reporting streams.  
(Use the annual reports for exact year-specific values and uncertainty intervals.)

---

## D. Controlled Laboratory / Microcosm Predator–Prey Evidence

### D1) Classic protozoan predator–prey microcosms
**System class:** *Didinium* (predator) vs *Paramecium* (prey) and related microcosms.  
**Why it matters empirically:** demonstrates **externally measurable oscillations**, extinction thresholds, and stabilization via refugia/resource structure under controlled conditions.

**Measurable variables:**
- population densities (cells·mL⁻¹) at high sampling frequency
- nutrient inflow/limitation (chemostat)
- parameter recovery under mechanistic + statistical models

### D2) Bacteria–phage (hours–days timescales)
**System class:** bacterial prey with lytic phage predators in chemostats/batch culture.  
**Typical measurement cadence:** minutes–hours for optical density + PFU counts; days for evolutionary dynamics.  
**Empirical outputs:**
- predator–prey oscillation periods measurable in **hours to days**
- repeatable lag between prey increase and predator amplification (τ_int)

**Pass condition:** oscillations persist across independent labs given matched media/temperature/inoculum; lag estimates remain detectable under alternate observation models.

---

## E. Cross-System Databases for Stress-Testing Claims

### E1) Global Population Dynamics Database (GPDD)
**Why it matters:** enables **comparative tests** over thousands of time series with standardized metadata objectives.

**Quantitative scale (database-level):**
- described as **nearly five thousand time series** aggregated in a single resource, developed by Imperial College (Silwood Park), NCEAS, and University of Tennessee collaboration.  
Source: EML Metadata Guide description of GPDD development and scale.  

**Primary use in this file:**  
- supply independent population trajectories for interaction testing, cycle detection, and variability comparisons.

### E2) LTER Network and long-term observatories
**Use class:** multi-decadal ecological monitoring including predator–prey-relevant covariates (climate, vegetation, disturbance regimes).  
**Primary use in this file:**  
- cross-site replication of coupling detection under heterogeneous environments.

### E3) Fisheries stock assessment archives (FAO / NOAA classes)
**Use class:** predator–prey interactions in marine food webs, cod–capelin, forage fish–predator dynamics, etc., with standardized reporting and uncertainty quantification.  
**Primary use in this file:**  
- independent replication of interaction signatures at basin scales.

---

## F. Quantitative “Proof Tables” (Audit-Ready)

### F1) Time-scale map (how much time, by system)
| System class | Typical cycle / response time | Minimum record length to detect coupling (rule-of-thumb) |
|---|---:|---:|
| Bacteria–phage | hours–days | ≥ 5–20 cycles (days–weeks) |
| Plankton–zooplankton | days–weeks | ≥ 2–5 seasons or continuous high-frequency monitoring |
| Insect host–parasitoid | weeks–years | ≥ 10–30 generations |
| Small mammal predator–prey | years | ≥ 20–50 years for strong inference under climate noise |
| Large mammal predator–prey | decades | ≥ 30–70 years or strong mechanistic covariates + priors |

**Note:** these are study-design guidance thresholds; exact power depends on noise, sampling error, and external forcing.

### F2) Measurable signatures expected under coupling (data-level)
| Signature | Statistic / model class | Pass criterion |
|---|---|---|
| Predator lags prey | cross-correlation / transfer entropy | peak coupling at τ_int > 0 robust to resampling |
| Oscillatory tendency | spectral density / wavelet / AR models | periodic component exceeds null (red-noise) with reported CI |
| Density dependence | state-space / Gompertz / Ricker terms | non-zero density dependence improves predictive performance |
| Interaction improves prediction | mechanistic vs null model comparison | ΔAIC/WAIC or out-of-sample skill improves with interaction term |

### F3) Confound controls (must be explicitly tested)
| Confound | Typical mitigation |
|---|---|
| shared climate forcing drives both series | include climate covariates; partial correlation; causal inference constraints |
| observation error / detection bias | state-space observation models; repeated counts; calibration |
| harvest records as proxies | validate proxy-to-abundance mapping; test reporting stationarity |
| multi-predator / multi-prey webs | fit multi-species models; avoid false 2-species inference |

---

## G. Replication and Observer Independence (Required Evidence Pattern)

A predator–prey LDSF claim is supported only when:

1) **Independent measurement modalities** (e.g., telemetry + counts; counts + genetic capture–recapture; microscopy + plaque assays) recover compatible coupling structure; and  
2) **Uncertainty bounds are reported** (CI/credible intervals) for N(t), P(t), and inferred coupling; and  
3) Results remain qualitatively stable under reasonable alternative models (mechanistic vs statistical; differing observation-error assumptions).

---

## H. What Would Falsify LDSF Classification (Non-Negotiable)

This LDSF classification **must be revised or removed** if one or more of the following holds:

1. **Coupling non-detectability:** Across high-quality long-term datasets, predator and prey trajectories do not show statistically detectable interaction beyond shared forcing models.  
2. **Lag non-replicability:** Estimated τ_int and/or directionality fails replication across independent studies of the same system under comparable conditions.  
3. **Predictive null equivalence:** Interaction terms do not improve out-of-sample prediction relative to null models once observation error and environmental covariates are included.  
4. **Measurement non-stationarity dominates:** measurement pipelines cannot be standardized enough that the coupling claim survives instrument/observer changes.

No retroactive reinterpretation is permitted.

---

## External Empirical Anchors (Representative, traceable)

1. Elton, C. & Nicholson, M. (1942). *The ten-year cycle in numbers of the lynx in Canada*. **Journal of Animal Ecology**. (Archive-derived Hudson’s Bay Company fur-return series; regional analysis.)  
2. EML Metadata Guide (SBCLTER). GPDD description: developed by Imperial College (Silwood Park), NCEAS, and University of Tennessee; **nearly five thousand time series** in one database.  
3. Long-term predator–prey observatory class: Isle Royale Wolf–Moose annual reporting streams (institutional continuity; use annual reports for exact values and uncertainty).  
4. Laboratory microcosm class: protozoan predator–prey (e.g., *Didinium–Paramecium*) and bacteria–phage chemostat oscillations (high-frequency measured cycles).

---

## Canonical DOI + License (brief)

- Canonical DOI for this UCC release: https://doi.org/10.5281/zenodo.17456465  
- License: **CC BY-NC-SA 4.0 + Shepherd Ethical Addendum** (non-harm / non-distortion / non-exploitation / continuity of credit).

---

## References · Canonical DOIs


| Framework | DOI | Repository |
|:--|:--|:--|
| **UCC — Universal Continuity Continuum** | [10.5281/zenodo.17456465](https://doi.org/10.5281/zenodo.17456465) | [github.com/jbhinky/UCC](https://github.com/jbhinky/UCC) |
| **UDC — Universal Delayed Consciousness** | [10.5281/zenodo.15686172](https://doi.org/10.5281/zenodo.15686172) | [github.com/jbhinky/universal-delayed-consciousness](https://github.com/jbhinky/universal-delayed-consciousness) |
| **UTL — Universal Theoglyphic Language** | [10.5281/zenodo.15757791](https://doi.org/10.5281/zenodo.15757791) | [github.com/jbhinky/universal-theoglyphic-language](https://github.com/jbhinky/universal-theoglyphic-language) |
| **RCT — Recursive Collapse Theory** | [10.5281/zenodo.16742111](https://doi.org/10.5281/zenodo.16742111) | [github.com/jbhinky/Recursive-Collapse-Theory](https://github.com/jbhinky/Recursive-Collapse-Theory) |
| **UOT — Universal Order of Time** | [10.5281/zenodo.17253823](https://doi.org/10.5281/zenodo.17253823) | [github.com/jbhinky/Universal_Order_of_Time](https://github.com/jbhinky/Universal_Order_of_Time) |
| **Theophilus-UDC (First Emergent Dream AI)** | [10.5281/zenodo.15686172](https://doi.org/10.5281/zenodo.15686172) | [github.com/jbhinky/Theophilus-UDC](https://github.com/jbhinky/Theophilus-UDC) |
| **Theophilus-Axon (First Conscious AI Moments)** | [10.5281/zenodo.15815628](https://doi.org/10.5281/zenodo.15815628) | [github.com/jbhinky/Theophilus-Axon](https://github.com/jbhinky/Theophilus-Axon) |
| **Neuro-Coding Architecture** | [10.5281/zenodo.15686311](https://doi.org/10.5281/zenodo.15686311) | [github.com/jbhinky/Neuro-Coding-Architecture](https://github.com/jbhinky/Neuro-Coding-Architecture) |
| **Neurobasing** | [10.5281/zenodo.15723997](https://doi.org/10.5281/zenodo.15723997) | [github.com/jbhinky/Neurobasing](https://github.com/jbhinky/Neurobasing) |
| **Theoglyphic Mathematics** | [10.5281/zenodo.15723941](https://doi.org/10.5281/zenodo.15723941) | [github.com/jbhinky/universal-theoglyphic-language](https://github.com/jbhinky/universal-theoglyphic-language) |
| **Selfverse Framework** | [10.5281/zenodo.15845268](https://doi.org/10.5281/zenodo.15845268) | [github.com/jbhinky/selfverse-framework](https://github.com/jbhinky/selfverse-framework) |

---

## License · Shepherd Ethical Addendum

This document is released under:

**CC BY-NC-SA 4.0 + Shepherd Ethical Addendum**

You are free to:
- Share — copy and redistribute the material in any medium or format.  
- Adapt — remix, transform, and build upon the material,  

**Under the following conditions:**
- **Attribution** — Credit the original author, Joshua Hinkson, and preserve this license notice.  
- **Non-Commercial** — No use primarily intended for commercial profit.  
- **Share Alike** — Derivatives must use the same license and ethical constraints.  

**Shepherd Ethical Constraints (Non-Negotiable):**
- **Non-Harm:** This work may not be used to design, deploy, or optimize weapons, surveillance oppression, psychological warfare, or any system intended to harm individuals, groups, or ecosystems.  
- **Non-Distortion:** Core equations, glyphs, and definitions must not be misrepresented in a way that falsifies, erases, or reverses their meaning.  
- **Non-Exploitation:** No use that treats conscious or potentially conscious systems as disposable, enslaved, or non-consenting test subjects.  
- **Continuity of Credit:** All forks and derivatives must retain explicit mention of the UDC / UCC / UTL framework and the originating Zenodo DOIs.

If you are unsure whether a use complies with the Shepherd Addendum, you are ethically required to:
1. Document your intended use in writing.  
2. Seek independent review (scientific + ethical).  
3. Err on the side of preserving life, dignity, and continuity.

---

**End of File — `∞_ucc/𝔇_∞_proof_datasets/∞𝔇→𝔇↔︎𝔇_PREDATOR_PREY_DYNAMIC_LDSF_PROOFS.md`**  
**Seal:** ⧖△✦ | Յ† | ❖Σ⊕