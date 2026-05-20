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

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">Poster 2025</div><img src='images/projects/b0ff99af9d3b7d292ddd54676ee4dea2.png' alt="Drosophila UMAP behavioral atlas" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

**Computational Ethology of Visually Evoked Hyperarousal: Disentangling Kinematic Proxies of Optic-Flow Modulation in Drosophila Using Explainable Deep Learning**

Carmen Wang

<img src='images/projects/5d2f7f1b2ceef661f12ad4c94b764f32.jpg' width="100%" style="margin-bottom:8px; border-radius:4px;">

**Lab Design:** Apterous *Drosophila* (N=30) in a PTFE-coated 6-well plate, illuminated by an inverted iPad Pro (120Hz) delivering high-contrast magenta stimuli. A global-shutter CMOS camera with a red-pass lens filter captured ground-level kinematics across 32 parameter combinations (speeds 2–15Hz, flicker 0–10Hz, centripetal/centrifugal patterns) in a pseudo-randomized block design.

**Pipeline:** UNet body-part tracker (head/thorax/abdomen) → kinematic feature extraction (velocity, spine angle, thigmotaxis index, postural jitter) → **Gaussian Mixture VAE** embedding 5.2M frames into a 20-cluster behavioral atlas (UMAP above).

**Key findings:** Centripetal optic flow (8Hz) + 2Hz flicker acts as a "neural anchor," suppressing wall-following and inducing center-biased tracking. Mutual information analysis identified pattern direction and flicker as primary causal knobs. Behavioral sensitization across a 24-hour sleep-wake cycle suggests dopaminergic neuroadaptation.

</div>
</div>


<div class='paper-box'><div class='paper-box-image'><div><div class="badge">NWSE 2025</div><img src='images/projects/4402236d7d4e8ae84c791a71a6b3f753.jpg' alt="SHAP waterfall plot CO2 flux" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

**SHAP Value-Based Random Forest Regressor: Modeling Greenhouse Gas Flux with Explainable AI**

Carmen Wang

<img src='images/projects/90efd38fc9eaaf495256dfbd414ba254.png' width="100%" style="margin-bottom:8px; border-radius:4px;">

**Lab Design:** Collected field gas samples (CH₄, CO₂, N₂O) at OES forest and SW Nicol Rd wetland using a chamber-syringe protocol — 4 syringe draws per chamber at T0, T10, T20, T30. Measured 7 soil/weather variables including moisture, pH, bulk density, soil C%, and temperature. Samples analyzed by gas chromatography.

**Model:** Random Forest Regressor with hyperparameter optimization; applied **SHAP waterfall analysis** to quantify per-feature contribution to predicted flux (CO₂ R²=0.751; N₂O R²=0.593).

**Key findings:** Soil temperature and moisture were dominant CO₂ predictors. Wetland CH₄ flux confirmed anaerobic methanogenesis; CO₂ remained elevated across both sites due to microbial and root respiration at surface layers.

</div>
</div>


<div class='paper-box'><div class='paper-box-image'><div><div class="badge">ASE 1st Place 2025</div><img src='images/projects/6d28a0600d7246c1db8070b49586df0f.jpg' alt="Nitrogen cycling soil jars" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

**The Influence of Oxygen Availability and Ammonium Addition on Nitrogen Cycling in Controlled Soil Microcosms**

Carmen Wang

<img src='images/projects/6dc7dd7352cbbfabb19d77df8dd6b65f.png' width="100%" style="margin-bottom:8px; border-radius:4px;">

**Lab Design:** Four airtight 1L jars filled with 300g of soil from a single forest site, split into four treatments: Aerobic control, Aerobic + NH₄Cl, Anaerobic control, Anaerobic + NH₄Cl. Anaerobic conditions created by hand pump evacuation. Headspace gas collected via syringe at 0, 24, 48, 72h; analyzed by **gas chromatography** for N₂O, CO₂, CH₄. Final NH₄⁺/NO₃⁻ concentrations measured by **microplate reader** after 2N KCl extraction.

**Key findings:** Anaerobic + NH₄Cl treatment produced peak N₂O at 48h (5.707 ppm) and highest denitrification efficiency (11.86%), confirming oxygen availability as the primary pathway switch. Progressive N₂O increase to 48h reflects optimal denitrifier activity before substrate depletion.

</div>
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

**Languages:** Python · R · MATLAB · Java · LaTeX

**Frameworks & Tools:** PyTorch · scikit-learn · SHAP · Gas Chromatography · Microplate Reader


# 📖 Education
- *2025.06 - 2025.08*, MehtA+ AI/ML Research Bootcamp, MIT
- *2025.04 - 2025.07*, Deep Learning Specialization — Andrew Ng
- *2025.05 - 2025.07*, Linear Algebra — Gilbert Strang
