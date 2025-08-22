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
**Stack:** Python (scikit-learn), Pandas, SHAP  
- Baselines vs. tuned tree models; feature importance explains drivers.  
**Code/Demo:** *add link*

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
