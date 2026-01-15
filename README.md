# AI/ML Salary Prediction & Career Advisor

**UC Berkeley AI/ML Certification Capstone Project**  
**Author: Sumanth Borra**  
**Date: January 2026**  
**Last Updated: January 11, 2026**

## Project Overview

This project analyzes the global AI/ML job market to predict realistic salary ranges and provide career advice based on professional attributes such as experience level, job title, location, remote work ratio, company size, and (when available) required skills extracted from job descriptions.

### Core Objectives
- Move from simple metadata-based salary lookup → enriched, skill-aware probabilistic predictions
- Provide uncertainty-aware outputs (p20/p50/p80 salary bounds, probability of exceeding 300K+)
- Incorporate location as a key input for personalized salary expectations
- Demonstrate clear improvement when adding NLP-derived features (text embeddings & skills)

### Key Phases
1. Data collection & preparation (merging multiple Kaggle sources)
2. Exploratory Data Analysis (EDA)
3. Baseline modeling (metadata only)
4. Enhanced modeling (skills + text embeddings)
5. Quantile regression for interval predictions
6. Interpretability (SHAP values)
7. Interactive prototype (Streamlit/Gradio demo)

## Datasets Used

I combine four complementary Kaggle datasets (total ~180k records after cleaning & deduplication):

| Dataset Slug | Size | Main Purpose | Key Features | License |
|--------------|------|--------------|--------------|---------|
| `adilshamim8/salaries-for-data-science-jobs` | ~151k | Core metadata & salary baseline | experience_level, job_title, salary_in_usd, employee_residence, company_location, remote_ratio, company_size | DbCL-1.0 |
| `asaniczka/data-science-job-postings-and-skills` | ~12k | Job postings + skills enrichment | job_title, company, job_location, (skills & summaries via companion files) | ODC-By |
| `kanchana1990/ai-and-ml-job-listings-usa` | ~862 | Full job descriptions (USA focus) | title, location (city/state), description | ODC-By |
| `bismasajjad/global-ai-job-market-and-salary-trends-2025` | 15k | Recent 2025 trends + explicit skills | salary_usd, required_skills (list), company_location, employee_residence | CC0-1.0 |

Note: All data is publicly available on Kaggle. No private or scraped data is used.

## Project Structure
AI-ML-salary-predictor-capstone-repo/
├── AI/ML Salary Predictor.ipynb              
├── README.md                       
├── requirements.txt                
├── images/                         
└── .gitignore                      


## How to Run the Project

### Prerequisites
- Google Colab (recommended) or local Jupyter environment
- Kaggle account (free)

### Step-by-Step Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/AI-ML-salary-predictor-capstone-repo.git
   cd AI-ML-salary-predictor-capstone-repo
2. Open setup_kaggle_auth.ipynb in Google Colab
3. Set up Kaggle authentication (very important – never commit credentials!)
- In Colab left sidebar → click the key icon (Secrets)
- Add new secret:
- Name: KAGGLE_API_TOKEN
- Value: Paste the entire content of your kaggle.json file (including {} and quotes)
- Run the cells in setup_kaggle_auth.ipynb to download and unzip the datasets

4. pen main_project.ipynb in Colab
- Run cells sequentially
- All data loading assumes datasets are in the folder structure created by the setup notebook
