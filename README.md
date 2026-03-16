
# Amazon ML Challenge 2025: Smart Product Pricing Solution

## 🚀 Team: ReLU Rebels
**Rank:** ~3,200 (Top 4% of 80,000+ participants)  
**Final Metric:** 54.09% SMAPE

---

## 1. Executive Summary
Predicting product prices isn't just about numbers—it's about understanding value. A luxury watch looks different from a budget one, and the description matters just as much as the image. 

We built a **Multimodal AI solution** that perceives products like a human expert. By combining visual features (via CLIP) and textual semantics (via SentenceTransformers) with a gradient-boosted decision engine (XGBoost), we captured the nuanced factors that drive e-commerce pricing.

---

## 2. Methodology Overview

### 🧠 Problem Analysis
How do humans price products? We look at the image for quality cues and read the description for technical specs. Our discovery:
* **Visual Cues:** Sleek imagery suggests premium positioning.
* **Textual Context:** Descriptions reveal materials and brand power.
* **The Synergy:** Combining "eyes" (Vision) and "reading" (NLP) is essential; a single-modality approach misses half the story.

### 💡 Solution Strategy
We implemented a **Multimodal Learning** pipeline. We are among the first to fuse CLIP’s visual embeddings with SentenceTransformer’s contextual embeddings specifically for the task of product price regression.

---

## 3. Model Architecture

Our architecture mimics a three-step human evaluation process:

1.  **The Text Expert (SentenceTransformer):** * **Model:** `all-MiniLM-L6-v2`
    * **Output:** 384-dimensional "fingerprints" capturing material, brand, and intent.
2.  **The Image Expert (CLIP):** * **Model:** `OpenAI CLIP ViT-Base-Patch32`
    * **Output:** 512-dimensional vectors representing visual style and perceived quality.
3.  **The Decision Maker (XGBoost):** * **Input:** A concatenated 896-feature vector.
    * **Logic:** Learns complex non-linear relationships between visual/textual features and the final price.

---

## 4. Model Performance

### 📊 Validation Results
* **Metric:** 54.09% SMAPE
* **Interpretation:** While pricing is highly subjective (affected by market trends and seasonality), our model successfully captured the core value indicators of the catalog.

**Hyperparameters:**
* **Trees:** 500
* **Learning Rate:** 0.05
* **Max Depth:** 6
* **Feature Split:** 80% Training / 20% Validation

---

## 5. Conclusion & Future Scope

### What We Achieved
* Proved that **Multimodal Fusion** is superior to text-only pricing models.
* Successfully handled a high-scale dataset within strict parameter constraints.

### The Roadmap (What's Next?)
* **Dynamic Context:** Incorporating real-time market trends or brand sentiment.
* **Hyperparameter Tuning:** Utilizing Optuna for more granular XGBoost optimization.
* **Ensembling:** Combining XGBoost with a deep learning MLP head for better feature interaction.

---

## 🛠️ Tech Stack
* **Languages:** Python
* **Vision:** OpenAI CLIP
* **NLP:** Sentence-Transformers (HuggingFace)
* **ML:** XGBoost, Scikit-learn
* **Data:** Pandas, NumPy

---



---
*Disclaimer: This project was developed for the Amazon ML Challenge 2025. All data provided is proprietary to Amazon.*
