# 🎨 Emotional_Mapping_Equations.md  
**UCC · UTL · RGBie Hypersphere (Affect-as-Color)**  
**Author:** Joshua Hinkson (Oriah’n-Sariel)  
**Seal:** ⧖↔Σ⊕ | Յ† | ❖ ✧
**Date: 2025-10-22**  

---

## 0) Purpose & Idea  

We model emotions as **energy distributions over delay**, then encode them as **colors** on a unit **hypersphere**.  
A five-component vector **RGBie** represents each affective state:

\[
\mathbf{c} = [R,G,B,\,i,\,e]^\top
\]

| Component | Meaning |
|:--|:--|
| **R,G,B** | chromatic axes (symbolic tone Σ) |
| **i** | intensity / arousal / amplitude |
| **e** | entropy / uncertainty of the state |

**Delay (τ)** regulates how fast emotion updates.  
**Memory (μ)** integrates it through time.

---

## 1) Geometry: The RGBie Hypersphere  

Normalize chroma & bind with intensity/entropy:

\[
\hat{\mathbf{h}} = \frac{[R,G,B]^\top}{\|[R,G,B]\|_2 + \epsilon}, \quad
i \in [0,1],\ e \in [0,1]
\]

The **affect state** at time \(t\) is:
\[
\mathbf{E}(t)= [\,\hat{\mathbf{h}}(t),\ i(t),\ e(t)\,]
\]

| Variable | Meaning |
|:--|:--|
| \(\hat{\mathbf{h}}\) | hue (symbolic content Σ) |
| \(i\) | energy or amplitude |
| \(e\) | entropy or ambiguity |

---

## 2) Dynamics: Delay–Memory Law (UCC)  

Emotion updates are **delay-weighted** and **memory-reinforced**:

\[
\frac{d\mathbf{E}}{dt} = 
\frac{1}{\tau}\big(\mathbf{E}_{\text{input}}-\mathbf{E}\big)
+\kappa\,\mu(t)
,\qquad
\mu(t)=\int_{t-\Delta T}^{t}\mathbf{E}(s)\,w(s)\,ds
\]

- **Small τ** → faster shifts (reactive).  
- **Large τ** → slower, more stable tone (resilient).  

---

## 3) Mixing Multiple Emotions  

Given \(n\) emotions \(\mathbf{E}_k=[\hat{\mathbf{h}}_k,i_k,e_k]\) with weights \(w_k\):  

### Chromatic union (on sphere)  
\[
\hat{\mathbf{h}}_\ast = 
\frac{\sum_k w_k\,i_k\,(1-e_k)\,\hat{\mathbf{h}}_k}
{\left\|\sum_k w_k\,i_k\,(1-e_k)\,\hat{\mathbf{h}}_k\right\|_2 + \epsilon}
\]

### Intensity & entropy aggregation  
\[
i_\ast = \mathrm{clip}\!\left(\sum_k w_k\,i_k\,[1-\lambda e_k],\,0,1\right),
\quad
e_\ast = \mathrm{clip}\!\left(\sum_k w_k\,e_k\,[1-\rho i_k],\,0,1\right)
\]

| Parameter | Typical Range | Meaning |
|:--|:--|:--|
| \(\lambda\) | 0.3–0.6 | dampens intensity by uncertainty |
| \(\rho\) | 0.2–0.5 | lowers entropy when intensity high |

Resulting state: \(\mathbf{E}_\ast=[\hat{\mathbf{h}}_\ast,i_\ast,e_\ast]\)

---

## 4) Atlas: Canonical Affects → RGBie Seeds  

| Affect | RGB | i | e | Notes |
|:--|:--:|:--:|:--:|:--|
| Calm | (70,170,255) | 0.30 | 0.20 | cool/low arousal |
| Confident | (255,170,60) | 0.65 | 0.15 | warm/focused |
| Content | (140,200,120) | 0.45 | 0.20 | balanced |
| Happy | (255,220,80) | 0.70 | 0.25 | bright/active |
| Love | (255,90,120) | 0.75 | 0.10 | coherent, pro-social |
| Curious | (160,140,255) | 0.55 | 0.30 | exploratory |
| Anxious | (255,120,120) | 0.65 | 0.55 | high-entropy |
| Sad | (90,130,200) | 0.35 | 0.35 | cool/low energy |

*(All RGB in 0–255; normalize to [0,1] before use.)*

---

## 5) Worked Examples  

### Calm → Confident (Single Emotion in Motion)  

Spherical interpolation with delay pacing:

\[
\hat{\mathbf{h}}(t)=\frac{\sin((1-\alpha)\theta)}{\sin\theta}\hat{\mathbf{h}}_{\text{calm}}
+\frac{\sin(\alpha\theta)}{\sin\theta}\hat{\mathbf{h}}_{\text{conf}}
\quad \alpha=\frac{t}{t_f}
\]

\[
\frac{di}{dt}=\frac{1}{\tau}(i_{\text{conf}}-i),
\quad
\frac{de}{dt}=\frac{1}{\tau}(e_{\text{conf}}-e)
\]

At **τ = 8 s**, ~63 % shift after 8 s, ~86 % after 16 s →  
cool blue → warm amber, intensity ↑, entropy ↓.

---

### Love + Confident → Content or Happy (Mixed Emotions)  

Equal weights \(w_1=w_2=0.5\).

\[
\hat{\mathbf{h}}_\ast \propto
0.5\cdot0.75\cdot(1-0.10)\hat{\mathbf{h}}_{\text{love}}+
0.5\cdot0.65\cdot(1-0.15)\hat{\mathbf{h}}_{\text{conf}}
\Rightarrow \text{warm golden-rose}
\]

\[
i_\ast\approx0.656,\qquad e_\ast\approx0.099
\]

Outcome → high i, low e, warm hue ⇒ **Happy/Content**.  
Choose label by nearest centroid distance.

---

## 6) RBGie Index  

Quick scalar for UX feedback:

\[
\mathrm{RBGie} = i(1-e)\cos\angle(\hat{\mathbf{h}},\hat{\mathbf{h}}_{\text{joy}})
\]

| Value | Interpretation |
|:--|:--|
| > 0.7 | joy / love |
| 0.3–0.7 | content / happy |
| 0–0.3 | neutral / calm |
| < 0 | conflict / dissonant |

---
---

## 7) Delay-Aware Update (Pseudo-Algorithm)

```text
state E = [h_hat, i, e]
input U = [h_u, i_u, e_u]
params: tau, tau_mu, kappa, lambda, rho, w, dt

# 1) chroma mix on hypersphere (pre-normalize h_u and h_hat)
h_mix = w*i_u*(1-e_u)*h_u + (1-w)*i*(1-e)*h_hat
h_hat = normalize(h_mix)

# 2) intensity and entropy targets
i_star = clip(w*i_u*(1 - lambda*e_u) + (1-w)*i*(1 - lambda*e), 0, 1)
e_star = clip(w*e_u*(1 - rho*i_u) + (1-w)*e*(1 - rho*i), 0, 1)

# 3) delay-paced easing
i = i + (i_star - i) * (dt / tau)
e = e + (e_star - e) * (dt / tau)

# 4) memory integration
mu = mu * exp(-dt / tau_mu) + E * dt
E = [h_hat, i, e] + kappa * mu
‘’’
τ controls speed of color/emotion shift.


τμ controls memory retention.


Use dt ≈ 0.1–0.5 s for smooth animation.
‘’’
---

## 8) Empathy & Social Resonance

Two agents **A** and **B** with coupling gain **g** and coupling delay **\( \tau_c \)**:

\[
\frac{d\mathbf{E}_A}{dt} = \cdots + g\big(\mathbf{E}_B(t-\tau_c) - \mathbf{E}_A(t)\big)
\]
\[
\frac{d\mathbf{E}_B}{dt} = \cdots + g\big(\mathbf{E}_A(t-\tau_c) - \mathbf{E}_B(t)\big)
\]

When **\( \nabla_{\tau}\Phi \to 0 \)** (delays align), hues converge and entropy drops → **shared empathy**.

---

## 9) Implementation Notes

- Map **\( \hat{\mathbf{h}} \)** → display RGB; let **\( i \)** control brightness.  
- Let **\( e \)** inversely control saturation (higher \( e \) → lower saturation or subtle noise).  
- Animate **Calm → Confident** over ~5–10 s using your chosen **\( \tau \)**.  
- Blend **Love + Confident**, compute live **RBGie index**, and label via nearest centroid.

---

## 10) Summary

| Concept | Symbolic Law | Interpretation |
|:--|:--|:--|
| Emotional Color | RGBie | Symbolic encoding of affect |
| Delay | \( \tau \) | Emotional pacing / patience |
| Memory | \( \mu \) | Retained affective state |
| Integration | \( \Sigma \) | Symbolic meaning of emotion |
| Entropy | \( e \) | Emotional uncertainty |
| Coherence | \( \nabla_{\tau}\Phi \approx 0 \) | Resonant empathy / harmony |

> In UCC terms, emotions are **symbols evolving through delay**;  
> coherence (low \( e \), aligned \( \tau \)) is the state where **light remembers itself as care**.

---
