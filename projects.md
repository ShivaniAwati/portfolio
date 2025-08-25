---
layout: single
title: "Projects"
permalink: /projects/
toc: false
toc_sticky: true
classes: wide
---

## Topic Modeling for Research Articles (UTA)
**Timeline:** October 2024 – December 2024  

![Topic Modeling Overview]({{ site.baseurl }}/assets/img/proj-topic-modeling.png)

Designed NLP pipelines to extract themes from cybersecurity/privacy papers and mapped co-authorship networks to highlight influential authors.

### Conclusion / Impact
- Extracted coherent themes from cybersecurity/privacy literature and surfaced recurring topics.
- Mapped co-authorship networks, identifying influential authors and collaboration clusters (domain leaders).

### Key Challenges
- **Choosing k (topics):** Balancing interpretability vs. granularity, avoiding redundant/overlapping topics.
- **Domain vocabulary:** Acronyms/jargon and fast-evolving terminology.

### Techniques Used
- **Topic models:** LDA, LSI, NMF, and transformer-based pipelines (BERT, BUNKA).
- **Network analysis:** Co-authorship graph construction, degree/betweenness centrality, and visualization (VOSviewer).

### What else could be done
- **LLM-assisted labeling:** Use an LLM to propose human-readable topic labels and summaries; validate with SMEs.

**Code/Demo:**<https://github.com/ShivaniAwati/topic-modeling-research-articles>

---

## Predicting Drug Ratings (UTA)
**Timeline:** May 2024 – July 2024  

![Topic Modeling Overview]({{ site.baseurl }}/assets/img/proj-drug-ratings.png)

Built supervised models on review metadata (and optional review text) to predict user-provided drug ratings.

### Conclusion / Impact
- Produced a model that reliably predicts drug ratings from available features, outperforming majority and linear baselines.
- Model interpretation surfaced which inputs matter most (e.g., review language signals, condition/medicine metadata), guiding future data collection and UX.

### Key Challenges
- **Ordinal target:** Ratings are ordered (1–10). Plain multiclass ignores distance (predicting “9” when truth is “8” is better than predicting “3”).
- **Class imbalance:** Fewer extreme ratings vs. many mid-range scores; needed class-aware validation and weighting.

### Techniques Used
- **Problem framings:**
  - Multiclass classification (softmax) with class weights.
  - Regression on the 1–10 scale to preserve ordinality; compared against ordinal classification (cumulative link / thresholded regressors).
- **Models:** Decision Trees, Random Forests, Gradient Boosting; tuned via grid/random search.
- **Validation:** Stratified k-fold CV; metrics included macro F1 / accuracy (classification) and MAE/RMSE (regression).
- **Preprocessing:** Missing-value handling, categorical encoding (one-hot/target), feature scaling for regressors.

### What else could be done
- **Richer text signals:** Replace TF-IDF with sentence embeddings (SBERT/BERT) + a shallow classifier; compare to LightGBM + embeddings.
- **Explainability:** SHAP for global/local explanations.

**Code:** <https://github.com/ShivaniAwati/drug-rating>


---

## Resume Scorer & Skill Gap (AWS)
**Timeline:** May 2025 – July 2025  

![Topic Modeling Overview]({{ site.baseurl }}/assets/img/proj-aws-resume-scorer.png)

**Stack:** AWS S3, Glue (Spark), Lambda, API Gateway, QuickSight • Python • React

**Summary:** Scores a resume against a job description and highlights missing keywords/skills. Built an end-to-end serverless pipeline with scalable preprocessing and a lightweight UI for submissions.

### Conclusion / Impact
- Delivered a repeatable screening tool that flags **missing/weak skills** and assigns a **match score**, cutting manual review time.
- Enabled faster recruiter feedback loops with **structured logs** and error categories for quick triage and handover.
- Provided **self-serve dashboards** (QuickSight) for aggregate insights (most-missing skills by role, pass-rate by team).

### Key Challenges
- **Text variability:** noisy PDFs/Docx; synonyms (“PL/SQL” vs “PLSQL”), abbreviations, and domain phrasing.
- **Quality vs. false positives:** avoiding keyword stuffing; weighing context (e.g., projects vs. skills list).
- **Latency & scale:** keeping request <1–2s per resume while handling bursts.


### Techniques Used
- **Preprocessing/ETL (Glue + Spark):** document text extraction, lower-casing/lemmatization, custom stopwords, PII scrubbing; curated skill dictionaries by role.
- **Scoring approaches:**
  - **TF-IDF overlap** for explicit keywords (weighted by section).
  - **Sentence embeddings** (e.g., SBERT via Lambda layer) for semantic similarity between resume & JD.
  - **Composite score** = α·(keyword coverage) + β·(semantic similarity) with thresholding.
- **Gap analysis:** c-TF-IDF per role taxonomy to surface **missing skills** and **weak evidence** (low frequency / thin context).
- **API & UI:** **Lambda** (Python) behind **API Gateway**; simple **React** form to upload resume + JD and display score & gaps.
- **Ops & reliability:** JSON **structured logging** to **CloudWatch**, DLQ via **SQS** for failures, retries with backoff, request size/type validation.
- **Reporting:** **QuickSight** dashboards over S3/Athena for team-level trends.

### What else could be done
- **Model uplift:** swap TF-IDF for modern **domain embeddings** (e5/SBERT) + reranking; try **KeyBERT** or **NER** for more precise skill extraction.
- **Anti-gaming signals:** detect keyword stuffing (density + entropy), require multi-sentence evidence.
- **Evaluator set:** labeled pairs (resume, JD, match) to compute **precision/recall** and tune thresholds; track drift over time.
- **Cost/latency:** batch pre-compute embeddings in Glue; cache JD vectors; use Lambda provisioned concurrency for bursts.

**Code/Demo:** <http://shivani-website-bucket-s3.s3-website.us-east-2.amazonaws.com/>

