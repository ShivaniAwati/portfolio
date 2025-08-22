---
layout: single
title: "Projects"
permalink: /projects/
toc: true
toc_sticky: true
---

## Topic Modeling on Cybersecurity & Privacy
**Stack:** Python, SBERT, UMAP, HDBSCAN, c-TF-IDF, NetworkX/Gephi  
**Summary:** Built a transformer-based topic discovery pipeline for ~1,000 research papers.  
- **Pipeline:** SBERT embeddings → UMAP (n_neighbors=15, metric='cosine') → HDBSCAN (min_cluster_size=10) → c-TF-IDF topic labeling.  
- **Quality:** silhouette ≈ **0.68**, coherence ≈ **0.74**; human-in-the-loop review for topic names.  
- **Deliverables:** interactive topic cards, author network (betweenness centrality), and a summary report adopted by other cohorts.  
**Code/Demo:** *link to repo or notebook*

---

## Predicting Drug Ratings (UTA)
**Stack:** Python (scikit-learn), Pandas, SHAP, Matplotlib  
**Goal:** Predict user-reported drug ratings from review metadata.  
- Built baselines and tuned tree models; compared RMSE/MAE vs simple heuristics.  
- Feature importance highlighted review language and key metadata as strong predictors.  
- Produced a concise report and plots to explain drivers and residual patterns.  
**Code/Demo:** *link to repo or notebook*

---

## HCM Weekly Hours Automation
**Stack:** Oracle Cloud HCM, Oracle SQL/PLSQL, OIC integrations  
**Outcome:** Weekly report of employees with hours > 0, filtered by emp_type; automated delivery.  
- Created HCM Extract with targeted SQL (bind week range), packaged in an integration flow.  
- Standardized filters reduced confusion (previously all employees every week).  
- **Impact:** cut manual triage time by ~**80%** for the client’s ops team.  
**Notes:** *link to design doc or sample output*

---

## Resume Screening & Keyword Gap Analyzer (AWS)
**Stack:** AWS S3, Glue (Spark), Lambda + API Gateway, QuickSight; Python  
**Summary:** End-to-end pipeline comparing resumes to JDs; highlighted missing skills and scores.  
- Serverless inference with structured logging and error categories.  
- Simple React UI for upload and results.  
**Code/Demo:** *link to repo or screenshots*

---

## Explainable Readmission Risk (XAI)
**Stack:** Python, scikit-learn, Alibi, DiCE-ML  
**Summary:** Prediction pipeline with anchors and counterfactuals for clinician review; produced HTML/CSV explanation bundles.  
**Code/Demo:** *link*

---

### Contact
- **Resume:** [/assets/Shivani_Awati_Resume.pdf](/assets/Shivani_Awati_Resume.pdf)  
- **LinkedIn:** <https://linkedin.com/in/YOUR-HANDLE>  
- **GitHub:** <https://github.com/shivaniawati>
