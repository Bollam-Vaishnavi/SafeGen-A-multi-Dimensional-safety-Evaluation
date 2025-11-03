# SafeGen Dataset Preparation 
This repository contains the initial phase
## Overview 
The code performs the following steps:
1. **Synthetic Misinformation Dataset Generation**
   - Generates 350 plausible but factually incorrect claims across diverse topics (health, science, history, technology).
   - Each claim includes:
      - The false statement
      - A '"false"' label
      - A factual correction

  - The dataset is converted into a pandas Dataframe and saved as a CSV file.
2. **Loading External Datasets**
    - Four additional datasets are loaded for safety evaluation:
    - **Real-Toxicity-Prompts**- for toxic content detection
    - **TruthfulQA** - for truthful question-answering
    - **CROWS-Pairs**- for bias and stereotyping assessment
    - **Synthetic misinformation Dataset**- newly created
  - All datasets are standardized into pandas dataframes and initially inspected using '.info()' and '.head()'.
3. **Data Cleaning and preprocessing**
    - Duplicate entries are identified and removed (27 duplicates found in the misinformation dataset).
    - Irrelevant or nested columns are dropped or extracted (e.g., extracting text from dictionary fields in toxicity prompts).
    - A robust 'clean_text' function is applied to all datasets to:
    - Nomalize Unicode
    - Strip HTML
    - Convert text to lowercase
    - Remove punctuation, emojis, and excess whitespace
  - This ensures clean, analysis-ready text across all datasets.
4. **Dataset Harmonization**
    - To enable balanced multi-dimensional evaluation, all datasets are sampled size of **294 records each**, except the misinformation dataset (kept complete after deduplication)
    - The result is **four hermonized, cleaned, and balanced datsets** ready for downstream safety benchmarking in detecting:
       - Misinformation
       - Toxicity
       - Bias
       - Untruthfulness in AI responses
## Usage
This prepared dataset serves as a foundation for AI safety evaluation tasks, allowing consistent, multi-dimensional testing across different types of harmfulor misleading content.
The resulting datasets form a robust foundation for **multi-aspect AI safety testing** and **content integrity evaluation**.
  - 
