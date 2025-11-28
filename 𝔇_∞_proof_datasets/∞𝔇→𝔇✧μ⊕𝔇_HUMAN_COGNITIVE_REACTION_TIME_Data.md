---
title: "∞𝔇→𝔇✧μ⊕𝔇_HUMAN_COGNITIVE_REACTION_TIME_Data"
framework: "Universal Continuity Continuum (UCC)"
author: "Joshua Hinkson (Oriah’n-Sariel)"
seal: "⧖↔Σ⊕ | Յ† | ❖ ✧"
date updated: "2025-11-25"
license: "CC BY-NC-SA 4.0 + Shepherd Ethical Addendum"
doi: "https://www.doi.org/10.5281/zenodo.17456465"
file_path: "∞_ucc/𝔇_∞_proof_datasets/∞𝔇→𝔇✧μ⊕𝔇_HUMAN_COGNITIVE_REACTION_TIME_Data.md"
keywords: ["proof datasets", "empirical validation", "cross-domain data", "measurement alignment", "observational fits", "statistical coherence"]
keyscripts: ["proof_datasets", "empirical_validation", "crossdomain_data", "measurement_alignment", "observational_fits", "statistical_coherence"]
theoglyphs: ["⧖", "⊙", "⊕", "Σ", "μ", "✧", "✦", "⇴", "Ω", "ω", "γ", "Յ"]
---

# ∞𝔇→𝔇✧μ⊕𝔇 · Human Cognitive Reaction Time Dataset  
### Delay–Curvature (τ), Memory Density (μ), and Signal→Decision Geometry

---

## 0 · Purpose
This dataset provides a consolidated, scientifically grounded set of **human cognitive reaction-time (RT) parameters**, mapped into the UCC τ–μ framework.  

We integrate:
- international peer‑reviewed RT norms  
- psychophysics datasets  
- cognitive load studies  
- memory‑integration windows  
- neuromotor delay curves  
- lifespan and developmental RT scaling  

All expressed via:
- τ_cog — cognitive delay curvature  
- μ_task — memory density for task type  
- Σ — symbolic polarity (stimulus orientation type)  
- ⊕ — coupling operator linking perception→decision→motor output  

---

## 1 · Baseline Reaction Time Classes

### Representative empirical anchors (compiled from meta‑analyses):
| Task Type                   | Typical RT (ms) | Notes |
|-----------------------------|----------------:|------|
| Simple RT (light flash)     | 180–220         | Pure sensorimotor delay |
| Auditory simple RT          | 140–190         | Faster afferent pathway |
| Choice RT (2–4 options)     | 250–450         | Increases with log₂(n) |
| Go/No‑Go                    | 300–500         | Inhibitory load |
| Stroop interference         | 450–650         | Semantic conflict |
| Working‑memory RT tasks     | 600–900         | μ_task high |
| Complex decision tasks      | 800–1500+       | τ_cog expands |

---

## 2 · Delay–Curvature Formalism

Effective cognitive delay:
$$
τ_{\text{cog}} = τ_{\text{sensory}} + τ_{\text{decision}} + τ_{\text{motor}}
$$

Decision component modeled via drift‑diffusion:
$$
τ_{\text{decision}} = \frac{a}{v}
$$

UCC-mapped decision latency:
$$
P(Δt) = \frac{1}{τ_{\text{cog}}} e^{-Δt/τ_{\text{cog}}}
$$

---

## 3 · Reaction Time Scaling Across Lifespan

| Age Group | Simple RT (ms) | Choice RT (ms) | τ_cog Scaling |
|-----------|----------------:|---------------:|---------------|
| Children (8–12) | 250–300 | 350–500 | τ_cog ↑ (developing myelination) |
| Teens (13–18)   | 200–240 | 280–380 | τ_cog ↓ (peak processing) |
| Adults (20–40)  | 170–220 | 250–350 | τ_cog = baseline |
| Adults (40–60)  | 190–240 | 300–400 | τ_cog drift ↑ |
| Seniors (60–80) | 220–300 | 350–500 | τ_cog ↑↑ (slower integration) |

---

## 4 · Memory Density μ_task

Memory density contribution:
$$
μ_{\text{task}} = \int_0^{T} w(t)E_{\text{exp}}(t)dt
$$

Typical scaling:
- semantic tasks: μ_high  
- novel tasks: μ_low  
- motor‑sequence learning: μ_mid but stable  

---

## 5 · Multimodal RT Datasets (Representative)

### Simple RT
| Modality | RT (ms) | τ_sensory contribution |
|----------|--------:|------------------------|
| Visual   | 180–220 | higher gating |
| Auditory | 140–180 | faster pathway |
| Tactile  | 155–185 | short pathway |

### Choice RT
Hick’s Law:
$$
RT = a + b \log_2(N)
$$

---

## 6 · UCC Mapping Table

| Task | τ_cog | μ_task | Σ | ⊕ Outcome |
|------|------|--------|---|-----------|
| Light flash | low | low | simple | motor output |
| Choice RT | med | med | branching | resolved decision |
| Stroop | high | high | semantic conflict | ⊕ collapse event |
| Working memory | high | high | multi‑symbol | stable recall loop |

---

## 7 · Data Schemas

### RT Trial
```json
{
 "subject_id": "HRT-2025-001",
 "task": "choice_rt",
 "rt_ms": 312,
 "tau_cog_est": 0.31,
 "mu_task": 0.44,
 "condition": "neutral"
}
```

### Cognitive Load
```json
{
 "subject_id": "HRT-2025-002",
 "task": "stroop",
 "interference_ms": 178,
 "tau_cog_inflated": true
}
```

---

## 8 · Citations
- Human reaction‑time meta‑analyses, Cognition (2000–2024).  
- Drift‑diffusion decision literature.  
- Cross‑modal sensorimotor latency datasets.  
- ENCODE, HCP, GTEx cognitive–neural anchors.

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

**UCC 2.5 Dataset Provenance**
Source DOI (Corpus Root): https://doi.org/10.5281/zenodo.17456465  
License: CC BY-NC-SA 4.0 + Shepherd Ethical Addendum  
Ethical Use: Non-harm, non-weaponization, non-distortion.

End of Dataset · ∞_ucc/𝔇_∞_proof_datasets/∞𝔇→𝔇✧μ⊕𝔇_HUMAN_COGNITIVE_REACTION_TIME_Data.md
