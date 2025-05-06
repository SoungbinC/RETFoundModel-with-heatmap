# RETFoundModel-with-heatmap
**🗓️ 2025-05-04 — Progress Log**
What I did:

- Fine-tuned RETFound_mae on 4-class eye disease dataset (93.96% accuracy).

- Evaluated predictions and analyzed false cases.

- Integrated ViT-LRP for heatmap-based interpretability.

- Quantified central attention ratios across diseases.

- Identified low focus on lens center in some cataract cases.

Next steps:

- Improve heatmap clarity and focus on pathological regions.

- Add bounding boxes to highlight optic disc/lens zone.

- Explore guided loss or attention regularization.

- Run heatmap drift comparison across image quality & diseases.



**🗓️ 2025-05–05 — Progress Log**

### ✅ What I worked on:
- Successfully fine-tuned the `RETFound_mae` foundation model on a 4-class eye disease dataset (Normal, Cataract, DR, Glaucoma), achieving **~93.96% validation accuracy**.
- Explored **false positives and false negatives**, especially in cataract misclassifications.
- Integrated **ViT-LRP (Layer-wise Relevance Propagation)** to generate **heatmaps** showing model attention.
- Quantified **central attention scores** (center/left/right zones) across predictions to analyze focus drift.
- Found that **some correct predictions had low central attention**, suggesting possible reliance on artifacts or peripheral features.
- Implemented **zone-wise attention scoring** to prepare for interpretability comparison.

### 🔭 Next steps:
- Improve **heatmap resolution and overlay clarity** for better clinical insight.
- Add **bounding boxes** to mark optic disc or lens regions to validate attention placement.
- Experiment with **attention regularization** or **guided loss** to enforce focus on pathological zones.
- Visualize and compare **attention drift** across:
  - Correct vs incorrect predictions
  - Disease types (e.g., Cataract vs DR vs Glaucoma)
  - Image quality (blur, glare, off-center)

---

### 🧠 Project Vision
The goal of this project is to **fine-tune a foundation model (RETFound)** for retinal disease classification **with transparent, explainable predictions** using heatmap visualizations. By analyzing attention maps, we aim to ensure the model isn't just accurate, but **clinically reliable** and focused on **anatomically meaningful regions**.


# 🧠 Big Picture

You're building an **interpretable retinal disease classification system** using a **ViT-based foundation model (RETFound-MAE)** and **Layer-wise Relevance Propagation (LRP)** to:

- 🩺 Classify retinal images into diseases like **cataract**, **glaucoma**, **diabetic retinopathy**, etc.
- 🔍 Visualize model attention using **heatmaps (LRP)** to understand and validate predictions.
- 📊 Quantify model focus across **image zones** (center, left, right).
- 🧪 Prepare for better generalization by identifying **shortcut learning** and planning **regularization** strategies.

---

# ✅ What You’ve Done Today (2025-05-05)

### 1. 🚀 Model Fine-Tuning
- Loaded and fine-tuned the **RETFound-MAE** model.
- Split dataset into **left-eye and right-eye** subsets for targeted training.
- Achieved **stable training and validation accuracy**.
- Saved fine-tuned model weights for reproducibility.

### 2. 🔎 Evaluation + Heatmap Analysis
- Ran predictions on test/validation set and saved detailed **CSV with prediction confidence**.
- Used **ViT-LRP** to generate heatmaps and overlay them on retina images.
- Computed **zone-wise attention scores** (center, left, right).
- Created visual side-by-side comparisons for:
  - ✅ True Positives (TP)
  - ❌ False Negatives (FN)
  - ⚠️ False Positives (FP)

### 3. 📉 Statistical Insights
- Plotted **center score vs confidence** — found **low or no correlation**.
- Compared **correct vs incorrect predictions** based on attention zones.
- Observed attention drift in some cases — model may be focusing on **irrelevant features** (e.g., reflections or periphery).

---

# 🔜 What You Plan to Do Next

### 🎯 Add Attention Regularization
- Introduce a lightweight **center-focused loss** to guide attention maps.
- Encourage model to focus more on **optic disc or lens region**.

### 🔬 Improve Interpretability
- Visualize more **heatmaps across classes and image zones**.
- Annotate optic disc/macula areas for possible **attention supervision**.

### 🧪 Better Data Handling
- Further refine **left/right splits** and consider grouping by image **brightness or quality**.

### 🧰 Train Evaluation Toolkit
- Automate saving of:
  - **Zone attention stats**
  - **Confusion matrix**
  - **Visual summaries** per class

### 📈 Prepare for Reporting
- Finalize **key visual examples** and metrics.
- Organize results for **presentation or publication**.
