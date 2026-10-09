---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<div class="intro" markdown="1">
<p class="eyebrow">Machine learning · Computational biology · Environmental science</p>

# About me
{: #about-me}

I'm a high school senior at **Oregon Episcopal School** in Portland, Oregon. I study machine learning, computational biology, and environmental science, with a focus on interpretable models and reliable measurement.

My recent work explores identifiable representations in world models, computer vision for fruit-fly behavior, and bias in air-pollution estimates. Earlier projects examined soil greenhouse gas fluxes and visually evoked behavior in *Drosophila*.

<p class="contact-note">Interested in my work or a collaboration? <a href="mailto:wangmu@go.oes.edu">Get in touch <span aria-hidden="true">↗</span></a></p>
</div>

<span class="legacy-anchor" id="-news" aria-hidden="true"></span>
## News
{: #news .section-title}

<ul class="dated-list news-list">
  <li><span class="entry-date">Sep 2026</span><div>Submitted my first-author manuscript on identifiability in JEPA world models for peer review.</div></li>
  <li><span class="entry-date">Sep 2026</span><div>Joined the <strong>Mao Lab at OHSU</strong> as a neuroscience research volunteer.</div></li>
  <li><span class="entry-date">Aug 2026</span><div>Delivered a fruit-fly sex-scoring tool to the <strong>Simões Lab, Reed College</strong>.</div></li>
  <li><span class="entry-date">Aug 2026</span><div>Completed <strong>Pioneer Academics</strong> with an audit of EJScreen's PM₂.₅ estimates.</div></li>
  <li><span class="entry-date">Apr 2026</span><div><strong>1st Place in Oregon</strong>, Purple Comet Math Meet.</div></li>
  <li><span class="entry-date">2026</span><div>Animal Science: <strong>1st Place at ASE</strong> and <strong>3rd Place at NWSE</strong>.</div></li>
  <li><span class="entry-date">Jun 2025</span><div>GHG Regressor nominated for the <strong>Northwest Science Expo</strong>.</div></li>
</ul>

<span class="legacy-anchor" id="-research" aria-hidden="true"></span>
## Research
{: #research .section-title}

<div class="paper-box" id="world-models" markdown="1">

<p class="project-meta">Under review · 2026</p>

### Identifiability in JEPA world models

<p class="paper-authors"><strong>Carmen Wang</strong> (first author), with a PhD collaborator · Manuscript under double-blind review</p>
<div class="paper-tags"><span class="paper-tag">World models</span><span class="paper-tag">Identifiability</span><span class="paper-tag">Representation learning</span></div>

<div class="project-figures project-figures--single">
<figure>
<a href="/images/papers/jepa_concept.png" aria-label="Enlarge figure: Schematic of the question, not a result from the manuscript"><img src="/images/papers/jepa_concept.png" alt="Schematic of the question, not a result from the manuscript" loading="lazy" decoding="async"></a>
<figcaption>Schematic of the question, not a result from the manuscript</figcaption>
</figure>
</div>

When do predictive representations separate meaningful physical factors rather than mix them across coordinates?

**Key result:** The study identifies conditions that improve the alignment between learned coordinates and physical factors while preserving predictive information.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Approach:** Combined theoretical analysis with controlled computational experiments to study how model structure and regularization affect identifiability.

**Role:** Initiated the research direction and collaborated with a PhD researcher on theoretical analysis and controlled computational comparisons. First author of the submitted manuscript.

**Availability:** The manuscript is under double-blind review. The title, venue, detailed results, and code are withheld during review.

</details>

</div>

<div class="paper-box" id="fly-sex-scoring" markdown="1">

<p class="project-meta">Simões Lab · 2026</p>

### Who is the male? Sex scoring for group-housed *Drosophila*

<p class="paper-authors"><strong>Carmen Wang</strong> · Research Assistant, Simões Lab, Reed College</p>
<div class="paper-tags"><span class="paper-tag">Computer vision</span><span class="paper-tag">ResNet-18</span><span class="paper-tag">Animal behavior</span><span class="paper-tag">Lab tool</span></div>

<div class="project-figures project-figures--reed">
<figure>
<a href="/images/projects/reed_arena_which_is_male.png" aria-label="Enlarge figure: One well of a six-well arena: five flies circled by FlyTracker; the question is which one is the male"><img src="/images/projects/reed_arena_which_is_male.png" alt="One well of a six-well arena: five flies circled by FlyTracker; the question is which one is the male" loading="lazy" decoding="async"></a>
<figcaption>One well of a six-well arena: five flies circled by FlyTracker; the question is which one is the male</figcaption>
</figure>
<figure>
<a href="/images/projects/reed_ranked_crops.png" aria-label="Enlarge figure: Within-well ranking by male score for three sampled frames (rank 1 = strongest male evidence)"><img src="/images/projects/reed_ranked_crops.png" alt="Within-well ranking by male score for three sampled frames (rank 1 = strongest male evidence)" loading="lazy" decoding="async"></a>
<figcaption>Within-well ranking by male score for three sampled frames (rank 1 = strongest male evidence)</figcaption>
</figure>
</div>

A computer-vision pipeline for identifying males in low-resolution timelapse recordings, packaged for routine lab use.

**Key result:** Held-out validation across three recording dates gave mean accuracy 0.870 and AUC 0.962; keeping only confident predictions (score outside 0.1 to 0.9, about 72% of crops) gave accuracy 0.951. Two negative results shaped the design: a classifier trained on single-sex wells looked excellent (AUC above 0.9) but was recognizing each well's imaging fingerprint rather than sex, falling to chance once per-well means were removed; and body size alone does not separate the sexes (Cohen's d = 0.14).

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Setup:** The lab records six-well arenas of five flies each, stocked at different sex ratios, as timelapse stills taken every 2.4 seconds (about 0.4 Hz). FlyTracker gives each fly a position and body axis but no sex, and its identity labels swap often at this frame rate, so courtship and mating analyses had no reliable way to follow the males.

**Pipeline:** Still → FlyTracker position → small crop around each fly → ImageNet-pretrained ResNet-18 trained on 1,124 hand-labeled crops → per-fly male score → within-well ranking on every scored frame. Validation is split by recording date, never by frame, because the five flies in a well are the same individuals across thousands of frames.

**Deliverable:** `flysex`, a pip-installable command-line package (predict, rank, export) with a quickstart, a methods-and-limitations note, and tests, so the lab can run it on new recordings without touching the research notebooks.

</details>

</div>

<div class="paper-box" id="pm25-audit" markdown="1">

<p class="project-meta">Pioneer Academics · 2026</p>

### Social vulnerability and error in EJScreen’s PM₂.₅ estimates

<p class="paper-authors"><strong>Carmen Wang</strong>; mentor Prof. Deborah Sunter · Final research report, Pioneer Academics</p>
<div class="paper-tags"><span class="paper-tag">Environmental justice</span><span class="paper-tag">Air quality</span><span class="paper-tag">Measurement error</span></div>

<div class="project-figures">
<figure>
<a href="/images/projects/pm25_study_area.png" aria-label="Enlarge figure: 847 census tracts with a regulatory PM₂.₅ monitor in 2020, colored by social vulnerability"><img src="/images/projects/pm25_study_area.png" alt="847 census tracts with a regulatory PM₂.₅ monitor in 2020, colored by social vulnerability" loading="lazy" decoding="async"></a>
<figcaption>847 census tracts with a regulatory PM₂.₅ monitor in 2020, colored by social vulnerability</figcaption>
</figure>
<figure>
<a href="/images/projects/pm25_gradient_attenuation.png" aria-label="Enlarge figure: Measured vs. reported PM₂.₅ against social vulnerability: the surface retains 79.9% of the measured gradient"><img src="/images/projects/pm25_gradient_attenuation.png" alt="Measured vs. reported PM₂.₅ against social vulnerability: the surface retains 79.9% of the measured gradient" loading="lazy" decoding="async"></a>
<figcaption>Measured vs. reported PM₂.₅ against social vulnerability: the surface retains 79.9% of the measured gradient</figcaption>
</figure>
</div>

An audit of whether a national air-pollution surface preserves the exposure disparities measured by regulatory monitors.

**Key finding:** Aggregate agreement is close (mean absolute error 0.79 µg/m³, 9.8% of the mean; r = 0.91), yet the surface flattens the social gradient: measured PM₂.₅ rises 3.36 µg/m³ across the national vulnerability range while the reported value rises 2.68, so the surface retains 79.9% of the measured gradient (95% CI 73.4% to 86.1%). Between the most and least vulnerable deciles, a measured gap of 3.20 µg/m³ is reported as 2.55.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Setup:** EJScreen, the EPA's environmental-justice screening tool, reports an annual mean PM₂.₅ concentration for every census tract by fusing monitor observations with a chemical transport model. For the 847 tracts that contained a regulatory monitor in 2020, I compared the reported value with the concentration measured at the monitor and regressed the residual on the tract's rank in the CDC/ATSDR Social Vulnerability Index for the same year. Final research report for Pioneer Academics' Data Science for Sustainability program, mentored by Prof. Deborah Sunter.

**Interpretation:** The shortfall is detected along poverty and education and not detected along racial composition (the confidence intervals overlap, so the axes cannot be ranked against each other), and it is accounted for statistically by concentration: vulnerable tracts sit higher in the distribution, and the surface compresses high concentrations toward the middle, consistent with regression toward the mean. Because monitor observations also inform the fused surface, this comparison may overstate performance at unmonitored locations. Screening surfaces should be evaluated on the disparity they reproduce, not on average error alone.

</details>

</div>

<div class="paper-box" id="visual-behavior" markdown="1">

<p class="project-meta">Research poster · 2025</p>

### Mapping visually evoked behavior in *Drosophila*

<p class="paper-authors"><strong>Carmen Wang</strong> · Independent research, Oregon Episcopal School</p>
<div class="paper-tags"><span class="paper-tag">Computational ethology</span><span class="paper-tag">Pose tracking</span><span class="paper-tag">GMVAE</span></div>

<div class="project-figures">
<figure>
<a href="/images/projects/5d2f7f1b2ceef661f12ad4c94b764f32.jpg" aria-label="Enlarge figure: Inverted arena: iPad Pro (120 Hz) + global-shutter CMOS, red-pass filter"><img src="/images/projects/5d2f7f1b2ceef661f12ad4c94b764f32.jpg" alt="Inverted arena: iPad Pro (120 Hz) + global-shutter CMOS, red-pass filter" loading="lazy" decoding="async"></a>
<figcaption>Inverted arena: iPad Pro (120 Hz) + global-shutter CMOS, red-pass filter</figcaption>
</figure>
<figure>
<a href="/images/projects/b0ff99af9d3b7d292ddd54676ee4dea2.png" aria-label="Enlarge figure: 5.2M frames embedded via GMVAE + UMAP: baseline vs. active stimulus"><img src="/images/projects/b0ff99af9d3b7d292ddd54676ee4dea2.png" alt="5.2M frames embedded via GMVAE + UMAP: baseline vs. active stimulus" loading="lazy" decoding="async"></a>
<figcaption>5.2M frames embedded via GMVAE + UMAP: baseline vs. active stimulus</figcaption>
</figure>
</div>

Tracking and embedding fruit-fly movement to study responses to controlled visual stimuli.

**Key finding:** Centripetal optic flow (8 Hz) + 2 Hz flicker suppresses wall-following and induces sustained center-tracking, a behavioral response that motivates further study of arousal and reward. Mutual information analysis identified flow direction and flicker as the strongest measured associations with behavior; the response persisted across a 24-hour sleep-wake cycle.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Setup:** Apterous *Drosophila* (N = 30) in PTFE-coated 6-well plates, exposed to 32 pseudo-randomized visual parameter combinations (speed 2 to 15 Hz, flicker 0 to 10 Hz, centripetal/centrifugal flow) with 20 s active / 40 s washout blocks.

**Pipeline:** UNet body-part tracker (head/thorax/abdomen) → kinematic feature extraction (velocity, spine angle, thigmotaxis index, postural jitter) → Gaussian Mixture VAE embedding into a 20-cluster behavioral atlas.

**Potential application:** A visual-stimulus library for follow-up experiments on arousal and reward.

</details>

</div>

<div class="paper-box" id="greenhouse-gases" markdown="1">

<p class="project-meta">NWSE · 2025</p>

### Modeling greenhouse gas flux with explainable AI

<p class="paper-authors"><strong>Carmen Wang</strong> · NASA Earth System Science Project Award, NWSE 2025</p>
<div class="paper-tags"><span class="paper-tag">Explainable AI</span><span class="paper-tag">SHAP</span><span class="paper-tag">Soil biogeochemistry</span></div>

<div class="project-figures">
<figure>
<a href="/images/projects/90efd38fc9eaaf495256dfbd414ba254.png" aria-label="Enlarge figure: Field sampling: chamber-syringe protocol + gas chromatography"><img src="/images/projects/90efd38fc9eaaf495256dfbd414ba254.png" alt="Field sampling: chamber-syringe protocol + gas chromatography" loading="lazy" decoding="async"></a>
<figcaption>Field sampling: chamber-syringe protocol + gas chromatography</figcaption>
</figure>
<figure>
<a href="/images/projects/4402236d7d4e8ae84c791a71a6b3f753.jpg" aria-label="Enlarge figure: SHAP waterfall: feature-level contribution to predicted CO₂ flux"><img src="/images/projects/4402236d7d4e8ae84c791a71a6b3f753.jpg" alt="SHAP waterfall: feature-level contribution to predicted CO₂ flux" loading="lazy" decoding="async"></a>
<figcaption>SHAP waterfall: feature-level contribution to predicted CO₂ flux</figcaption>
</figure>
</div>

A random forest trained on Borneo soil data, interpreted with SHAP and tested on forest and wetland sites at OES.

**Key finding:** At the campus sites the model ranked the forest and wetland correctly for all three gases and matched the forest CH₄ flux within 10%, but it under-predicted wetland CH₄ threefold and over-predicted CO₂ and N₂O. This is consistent with a limitation of tree ensembles: a model trained on soils at 23 to 25 °C cannot reliably extrapolate to 12 °C November soil. Wetland CH₄ was consistent with anaerobic methanogenesis.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Setup:** Trained on 672 open static-chamber records from a tropical forest landscape in Malaysian Borneo (SAFE project), using seven predictors (soil moisture, soil and air temperature, pH, bulk density, soil carbon, elevation) retained after Pearson screening of 17 candidates. In parallel, measured the same soil properties and CH₄, CO₂, and N₂O fluxes by gas chromatography along transects in a forest and a wetland on the OES campus, using a chamber-syringe protocol (four draws per chamber at T0, T10, T20, T30).

**Model:** Random Forest regressor interpreted with SHAP; on held-out data it explained 14% of the variance in CH₄ flux, 59% in CO₂, and 75% in N₂O. Attributions matched known biogeochemistry: moisture and compaction raised CH₄ predictions, temperature and moisture dominated CO₂, and moisture with low pH dominated N₂O, a pattern consistent with denitrification.

</details>

</div>

<div class="paper-box" id="soil-microcosms" markdown="1">

<p class="project-meta">ASE 1st Place · 2025</p>

### Oxygen availability and nitrogen cycling in soil microcosms

<p class="paper-authors"><strong>Carmen Wang</strong> · Aardvarks Science Exposition, 1st Place</p>
<div class="paper-tags"><span class="paper-tag">Soil science</span><span class="paper-tag">Gas chromatography</span><span class="paper-tag">Wet lab</span></div>

<div class="project-figures">
<figure>
<a href="/images/projects/6dc7dd7352cbbfabb19d77df8dd6b65f.png" aria-label="Enlarge figure: 4-treatment airtight microcosms with syringe gas collection and KCl extraction"><img src="/images/projects/6dc7dd7352cbbfabb19d77df8dd6b65f.png" alt="4-treatment airtight microcosms with syringe gas collection and KCl extraction" loading="lazy" decoding="async"></a>
<figcaption>4-treatment airtight microcosms with syringe gas collection and KCl extraction</figcaption>
</figure>
<figure>
<a href="/images/projects/85b8771a26094ef97ab2eeada29676d4.jpg" aria-label="Enlarge figure: Nitrification rate and denitrification efficiency across four treatments"><img src="/images/projects/85b8771a26094ef97ab2eeada29676d4.jpg" alt="Nitrification rate and denitrification efficiency across four treatments" loading="lazy" decoding="async"></a>
<figcaption>Nitrification rate and denitrification efficiency across four treatments</figcaption>
</figure>
</div>

A controlled experiment on how oxygen and ammonium availability affect nitrogen cycling.

**Key finding:** Anaerobic + NH₄Cl produced the highest denitrification efficiency (11.86%) and peak N₂O at 48 h (5.707 ppm), consistent with oxygen-dependent differences in nitrogen cycling.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Setup:** Four airtight 1 L jars (300 g soil each) across two oxygen conditions × ±NH₄Cl addition. Anaerobic jars evacuated by hand pump. Headspace gas collected via syringe at 0, 24, 48, 72 h and analyzed by gas chromatography; NH₄⁺/NO₃⁻ measured by microplate reader after 2 N KCl extraction.

</details>

</div>

### Competition and program papers
{: #papers .subsection-title}

<div class="paper-box" id="himcm-2025" markdown="1">

<p class="project-meta">HiMCM · 2025</p>

### Emergency evacuation sweeps with graph simulation and multi-agent reinforcement learning

<p class="paper-authors">Team 16980, Oregon Episcopal School · <strong>Carmen Wang</strong>, team leader and primary modeler · HiMCM 2025, Problem A</p>
<div class="paper-tags"><span class="paper-tag">Mathematical modeling</span><span class="paper-tag">Multi-agent RL</span><span class="paper-tag">Graph attention</span></div>
<p class="paper-links"><a class="paper-link" href="/files/HiMCM2025_Team16980.pdf">PDF</a></p>

<div class="project-figures">
<figure>
<a href="/images/papers/himcm2025_gat_attention.png" aria-label="Enlarge figure: Graph-attention weights over the three-floor daycare graph; thicker edges carry more attention"><img src="/images/papers/himcm2025_gat_attention.png" alt="Graph-attention weights over the three-floor daycare graph; thicker edges carry more attention" loading="lazy" decoding="async"></a>
<figcaption>Graph-attention weights over the three-floor daycare graph; thicker edges carry more attention</figcaption>
</figure>
<figure>
<a href="/images/papers/himcm2025_office_trajectory.png" aria-label="Enlarge figure: Office sweep routes for two responders from the greedy planner"><img src="/images/papers/himcm2025_office_trajectory.png" alt="Office sweep routes for two responders from the greedy planner" loading="lazy" decoding="async"></a>
<figcaption>Office sweep routes for two responders from the greedy planner</figcaption>
</figure>
</div>

How should responders sweep an office, a multi-floor daycare, and a warehouse during a fire, and how many responders does each building need?

**Approach:** We represented each building as a graph and simulated fire and smoke spread, occupant awareness, and responder exposure. A risk-weighted greedy planner produced fast, interpretable sweep orders and staffing guidance, and a multi-agent PPO policy on graph-attention embeddings was trained to adapt to stochastic hazards.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Model:** Rooms, hallways, stairwells, and exits are nodes; the sweep is a discrete-time, partially observable process with search times proportional to room area, congestion, and health-point dynamics for children, adults, and limited-mobility occupants. Rooms can require repeated sweeps before an all-clear.

**Role:** Led the team, designed the reinforcement-learning model, and resolved its training collapse with a staged-complexity curriculum.

</details>

</div>

<div class="paper-box" id="himcm-2024" markdown="1">

<p class="project-meta">HiMCM · Honorable Mention</p>

### Which sports belong at Brisbane 2032? A multi-criteria evaluation of Olympic events

<p class="paper-authors">Team 15277, Oregon Episcopal School · <strong>Carmen Wang</strong>, team leader · HiMCM 2024, Problem A · Honorable Mention</p>
<div class="paper-tags"><span class="paper-tag">Decision analysis</span><span class="paper-tag">AHP</span><span class="paper-tag">Entropy weights</span><span class="paper-tag">TOPSIS</span></div>
<p class="paper-links"><a class="paper-link" href="/files/HiMCM2024_Team15277.pdf">PDF</a></p>

<div class="project-figures">
<figure>
<a href="/images/papers/himcm2024_flowchart.png" aria-label="Enlarge figure: Model pipeline: AHP and entropy weights fused by grey relational analysis, then ranked by TOPSIS"><img src="/images/papers/himcm2024_flowchart.png" alt="Model pipeline: AHP and entropy weights fused by grey relational analysis, then ranked by TOPSIS" loading="lazy" decoding="async"></a>
<figcaption>Model pipeline: AHP and entropy weights fused by grey relational analysis, then ranked by TOPSIS</figcaption>
</figure>
<figure>
<a href="/images/papers/himcm2024_sensitivity.png" aria-label="Enlarge figure: Sensitivity analysis: event scores barely move when each weight is shifted by 5% or 10%"><img src="/images/papers/himcm2024_sensitivity.png" alt="Sensitivity analysis: event scores barely move when each weight is shifted by 5% or 10%" loading="lazy" decoding="async"></a>
<figcaption>Sensitivity analysis: event scores barely move when each weight is shifted by 5% or 10%</figcaption>
</figure>
</div>

A model to help the IOC decide which sports, disciplines, and events to add to or remove from the 2032 Summer Olympics.

**Key result:** The model ranked long-standing sports above recent additions, held up under a weight-sensitivity analysis, and identified boxing, flying disc, and Australian rules football as the strongest candidates for 2032.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Approach:** Indicators for the IOC's six criteria (popularity and accessibility, gender equity, sustainability, inclusivity, relevance and innovation, safety and fair play) were weighted twice: subjectively with the Analytic Hierarchy Process from expert judgments, and objectively with the Entropy Weight Method from data. Grey Relational Analysis fused the two weightings, and TOPSIS ranked the events. ARIMA forecasts extended the evaluation to candidates for 2036.

**Role:** Led the team. Combining expert and data-driven weights is how we settled a real disagreement about whose weights to trust.

</details>

</div>

<div class="paper-box" id="norman-sicily" markdown="1">

<p class="project-meta">MehtA+ · 2025</p>

### ML-driven insights into the geosocial dynamics of Norman Sicily

<p class="paper-authors"><strong>Carmen Wang</strong>, Nischith Srikanth, Vivian Tang, Selina Zhang · MehtA+ AI/ML Research Bootcamp, with the Norman Sicily Project (Montclair State University)</p>
<div class="paper-tags"><span class="paper-tag">Digital humanities</span><span class="paper-tag">Clustering</span><span class="paper-tag">RAG chatbot</span></div>
<p class="paper-links"><a class="paper-link" href="/files/Norman_Sicily_MehtA.pdf">PDF</a></p>

<div class="project-figures">
<figure>
<a href="/images/papers/sicily_clusters.png" aria-label="Enlarge figure: Fortifications grouped by k-means (k = 3); the circled inland region has no recorded sites"><img src="/images/papers/sicily_clusters.png" alt="Fortifications grouped by k-means (k = 3); the circled inland region has no recorded sites" loading="lazy" decoding="async"></a>
<figcaption>Fortifications grouped by k-means (k = 3); the circled inland region has no recorded sites</figcaption>
</figure>
<figure>
<a href="/images/papers/sicily_chatbot_flow.png" aria-label="Enlarge figure: Chatbot design: GPT-4o routes each question to a retrieval tool or a pandas-query tool"><img src="/images/papers/sicily_chatbot_flow.png" alt="Chatbot design: GPT-4o routes each question to a retrieval tool or a pandas-query tool" loading="lazy" decoding="async"></a>
<figcaption>Chatbot design: GPT-4o routes each question to a retrieval tool or a pandas-query tool</figcaption>
</figure>
</div>

Settlement and elevation patterns of monasteries and fortifications in Norman Sicily (c. 1061 to 1194), plus a chatbot that lets historians query the project's records.

**Key finding:** Monastery locations were strongly structured (latitude and longitude r = −0.83) and concentrated along the northeast coast, while fortifications spread across the island. An inland region with no recorded sites suggests that settlement followed rivers, roads, and the coast.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Data:** The project's records of about 200 monasteries and 150 fortifications, with condition surveys and people-to-places and places-to-places link tables, provided by Prof. Dawn Marie Hayes's team.

**Analysis:** Pearson and point-biserial correlation, one-way ANOVA, Lasso regression, and an RBF-kernel SVM with permutation importance related elevation to location and site attributes; k-means (k = 3, chosen by the elbow method) mapped settlement patterns.

**Chatbot:** GPT-4o with LangChain tool calling routes structured questions to a pandas-query tool over the link tables and general questions to a retrieval-augmented generation tool over the site records, served in Streamlit.

**Role:** Data processing, the elevation case study, the chatbot, and the paper.

</details>

</div>

<div class="paper-box" id="catalan-rhetoric" markdown="1">

<p class="project-meta">MehtA+ · 2025</p>

### Identifying rhetorical devices in 15th-century Spanish and Catalan literature

<p class="paper-authors">Selina Z., <strong>Carmen Wang</strong>, Haripriya T., Kathleen L. · MehtA+ AI/ML Research Bootcamp</p>
<div class="paper-tags"><span class="paper-tag">NLP</span><span class="paper-tag">BERT</span><span class="paper-tag">Few-shot LLMs</span><span class="paper-tag">Low-resource text</span></div>
<p class="paper-links"><a class="paper-link" href="/files/Rhetorical_Devices_Spanish_Catalan_MehtA.pdf">PDF</a></p>

<div class="project-figures">
<figure>
<a href="/images/papers/catalan_pathos_prompt.png" aria-label="Enlarge figure: Few-shot prompt used to find pathos in 15th-century Spanish and Catalan text"><img src="/images/papers/catalan_pathos_prompt.png" alt="Few-shot prompt used to find pathos in 15th-century Spanish and Catalan text" loading="lazy" decoding="async"></a>
<figcaption>Few-shot prompt used to find pathos in 15th-century Spanish and Catalan text</figcaption>
</figure>
<figure>
<a href="/images/papers/catalan_metaphor_scores.png" aria-label="Enlarge figure: Metaphor classifier: precision, recall, and F1 by class on the 13-sentence test set"><img src="/images/papers/catalan_metaphor_scores.png" alt="Metaphor classifier: precision, recall, and F1 by class on the 13-sentence test set" loading="lazy" decoding="async"></a>
<figcaption>Metaphor classifier: precision, recall, and F1 by class on the 13-sentence test set</figcaption>
</figure>
</div>

Can machine learning find metaphor, anaphora, pathos, and parallelism in partially annotated texts by three 15th-century Iberian women writers?

**Key finding:** With only 9 to 13 labeled examples for some devices, few-shot prompting of an LLM proved more practical than fine-tuning, and every output still needed human checking. A fine-tuned Spanish BERT reached 84.6% accuracy for metaphor, but on a test set of only 13 sentences.

<details class="project-details" markdown="1">
<summary>Methods and context</summary>

**Approach:** Metaphor used a fine-tuned Spanish BERT (BETO) with LLM-generated examples to balance the classes; anaphora used synthetic training examples; pathos used few-shot prompting of Gemini 1.5 Flash, which recovered all five held-out examples with one false positive; parallelism used part-of-speech n-grams.

**Limits:** Castilian and Catalan of this period differ enough from modern Spanish that standard tokenizers and taggers struggled, and the tiny labeled sets make every accuracy figure fragile.

</details>

</div>


<span class="legacy-anchor" id="-research-experience" aria-hidden="true"></span>
## Research experience
{: #experience .section-title}

<div class="experience-list">
<article class="experience-entry">
  <p class="entry-date">Sep 2026 to present</p>
  <div>
    <h3>Mao Lab, Oregon Health &amp; Science University</h3>
    <p class="entry-role">Neuroscience Research Volunteer</p>
    <p>Annotating cells in 3D microscopy volumes in napari, reviewing trial annotations with the lab's imaging lead, and resolving ambiguous cases. The labels serve as ground truth for segmentation models.</p>
  </div>
</article>
<article class="experience-entry">
  <p class="entry-date">May to Sep 2026</p>
  <div>
    <h3>Simões Lab, Reed College</h3>
    <p class="entry-role">Research Assistant</p>
    <p>Built and validated a sex-scoring pipeline for group-housed <em>Drosophila</em> and packaged it for routine lab use. In residence in August 2026.</p>
  </div>
</article>
<article class="experience-entry">
  <p class="entry-date">Summer 2026</p>
  <div>
    <h3>Pioneer Academics</h3>
    <p class="entry-role">Student Researcher · Data Science for Sustainability</p>
    <p>Audited EJScreen's PM₂.₅ estimates with Prof. Deborah Sunter. Wrote a final research report with a reproducible supplement and presented it in the program's final session.</p>
  </div>
</article>
</div>

<span class="legacy-anchor" id="-honors--awards" aria-hidden="true"></span>
## Honors & awards
{: #honors .section-title}

<ul class="dated-list awards-list">
  <li><span class="entry-date">Apr 2026</span><div>Purple Comet Math Meet · <strong>1st Place, Oregon State</strong></div></li>
  <li><span class="entry-date">2026</span><div>Northwest Science Expo, Animal Science · <strong>3rd Place</strong></div></li>
  <li><span class="entry-date">2026</span><div>Aardvarks Science Exposition, Animal Science · <strong>1st Place</strong></div></li>
  <li><span class="entry-date">2025, 2026</span><div><strong>AIME Qualifier</strong></div></li>
  <li><span class="entry-date">May 2025</span><div><strong>NASA Earth System Science Project Award</strong> · NWSE</div></li>
  <li><span class="entry-date">Mar 2025</span><div>ASE Environmental Science · <strong>1st Place</strong></div></li>
  <li><span class="entry-date">Nov 2024</span><div>HiMCM · Honorable Mention</div></li>
  <li><span class="entry-date">Nov 2024</span><div>AMC 12: 118.5 (top 5%) · AMC 12B: 94.5</div></li>
</ul>

<span class="legacy-anchor" id="-skills" aria-hidden="true"></span>
## Skills
{: #skills .section-title}

<dl class="skills-grid">
  <div><dt>Programming</dt><dd>Python · R · MATLAB · Java · LaTeX</dd></div>
  <div><dt>ML &amp; data</dt><dd>PyTorch · scikit-learn · SHAP · UMAP</dd></div>
  <div><dt>Imaging &amp; behavior</dt><dd>napari · SLEAP · FlyTracker</dd></div>
  <div><dt>Wet lab</dt><dd>Gas chromatography · Microplate reader · KCl extraction</dd></div>
</dl>

<span class="legacy-anchor" id="-education" aria-hidden="true"></span>
## Education
{: #education .section-title}

<div class="school-entry">
  <h3>Oregon Episcopal School</h3>
  <p>High school senior · Portland, Oregon</p>
</div>

### Additional coursework
{: .coursework-heading}

<ul class="dated-list">
  <li><span class="entry-date">Jun to Aug 2025</span><div>MehtA+ AI/ML Research Bootcamp</div></li>
  <li><span class="entry-date">Apr to Jul 2025</span><div>Deep Learning Specialization · Andrew Ng, Coursera</div></li>
  <li><span class="entry-date">May to Jul 2025</span><div>Linear Algebra · Gilbert Strang, MIT OpenCourseWare</div></li>
</ul>
