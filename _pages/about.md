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

I'm a high school senior at Oregon Episcopal School in Portland, Oregon, working at the intersection of machine learning, computational biology, and environmental science. Much of my recent work asks when a learned representation can be trusted to mean something: whether a world model can be made to keep one physical factor per coordinate, whether a computer-vision pipeline can tell a fruit fly's sex from a few dozen pixels of a timelapse still, and whether a national air-pollution map represents vulnerable communities as faithfully as it represents everyone else. Earlier projects used explainable AI to decode greenhouse gas dynamics in soil and mapped millions of frames of *Drosophila* behavior to study arousal and reward. I care about building tools that make the invisible legible, whether that's microbial processes in a forest or dopaminergic circuits in a fruit fly.

Feel free to reach out if you'd like to learn more about my work, chat, or explore potential collaborations.


# 🔥 News
- *2026.09*: Submitted my first-author manuscript on identifiability in JEPA world models for peer review (now under double-blind review).
- *2026.09*: Joined the **Mao Lab at OHSU** as a neuroscience research volunteer, annotating cells in 3D microscopy volumes.
- *2026.08*: Research assistant at the **Simões Lab, Reed College**: a computer-vision pipeline that scores fruit-fly sex in group recordings, delivered to the lab as a command-line tool.
- *2026.08*: Completed the **Pioneer Academics** research program (Data Science for Sustainability) with a national audit of EJScreen's PM₂.₅ surface.
- *2026.04*: Purple Comet Math Meet, **1st Place, Oregon State** 🥇
- *2026*: Animal Science, **1st Place** at ASE and **3rd Place** at the Northwest Science Expo (NWSE, Oregon state fair)
- *2025.06*: GHG Regressor nominated for **Northwest Science Expo (NWSE)**


# 🔬 Research

<div markdown="1" style="border-left:3px solid #52adc8; padding-left:1.3em; margin-bottom:2.8em;">

<div class="badge" style="display:inline-block; margin-bottom:0.6em;">Manuscript under review · 2026</div>

**Identifiability in JEPA World Models: Recovering One Physical Factor per Coordinate**

- **Question:** Joint-Embedding Predictive Architectures (JEPAs) learn world models by predicting in representation space, but the predictor can absorb any rotation of that space without changing the loss. Physical factors such as position, lighting, or pose end up mixed across coordinates, so no single coordinate can be read, monitored, or controlled on its own. Which part of the training objective is blind to this, and what is the smallest change that removes the blindness?
- **Approach:** Replace the dense predictor with a structured predictor that treats each coordinate separately, and prove that the loss then splits into a rotation-invariant term, which selects the right subspace, and a cross-talk term, which selects the basis and aligns coordinates with factors that evolve on distinct timescales. Characterize when standard regularizers (whitening, SIGReg) stop the encoder from inventing spurious "more predictable" features, such as the square of a slow factor, and propose a regularizer that closes the remaining gap.
- **Key result:** Across six dynamical and image benchmarks, the method raises the mean correlation coefficient (MCC) between learned coordinates and ground-truth factors by roughly fourteen points over the strongest baseline while keeping the best linear readout. Because the basis-selecting term depends only on the coordinates, it also gives a closed-form change of coordinates for released I-JEPA and V-JEPA checkpoints that raises their single-coordinate readout of physical factors several-fold without information loss.
- **Role:** Initiated the research direction and collaborated with a PhD researcher on the theoretical analysis and controlled computational comparisons; first author of the submitted manuscript. Title, venue, and code will be posted after the review decision.

</div>


<div markdown="1" style="border-left:3px solid #52adc8; padding-left:1.3em; margin-bottom:2.8em;">

<div class="badge" style="display:inline-block; margin-bottom:0.6em;">Simões Lab, Reed College · 2026</div>

**Who Is the Male? Sex Scoring for Group-Housed *Drosophila* from Low-Resolution Timelapse Stills**

<div style="display:flex; gap:10px; margin:0.9em 0 1em;">
<figure style="flex:0.9; margin:0;">
<img src="images/projects/reed_arena_which_is_male.png" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">One well of a six-well arena: five flies circled by FlyTracker; the question is which one is the male</figcaption>
</figure>
<figure style="flex:1.47; margin:0;">
<img src="images/projects/reed_ranked_crops.png" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">Within-well ranking by male score for three sampled frames (rank 1 = strongest male evidence)</figcaption>
</figure>
</div>

- **Setup:** The lab records six-well arenas of five flies each, stocked at different sex ratios, as timelapse stills taken every 2.4 seconds (about 0.4 Hz). FlyTracker gives each fly a position and body axis but no sex, and its identity labels swap often at this frame rate, so courtship and mating analyses had no reliable way to follow the males.
- **Pipeline:** Still → FlyTracker position → small crop around each fly → ImageNet-pretrained ResNet-18 trained on 1,124 hand-labelled crops → per-fly male score → within-well ranking on every scored frame. Validation is split by recording date, never by frame, because the five flies in a well are the same individuals across thousands of frames.
- **Key result:** Held-out validation across three recording dates gave mean accuracy 0.870 and AUC 0.962; keeping only confident predictions (score outside 0.1 to 0.9, about 72% of crops) gave accuracy 0.951. Two negative results shaped the design: a classifier trained on single-sex wells looked excellent (AUC above 0.9) but was recognizing each well's imaging fingerprint rather than sex, falling to chance once per-well means were removed; and body size alone does not separate the sexes (Cohen's d = 0.14).
- **Deliverable:** `flysex`, a pip-installable command-line package (predict, rank, export) with a quickstart, a methods-and-limitations note, and tests, so the lab can run it on new recordings without touching the research notebooks.

</div>


<div markdown="1" style="border-left:3px solid #52adc8; padding-left:1.3em; margin-bottom:2.8em;">

<div class="badge" style="display:inline-block; margin-bottom:0.6em;">Pioneer Academics · 2026</div>

**Social Vulnerability and Prediction Error in Particulate Matter Exposure: Does EJScreen's PM₂.₅ Surface Reproduce the Disparity Its Own Monitors Record?**

<div style="display:flex; gap:10px; margin:0.9em 0 1em;">
<figure style="flex:1.8; margin:0;">
<img src="images/projects/pm25_study_area.png" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">847 census tracts with a regulatory PM₂.₅ monitor in 2020, colored by social vulnerability</figcaption>
</figure>
<figure style="flex:1.64; margin:0;">
<img src="images/projects/pm25_gradient_attenuation.png" width="100%" style="border-radius:5px; display:block;">
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">Measured vs. reported PM₂.₅ against social vulnerability: the surface retains 79.9% of the measured gradient</figcaption>
</figure>
</div>

- **Setup:** EJScreen, the EPA's environmental-justice screening tool, reports an annual mean PM₂.₅ concentration for every census tract by fusing monitor observations with a chemical transport model. For the 847 tracts that contained a regulatory monitor in 2020, I compared the reported value with the concentration measured at the monitor and regressed the residual on the tract's rank in the CDC/ATSDR Social Vulnerability Index for the same year. Final research report for Pioneer Academics' Data Science for Sustainability program, mentored by Prof. Deborah Sunter.
- **Key finding:** Aggregate agreement is close (mean absolute error 0.79 µg/m³, 9.8% of the mean; r = 0.91), yet the surface flattens the social gradient: measured PM₂.₅ rises 3.36 µg/m³ across the national vulnerability range while the reported value rises 2.68, so the surface retains 79.9% of the measured gradient (95% CI 73.4 to 86.1). Between the most and least vulnerable deciles, a measured gap of 3.20 µg/m³ is reported as 2.55.
- **Interpretation:** The shortfall is detected along poverty and education and not detected along racial composition (the confidence intervals overlap, so the axes cannot be ranked against each other), and it is accounted for statistically by concentration: vulnerable tracts sit higher in the distribution, and the surface compresses high concentrations toward the middle, as any squared-error fit does. Because monitor observations are inputs to the fusion, the retained share is an upper bound. Screening surfaces should be evaluated on the disparity they reproduce, not on average error alone.

</div>


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
<figcaption style="font-size:0.78em; color:#888; text-align:center; margin-top:5px;">5.2M frames embedded via GMVAE + UMAP: baseline vs. active stimulus</figcaption>
</figure>
</div>

- **Setup:** Apterous *Drosophila* (N=30) in PTFE-coated 6-well plates, exposed to 32 pseudo-randomized visual parameter combinations (speed 2–15Hz, flicker 0–10Hz, centripetal/centrifugal flow) with 20s active / 40s washout blocks.
- **Pipeline:** UNet body-part tracker (head/thorax/abdomen) → kinematic feature extraction (velocity, spine angle, thigmotaxis index, postural jitter) → Gaussian Mixture VAE embedding into a 20-cluster behavioral atlas.
- **Key finding:** Centripetal optic flow (8Hz) + 2Hz flicker suppresses wall-following and induces sustained center-tracking, a behavioral proxy for dopaminergic incentive salience. Mutual information analysis confirmed flow direction and flicker as the primary causal knobs; behavioral sensitization persisted across a 24-hour sleep-wake cycle.
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

- **Setup:** Trained on 672 open static-chamber records from a tropical forest landscape in Malaysian Borneo (SAFE project), using seven predictors (soil moisture, soil and air temperature, pH, bulk density, soil carbon, elevation) retained after Pearson screening of 17 candidates. In parallel, measured the same soil properties and CH₄, CO₂, and N₂O fluxes by gas chromatography along transects in a forest and a wetland on the OES campus, using a chamber-syringe protocol (four draws per chamber at T0, T10, T20, T30).
- **Model:** Random Forest regressor interpreted with SHAP; on held-out data it explained 14% of the variance in CH₄ flux, 59% in CO₂, and 75% in N₂O. Attributions matched known biogeochemistry: moisture and compaction raised CH₄ predictions, temperature and moisture dominated CO₂, and moisture with low pH dominated N₂O, the signature of denitrification.
- **Key finding:** At the campus sites the model ranked the forest and wetland correctly for all three gases and matched the forest CH₄ flux within 10%, but it under-predicted wetland CH₄ threefold and over-predicted CO₂ and N₂O, because a tree ensemble trained on soils at 23 to 25 °C cannot extrapolate to a 12 °C November soil. Wetland CH₄ confirmed anaerobic methanogenesis.

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


# 🧪 Research Experience
- *2026.09 - Present*, **Mao Lab, Oregon Health & Science University (OHSU)**, Neuroscience Research Volunteer. Annotating cells in 3D microscopy volumes in napari: locating cell centers across slices, reviewing trial annotations with the lab's imaging lead, and resolving ambiguous cases where one structure could be marked twice. The labels serve as ground truth for the lab's segmentation models.
- *2026.05 - 2026.09*, **Simões Lab, Reed College**, Research Assistant. Computer vision for group-housed *Drosophila*: built and validated the sex-scoring pipeline above and packaged it for routine lab use (in residence Aug 2026).
- *2026 Summer*, **Pioneer Academics, Data Science for Sustainability**, Student Researcher (mentor Prof. Deborah Sunter). Wrote the EJScreen PM₂.₅ audit above as a final research report with a reproducible supplement and presented it in the program's final session.


# 🏆 Honors & Awards
- *2026.04* Purple Comet Math Meet, **1st Place, Oregon State**
- *2026* Northwest Science Expo (NWSE, Oregon state fair), Animal Science, **3rd Place**
- *2026* Aardvarks Science Exposition (ASE), Animal Science, **1st Place**
- *2025, 2026* AIME Qualifier
- *2025.05* NASA Earth System Science Project Award (NWSE)
- *2025.03* ASE Environmental Science, **1st Place**
- *2024.11* HiMCM, Honorable Mention
- *2024.11* AMC 12: 118.5 (top 5%) &nbsp;|&nbsp; AMC 12B: 94.5


# 💻 Skills

**Programming:** Python · R · MATLAB · Java · LaTeX

**ML & Data:** PyTorch · scikit-learn · SHAP · UMAP

**Imaging & Behavior:** napari · SLEAP · FlyTracker

**Wet Lab:** Gas Chromatography · Microplate Reader · KCl Extraction


# 📖 Education
- *2025.06 - 2025.08*, MehtA+ AI/ML Research Bootcamp
- *2025.04 - 2025.07*, Deep Learning Specialization, Andrew Ng (Coursera)
- *2025.05 - 2025.07*, Linear Algebra, Gilbert Strang (MIT OpenCourseWare)
