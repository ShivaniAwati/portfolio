---
layout: single
title: "Projects"
permalink: /projects/
toc: true
toc_sticky: true
---

## Topic Modeling on Cybersecurity & Privacy
**Stack:** Python, SBERT, UMAP, HDBSCAN, c-TF-IDF, NetworkX/Gephi  
**Summary:** Transformer-based topic discovery for ~1,000 papers.  
- SBERT embeddings → UMAP (n_neighbors=15, metric='cosine') → HDBSCAN (min_cluster_size=10) → c-TF-IDF.  
- Silhouette ≈ **0.68**, coherence ≈ **0.74**; author network (betweenness centrality).  
**Code/Demo:** *add link*

---

## Predicting Drug Ratings (UTA)
**Timeline:** May 2024 – July 2024  

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

**Code/Demo:** *add your repo or notebook link here*


---

## HCM Weekly Hours Automation
**Stack:** Oracle Cloud HCM, Oracle SQL/PLSQL, OIC  
- Targeted HCM Extract + integration; automated weekly delivery.  
- **Impact:** reduced manual triage ~**80%**.  
**Notes:** *add link*

---

## Resume Scorer & Skill Gap (AWS)
**Timeline:** May 2025 – July 2025  
**Stack:** AWS S3, Glue (Spark), Lambda, API Gateway, QuickSight • Python  
**Summary:** Scores a resume against a job description and highlights missing keywords/skills.  
- Built an end-to-end pipeline using **S3** ingestion and preprocessing in **Glue (Spark)**.  
- Exposed inference via **Lambda + API Gateway**; simple React UI for submitting resumes & JDs and viewing results.  
- Added **structured logging** and error categorization to speed up debugging and handover.  
**Code/Demo:** *add your repo or demo link*
