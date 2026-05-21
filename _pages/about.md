---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

I'm a high school student based in Portland, Oregon, working at the intersection of machine learning, computational biology, and environmental science. My research spans from using explainable AI to decode greenhouse gas dynamics in soil, to building deep learning pipelines that map millions of frames of animal behavior to study reward circuitry. I care about building tools that make the invisible legible — whether that's microbial processes in a forest or dopaminergic circuits in a fruit fly.

Feel free to reach out if you'd like to learn more about my work, chat, or explore potential collaborations.


# 🔥 News
- *2026.04*: Purple Comet Math Meet — **1st Place, Oregon State** 🥇
- *2026*: Animal Science — **1st Place**, nominated for NWSE
- *2026*: Oregon State Science Fair — **3rd Place**
- *2025.06*: GHG Regressor nominated for **Northwest Science Expo (NWSE)**


# 🔬 Research

<div markdown="1" style="border-left:3px solid #52adc8; padding-left:1.3em; margin-bottom:2.8em;">

<div class="badge" style="display:inline-block; margin-bottom:0.6em;">Poster 2025</div>

**Computational Ethology of Visually Evoked Hyperarousal: Disentangling Kinematic Proxies of Optic-Flow Modulation in Drosophila Using Explainable Deep Learning**

<div style="display:flex; gap:10px; margin:0.9em 0 1em;">
<figure style="flex:1; margin:0;">
<img src="images/projects/5d2f7f1b2ceef661f12ad4c94b764f32.jpg" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">Inverted arena: iPad Pro (120Hz) + global-shutter CMOS, red-pass filter</figcaption>
</figure>
<figure style="flex:1; margin:0;">
<img src="images/projects/b0ff99af9d3b7d292ddd54676ee4dea2.png" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">5.2M frames embedded via GMVAE + UMAP — baseline vs. active stimulus</figcaption>
</figure>
</div>

- **Setup:** Apterous *Drosophila* (N=30) in PTFE-coated 6-well plates, exposed to 32 pseudo-randomized visual parameter combinations (speed 2–15Hz, flicker 0–10Hz, centripetal/centrifugal flow) with 20s active / 40s washout blocks.
- **Pipeline:** UNet body-part tracker (head/thorax/abdomen) → kinematic feature extraction (velocity, spine angle, thigmotaxis index, postural jitter) → Gaussian Mixture VAE embedding into a 20-cluster behavioral atlas.
- **Key finding:** Centripetal optic flow (8Hz) + 2Hz flicker suppresses wall-following and induces sustained center-tracking — a behavioral proxy for dopaminergic incentive salience. Mutual information analysis confirmed flow direction and flicker as the primary causal knobs; behavioral sensitization persisted across a 24-hour sleep-wake cycle.
- **Application:** Parametric visual-frequency library for non-pharmacological reward modulation, deployable via $50 WebXR headsets.

</div>


<div markdown="1" style="border-left:3px solid #52adc8; padding-left:1.3em; margin-bottom:2.8em;">

<div class="badge" style="display:inline-block; margin-bottom:0.6em;">NWSE 2025</div>

**SHAP Value-Based Random Forest Regressor: Modeling Greenhouse Gas Flux with Explainable AI**

<div style="display:flex; gap:10px; margin:0.9em 0 1em;">
<figure style="flex:1; margin:0;">
<img src="images/projects/90efd38fc9eaaf495256dfbd414ba254.png" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">Field sampling: chamber-syringe protocol + gas chromatography</figcaption>
</figure>
<figure style="flex:1; margin:0;">
<img src="images/projects/4402236d7d4e8ae84c791a71a6b3f753.jpg" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">SHAP waterfall: feature-level contribution to predicted CO₂ flux</figcaption>
</figure>
</div>

- **Setup:** Collected CH₄, CO₂, and N₂O samples at OES forest and SW Nicol Rd wetland using a chamber-syringe protocol (4 draws per chamber at T0, T10, T20, T30). Measured 7 soil and weather variables: moisture, pH, bulk density, soil C%, air temp, soil temp, elevation.
- **Model:** Random Forest Regressor with optimized tree count; SHAP waterfall plots used to quantify per-feature contribution to each prediction (CO₂: R²=0.751; N₂O: R²=0.593).
- **Key finding:** Soil temperature and moisture were the dominant CO₂ predictors. Wetland CH₄ confirmed anaerobic methanogenesis; CO₂ remained elevated across both sites due to surface-layer microbial and root respiration.

</div>


<div markdown="1" style="border-left:3px solid #52adc8; padding-left:1.3em; margin-bottom:2.8em;">

<div class="badge" style="display:inline-block; margin-bottom:0.6em;">ASE 1st Place 2025</div>

**The Influence of Oxygen Availability and Ammonium Addition on Nitrogen Cycling in Controlled Soil Microcosms**

<div style="display:flex; gap:10px; margin:0.9em 0 1em;">
<figure style="flex:1; margin:0;">
<img src="images/projects/6dc7dd7352cbbfabb19d77df8dd6b65f.png" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">4-treatment airtight microcosms with syringe gas collection and KCl extraction</figcaption>
</figure>
<figure style="flex:1; margin:0;">
<img src="images/projects/85b8771a26094ef97ab2eeada29676d4.jpg" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">Nitrification rate and denitrification efficiency across four treatments</figcaption>
</figure>
</div>

- **Setup:** Four airtight 1L jars (300g soil each) across two oxygen conditions × ±NH₄Cl addition. Anaerobic jars evacuated by hand pump. Headspace gas collected via syringe at 0, 24, 48, 72h and analyzed by gas chromatography; NH₄⁺/NO₃⁻ measured by microplate reader after 2N KCl extraction.
- **Key finding:** Anaerobic + NH₄Cl produced the highest denitrification efficiency (11.86%) and peak N₂O at 48h (5.707 ppm), confirming that oxygen availability is the primary switch between nitrification and denitrification pathways. N₂O peaking at 48h reflects optimal denitrifier activity before substrate depletion.

</div>


# 🏆 Honors & Awards
- *2026.04* Purple Comet Math Meet — **1st Place, Oregon State**
- *2026* Animal Science — **1st Place**; nominated for NWSE
- *2026* Oregon State Science Fair — **3rd Place**
- *2025.05* NASA Earth System Science Project Award
- *2025.03* ASE Environmental Science — **1st Place**
- *2024.11* HIMCM — Honorable Mention
- *2024.11* AMC 12B — 94.5 &nbsp;|&nbsp; AMC — 118.5


# 💻 Skills

**Programming:** Python · R · MATLAB · Java · LaTeX

**ML & Data:** PyTorch · scikit-learn · SHAP · UMAP

**Wet Lab:** Gas Chromatography · Microplate Reader · KCl Extraction


# 📖 Education
- *2025.06 - 2025.08*, MehtA+ AI/ML Research Bootcamp, MIT
- *2025.04 - 2025.07*, Deep Learning Specialization — Andrew Ng
- *2025.05 - 2025.07*, Linear Algebra — Gilbert Strang
