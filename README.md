# Heart Failure Prediction Using Multiple Linear Regression

An educational machine-learning project that uses clinical measurements
from a heart-failure dataset to explore whether a patient experienced a
death event during the recorded follow-up period.

> **Important:** This is an academic demonstration, not a medical
> diagnostic or clinical decision-support tool.

## Team 16

| Team member       | IIT Ropar Entry Number | GitHub Handle                                            | Lead Responsibility |
|-------------------|------------------------|----------------------------------------------------------|---------------------|
| Sai Varsith Reddy | `2026AIB1086`          | [@saivarsith](https://github.com/saivarsith)             | Documentation Lead  |
| Rishit Jha        | `2026EEB1400`          | [@2026eeb1400-beep](https://github.com/2026eeb1400-beep) | Execution Lead      |
| Pranav Kardile    | `2026MCB1534`          | [@Pranavx-k](https://github.com/Pranavx-k)               | Video Lead           |
| Ujjwal Kumar      | `2025DAB1286`          | [@Ujjwal4401](https://github.com/Ujjwal4401)             | PPT Lead          |

**GitHub repository:**
<https://github.com/2026eeb1400-beep/AI101-Project-Grp-16>

## Project Overview

The project uses the heart failure clinical records dataset to build a
**Multiple Linear Regression** model. The target column is
`DEATH_EVENT`:

- `1` — death event recorded during the follow-up period.
- `0` — no death event recorded during the follow-up period.

The notebook selects five input features:

- `age`
- `ejection_fraction`
- `serum_creatinine`
- `serum_sodium`
- `time`

The model produces a numerical score. The notebook uses a threshold of
`0.5` to convert that score into a predicted class (`0` or `1`).

## Dataset

The supplied CSV file is `heart_failure_clinical_records_dataset.csv`.

- **Rows:** 299 patient records
- **Columns:** 13
- **Target:** `DEATH_EVENT`
- **Missing values:** none were found during the notebook's data
  inspection

The dataset contains clinical measurements and patient information,
including age, anaemia, creatinine phosphokinase, diabetes, ejection
fraction, high blood pressure, platelets, serum creatinine, serum
sodium, sex, smoking, follow-up time, and the death-event target.

The notebook expects the CSV file to be in the **same directory** as
`heart_failure_simple.ipynb`. Do not rename either file unless you also
update the path in the notebook.


## Repository Structure

The repository contains the following files:

``` text
AI101-Project-Grp-16/
├── data/
│   ├── raw/
│   │   └── heart_failure_clinical_records_dataset.csv
│   └── processed/
│
├── models/
│
├── notebooks/
│   └── heart_failure_analysis.ipynb
│
├── outputs/
│   ├── figures/
│   └── metrics/
│
├── src/
│   ├── _init_.py
│   ├── config.py
│   ├── data_preprocessing.py
│   ├── train_model.py
│   ├── evaluate_model.py
│   └── predict.py
│
├── requirements.txt
└── README.md
```

## Requirements

- **Python:** 3.13.5 (version used to execute and check the notebook) and above
- Dependencies and pinned versions are listed in `requirements.txt`.
- The notebook uses Jupyter Notebook, pandas, Matplotlib, and
  scikit-learn.

## Setup and Execution
### Please run the codes one line at a time.
### 1. Clone the repository

``` bash
git clone https://github.com/2026eeb1400-beep/AI101-Project-Grp-16.git
```
``` bash
cd AI101-Project-Grp-16
```

### 2. Create and activate a virtual environment

**Windows (Command Prompt):**

``` bat
py -m venv .venv
```

``` bat
.venv\Scripts\activate
```

**Windows (PowerShell):**

``` powershell
py -m venv .venv
```
``` powershell
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

``` bash
python3 -m venv .venv
```
``` bash
source .venv/bin/activate
```

### 3. Install dependencies

``` bash
python3 -m pip install --upgrade pip
```
``` bash
python3 -m pip install -r requirements.txt
```

### 4. Train the Model

Execute the following code:

``` bash
python3 src/train_model.py
```

### 5. Evaluate the Model

After training is complete, execute:

``` bash
python3 src/evaluate_model.py
```

### 6. Output

After successful execution, the generated files will be available in:

Trained Model:

``` text
models/
└── heart_failure_model.joblib
```

Evaluation Metrics: 

``` text
outputs/metrics/
├── model_metrics.csv
├── model_weights.csv
├── confusion_matrix.csv
└── test_predictions.csv
```

Visualizations: 

``` text
outputs/figures/
├── training_risk_scores.png
├── training_risk_map.png
├── confusion_matrix.png
└── testing_risk_scores.png
```

## Model Results

The model was executed with the supplied dataset and the dependency
versions listed in `requirements.txt`. With the notebook's current split
and threshold, the testing results were:

| Metric    | Test result |
|-----------|------------:|
| MAE       |       0.290 |
| RMSE      |       0.371 |
| R²        |       0.363 |
| Accuracy  |       0.833 |
| Precision |       0.846 |
| Recall    |       0.579 |
| F1 score  |       0.688 |

The test confusion matrix is:

``` text
[[39  2]
 [ 8 11]]
```

Rows represent actual classes (`0`, `1`) and columns represent predicted
classes (`0`, `1`).

These values are tied to the current dataset, feature-selection
procedure, train/test split, and threshold. They may change if any of
those are changed.


## Presentation and Video

- **Project presentation (PPT):** `[Add the shareable PPT link here]`
- **Project video (maximum 5 minutes):**
  `[Add the shareable video link here]`

Before submission, replace both placeholders with working links and
check that they can be opened by the evaluator (including in a
private/incognito window, if required).

## AI-Use Disclosure

ChatGPT (OpenAI) was used to assist with drafting and organising this
README and reviewing the project files for documentation details. The
project description, repository instructions, and reported metrics were
checked against the supplied notebook and dataset; the notebook was also
executed to verify that it runs with the pinned dependencies listed in
`requirements.txt`.

Claude (Anthropic) was used to refine the model training and evaluation process.
Joblib library was recommended by Claude for storage of trained model.

## Before Submission Checklist

- [ ] Confirm that all four members have access to the repository.
- [ ] Each member makes meaningful commits from their own GitHub
  account.
- [ ] Keep the notebook and CSV in the same directory, or update the
  notebook's relative path and this README.
- [ ] Add the actual evaluation screenshot at
  `images/model_evaluation.png`.
- [ ] Replace the PPT and video placeholders with working links.
- [ ] Ask a teammate to clone the repository on another computer and
  follow only the instructions in this README.
- [ ] Confirm that the notebook runs from a fresh clone using the
  commands above.
- [ ] Ensure the README and the final PPT slide contain the required
  AI-use disclosure.
