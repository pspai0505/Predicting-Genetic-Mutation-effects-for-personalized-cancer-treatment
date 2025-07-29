
---

# 🧬 Classifying Cancer-Driving Mutations with Machine Learning

This repository contains the code, methodology, and analysis for the project **"Classifying Cancer-Driving Mutations with Machine Learning: A Personalized Medicine Approach"**.

## 📌 Project Overview

Traditional cancer treatment often applies the same therapy to all patients with a particular type of cancer. However, not all tumors are biologically identical. **Personalized medicine** seeks to tailor treatment based on specific genetic mutations driving each individual’s tumor.

This project leverages AI to automate the **classification of cancer-driving genetic mutations** using clinical evidence, helping support targeted therapies and personalized cancer treatment.

---

## 🧠 Why AI for Mutation Classification?

* A single tumor can have **thousands of genetic mutations**.
* Manual classification is **slow** and requires **expert clinical knowledge**.
* AI models can help **scale mutation interpretation** by learning patterns from clinical literature and mutation metadata.

---

## 📂 Dataset

**Source:** [Memorial Sloan Kettering Cancer Center (MSKCC)](https://www.kaggle.com/competitions/msk-redefining-cancer-treatment/overview)

* `variants.csv`: Genetic mutation metadata

  * Columns: `ID`, `Gene`, `Variation`, `Class` (1–9)
* `text.csv`: Associated clinical literature

  * Columns: `ID`, `Text`
* Both files are joined using the `ID` column.
<img width="1088" height="665" alt="image" src="https://github.com/user-attachments/assets/0df85e98-8231-432c-823a-95a2ebdd9267" />

---

## 🧪 Methodology

The methodology involved:

1. **Preprocessing clinical text and mutation features**
2. **Feature extraction**

   * TF-IDF
   * BioBERT embeddings
3. **Handling class imbalance**

   * SMOTE
   * Class weighting
   * Focal Loss
4. **Model training**

   * XGBoost, LSTM, LightGBM, Ensemble models etc.
5. **Evaluation**

   * Accuracy and class-specific performance
<img width="1176" height="392" alt="image" src="https://github.com/user-attachments/assets/97cc74f6-9e65-4402-ab48-c7d582ba3c0f" />
<img width="1179" height="440" alt="image" src="https://github.com/user-attachments/assets/27d6b683-5447-40f8-a8ed-92352e0e9b9a" />

---

## 📊 Observations

* Model performance was biased toward dominant classes (1, 4, 7).
* Class 8 had only 19 samples, limiting the effectiveness of SMOTE and Focal Loss.
* TF-IDF lacked semantic understanding; BioBERT offered context but was too generic without fine-tuning.

---

## 🔬 Future Improvements (In Progress)

* Use **expert-generated synthetic data** instead of SMOTE.
* **Fine-tune BioBERT** on cancer-specific literature.
* Enrich features using **biological knowledge bases** (e.g., gene-gene interaction).
* Improve clinical text preprocessing to retain biological relevance.

---

## 📚 References

* [MSKCC Dataset](https://datacatalog.mskcc.org/)
* [Kaggle Competition](https://www.kaggle.com/competitions/msk-redefining-cancer-treatment/overview)
* [Oncotarget 2023 Article](https://www.oncotarget.org/2023/09/07/predicting-functions-of-cancer-associated-genetic-variants/)
* [PubMed Central Reference](https://pmc.ncbi.nlm.nih.gov/articles/PMC6030626/)
* [PNAS Article](https://www.pnas.org/doi/10.1073/pnas.1010978107)

---


