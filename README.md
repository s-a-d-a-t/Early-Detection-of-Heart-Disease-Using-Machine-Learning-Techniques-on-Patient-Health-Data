# 🫀 Early Detection of Heart Disease Using Machine Learning

<div align="center">

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.4-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![LaTeX](https://img.shields.io/badge/LaTeX-Proposal-008080?style=for-the-badge&logo=latex&logoColor=white)
![License](https://img.shields.io/badge/License-Academic-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow?style=for-the-badge)

**A Predictive Framework for Resource-Limited Healthcare Settings**

*Hawassa University · Institute of Technology · Computer Science Department*
*Research Methods in Computer Science (CoSc3101) · Year III, Semester II · 2026*

</div>

---

## 📋 Abstract

Early detection of heart disease is critical for improving patient outcomes and
reducing healthcare costs, especially in low-resource settings. This research
proposes a machine learning framework that uses patient health data to detect
heart disease at an early stage. The study utilises the **Combined Heart Disease
Dataset** from the UCI Machine Learning Repository — integrating records from
Cleveland, Hungary, Switzerland, and Long Beach VA — yielding approximately
**918 clinical instances**.

Three supervised machine learning models are trained and compared:
**Random Forest**, **Logistic Regression**, and **Support Vector Machine (SVM)**.
The framework is evaluated using Accuracy, Precision, Recall (Sensitivity),
F1-Score, and ROC-AUC, with **Recall as the primary metric** (target ≥ 0.90)
to minimise undiagnosed cases. The expected outcome is a lightweight,
interpretable, and deployable system that assists healthcare providers in
making faster, more accurate diagnostic decisions — even on basic hardware
in underserved clinics.

---

## 👤 Project Information

| Field        | Details                            |
|--------------|------------------------------------|
| **Name**     | Sadat Amir                         |
| **ID**       | 3369/16                            |
| **Year**     | 3rd Year, Computer Science         |
| **Course**   | CoSc3101 – Research Methods in CS  |
| **Instructor** | Mr. Birhane                      |
| **University** | Hawassa University               |
| **Deadline** | April 28, 2026                     |

---

## 📁 Repository Structure

```
heart-disease-ml-proposal/
│
├── 📄 README.md                   ← You are here
│
├── 📂 proposal/                   ← LaTeX source files
│   ├── main.tex                   ← Main LaTeX document
│   ├── reference.bib              ← BibTeX bibliography (14 entries)
│   └── figures/
│       ├── p 3.1.png              ← System architecture diagram
│       ├── p 3..png               ← Preprocessing pipeline diagram
│       └── gantt.png              ← Project Gantt chart
│
├── 📂 code/                       ← (Planned) Python implementation
│   ├── preprocessing.py           ← Data cleaning & normalisation
│   ├── train_models.py            ← Model training (RF, LR, SVM)
│   ├── evaluate.py                ← Metrics computation & plots
│   └── requirements.txt           ← Python dependencies
│
└── 📂 data/                       ← Dataset placeholder
    └── README_data.md             ← Dataset download instructions
```

---

## 🚀 Installation Instructions

### Prerequisites

Make sure you have the following installed on your system:

- **Python 3.9+** — [Download](https://www.python.org/downloads/)
- **pip** (comes with Python)
- **Git** — [Download](https://git-scm.com/)
- A **LaTeX distribution** (for compiling the proposal PDF)

---

### Step 1 — Clone the Repository

```bash
git clone https://github.com/s-a-d-a-t/Early-Detection-of-Heart-Disease-Using-Machine-Learning-Techniques-on-Patient-Health-Data     
cd heart-disease-ml-proposal
```

---

### Step 2 — Set Up Python Environment

It is strongly recommended to use a virtual environment:

```bash
# Create virtual environment
python -m venv venv

# Activate it
# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate
```

---

### Step 3 — Install Python Dependencies

```bash
pip install -r code/requirements.txt
```

The `requirements.txt` includes:

```
scikit-learn>=1.4.0
pandas>=2.0.0
numpy>=1.26.0
matplotlib>=3.8.0
seaborn>=0.13.0
```

Install them individually if needed:

```bash
pip install scikit-learn pandas numpy matplotlib seaborn
```

---

### Step 4 — Download the Dataset

The **Combined Heart Disease Dataset** is publicly available from the UCI
Machine Learning Repository. Download it manually:

1. Visit: [https://archive.ics.uci.edu/ml/datasets/heart+Disease](https://archive.ics.uci.edu/ml/datasets/heart+Disease)
2. Download the combined dataset (Cleveland, Hungary, Switzerland, Long Beach VA)
3. Place the CSV file inside the `data/` folder:

```
data/
└── heart_disease_combined.csv
```

> **Note:** The dataset contains ~918 instances and 11 clinical features
> including age, sex, chest pain type, resting blood pressure, cholesterol,
> fasting blood sugar, ECG results, max heart rate, and more.

---

### Step 5 — Compile the LaTeX Proposal

Install a LaTeX distribution if you haven't already:

| OS      | Recommended Distribution |
|---------|--------------------------|
| Windows | [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/) |
| macOS   | [MacTeX](https://www.tug.org/mactex/) |
| Linux   | `sudo apt install texlive-full` |

Then compile the proposal using this **exact 4-step sequence**:

```bash
cd proposal/

pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

> ⚠️ **You must run all four commands in order.** BibTeX needs the `.aux` file
> from the first `pdflatex` run to resolve citation keys. The final two
> `pdflatex` runs resolve cross-references and citation numbers.

If using **Overleaf**:
1. Upload `main.tex` and `reference.bib` and all figures to the same project
2. Set compiler to **pdfLaTeX** (Menu → Compiler)
3. Click **Recompile**

---

## 🧪 Machine Learning Models

| Model               | Library          | Key Hyperparameter         |
|---------------------|------------------|----------------------------|
| Logistic Regression | `scikit-learn`   | `max_iter=1000`, `C=1.0`   |
| Support Vector Machine | `scikit-learn` | `kernel='rbf'`, `C=1.0`   |
| Random Forest       | `scikit-learn`   | `n_estimators=100`         |

All models are trained under **5-fold stratified cross-validation** on an
80%/20% train/test split.

---

## 📊 Evaluation Metrics

| Metric    | Formula                                           | Role           |
|-----------|---------------------------------------------------|----------------|
| Accuracy  | (TP + TN) / (TP + TN + FP + FN)                  | Overall        |
| Precision | TP / (TP + FP)                                    | False alarms   |
| **Recall**| **TP / (TP + FN)**                                | **Primary ✓**  |
| F1-Score  | 2 × (Precision × Recall) / (Precision + Recall)  | Balance        |
| ROC-AUC   | ∫ TPR d(FPR)                                      | Discrimination |

> **Recall ≥ 0.90** is the minimum target. Missing a true heart disease case
> is clinically far more harmful than a false alarm.

---

## ⚖️ Ethics & Compliance

| Concern | Approach |
|---------|----------|
| **Data Privacy (GDPR)** | Only anonymised public UCI datasets are used. No PII is processed. |
| **Algorithmic Bias** | Stratified sampling ensures consistent accuracy across age groups and sexes. |
| **Environmental Impact** | Lightweight supervised models (vs. deep learning) minimise energy use — *Green AI*. |

---

## 📚 Key References

1. Mohan et al. (2019) — *Effective Heart Disease Prediction Using Hybrid ML* · IEEE Access
2. Detrano et al. (1989) — *UCI Cleveland Heart Disease Dataset* · Am. Journal of Cardiology
3. Bhatt et al. (2023) — *Heart Disease Prediction Using ML* · Algorithms (MDPI)
4. Chang et al. (2022) — *AI Model for Heart Disease Detection* · Healthcare Analytics
5. WHO (2023) — *Cardiovascular Diseases Fact Sheet*

> Full bibliography with DOIs is available in [`proposal/reference.bib`](proposal/reference.bib)

---

## 📅 Project Timeline

| Phase | Activity | Period |
|-------|----------|--------|
| 1 | Literature Review & Problem Definition | March 2026 |
| 2 | Dataset Collection & Preprocessing | March–April 2026 |
| 3 | Model Development & Training | April 2026 |
| 4 | Evaluation & Analysis | April 2026 |
| 5 | Report Writing & Submission | April 28, 2026 |

---

<div align="center">

*Hawassa University — Institute of Technology — Computer Science Department*
*© 2026 Sadat Amir · Academic Use Only*

</div>
