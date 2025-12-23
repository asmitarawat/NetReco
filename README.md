## 🎬 NetReco — Time-Aware Netflix Recommendation System

A data-driven, explainable recommendation system that balances user taste with content freshness using real Netflix metadata.

### **Project Overview**

Most Netflix analysis projects stop at visualizations.

#### **NetReco goes further.**

This project combines:

-Deep **Exploratory Data Analysis (EDA)**

-Robust **feature engineering**

-A **time-aware recommendation engine**

#### **to recommend Netflix titles based on:**

-User-selected genres

-Recency of content addition

The result is a recommender that feels **relevant, fresh, and personalized.**

### **Why This Project Matters**

**Traditional recommenders:**

Ignore time → recommend outdated content

Are black boxes → hard to explain

**NetReco solves both:**

-Time-aware ranking

-Fully explainable scoring logic

This mirrors real-world recommender systems used by Netflix, Spotify, and YouTube.

### 📊 Dataset

**Source:** Netflix Movies & TV Shows Dataset
**Size:** 8,800+ titles

#### **Key Columns Used:**

-type (Movie / TV Show)

-listed_in (Genres)

-date_added

-duration

-country

-release_year

### **🔍 Phase 1 — Exploratory Data Analysis (EDA)**

**Performed in *01_NetflixDataAnalysis.ipynb***

#### **Key Analyses:**

-Movies vs TV Shows distribution

-Top 10 countries with most content

-Content addition trends over years

-Genre popularity analysis

-Movie duration & TV season patterns

-Actor & director network analysis

**Goal:** Understand Netflix’s content strategy before modeling.

### **🛠 Phase 2 — Feature Engineering**

Engineered meaningful features for modeling:

**Feature**                            	    **Description**

movie_duration	      -                 Duration in minutes (movies only)

tv_seasons	          -                  Number of seasons (TV shows only)

num_genres	          -                 Count of genres per title
 
num_countries   	    -                   Count of production countries

content_age	          -                 Years since content was added

These features power the recommendation logic.

### **🤖 Phase 3 — Time-Aware Recommendation System**

**Implemented in** *02_NetReco_Recommendation.ipynb*

**Step 1: Genre Matching**

User selects preferred genres

Titles scored based on genre overlap

**Step 2: Freshness Scoring**

Recent titles boosted

Older content gradually penalized

*freshness_score = max(0, 1 - content_age / threshold)*

**Step 3: Final Ranking**

Weighted scoring:

*final_score = 0.7 * genre_score + 0.3 * freshness_score*


--Balances **relevance** and **recency.**

### **🎯 Sample Recommendation Output**   
**Title	         -->          Genres	       -->       Content Age 	   -->       Final Score**

Sintonia	   -->         Crime, TV Drama	       -->        0	         -->             1.00

Freud   	   -->          Crime, Mystery	       -->        0	         -->             1.00

Young Wallander	    -->    Crime, Drama	       -->          0	         -->           1.00

### **What Makes NetReco Unique?**

✅ Time-aware recommendations

✅ User-controlled personalization

✅ Explainable scoring

✅ Modular pipeline (EDA → Features → Reco)

✅ Recruiter-ready logic


### **Future Enhancements**

-TF-IDF + cosine similarity recommender,

-Hybrid ML-based ranking,

-Diversity & novelty constraints,

-User watch-history simulation

### **Tech Stack**
-Python

-Pandas, NumPy

-Matplotlib, Seaborn

-Jupyter Notebook

### **How to Run**

-Clone the repo

-Run 01_NetflixDataAnalysis.ipynb

-Run 02_NetReco_Recommendation.ipynb

-Select genres → Get recommendations

### **Final Note**

#### **This project demonstrates end-to-end data science thinking:**
**from raw data → insights → production-style recommendation logic.**
