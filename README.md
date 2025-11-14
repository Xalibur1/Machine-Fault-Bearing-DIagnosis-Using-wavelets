
# Explainable Bearing Fault Diagnosis with Wavelet Features and Random Forests

This project is a complete case study for predictive maintenance (PdM) using the Case Western Reserve University (CWRU) bearing dataset. It demonstrates a practical and highly explainable machine learning pipeline for detecting and classifying faults in rolling-element bearings.

The entire analysis is based on the accompanying [Python notebook](notebooks/fdl-project.ipynb) and is summarized in the [detailed research paper](report/FDL_Paper.pdf).

## ⚙️ Key Features
* **Dataset:** CWRU Bearing Dataset (10-class problem, including fault type and severity).
* **Feature Engineering:** A robust pipeline comparing Time-Domain, FFT, STFT, and Discrete Wavelet Transform (DWT) features.
* **Model:** A Random Forest classifier that achieves high accuracy (98% in the notebook) on the 10-class problem.
* **Explainability (XAI):** Analysis of feature importance proves *why* DWT (wavelet) features are critical for separating the fault "signal" from the machine "noise".

## 📊 Key Results
The comprehensive analysis from the notebook (`fdl-project.ipynb`) generated the dashboard below. The "Top 12 Feature Importances" plot clearly shows that Wavelet-based features (e.g., `wavelet_L1_mean`, `wavelet_L4_entropy`) and FFT features were the most decisive for the model.

![Comprehensive Analysis Dashboard](outputs/images/bearing_fault_diagnosis_complete.png)

## 📁 Repository Structure
```

bearing-fault-diagnosis/
├── README.md               \<-- You are here
├── requirements.txt        \<-- Python libraries to install
├── data/raw/               \<-- Download and place CWRU .mat files here
├── notebooks/
│   └── fdl-project.ipynb   \<-- The main Jupyter notebook
├── outputs/
│   ├── images/
│   │   └── ...\_complete.png  \<-- Saved dashboard image
│   └── models/
│       └── (Saved .pkl models)
└── report/
└── FDL\_Paper.pdf         \<-- The full PDF write-up

````

## 🚀 How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/bearing-fault-diagnosis.git](https://github.com/your-username/bearing-fault-diagnosis.git)
    cd bearing-fault-diagnosis
    ```
2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```
3.  **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Download the Data:**
    * Download the CWRU bearing dataset `.mat` files. A common source is the [Kaggle mirror](https://www.kaggle.com/datasets/brjapon/cwru-bearing-datasets-mat-files).
    * Place all the `.mat` files (e.g., `B007_1_123.mat`, `OR007_6_1_136.mat`, etc.) inside the `data/raw/` directory.
    * *Note: You may need to slightly adjust the `find_mat_files` function in the notebook to look in `./data/raw/` instead of `/kaggle/input/`.*

5.  **Run the Notebook:**
    * Launch Jupyter Notebook:
      ```bash
      jupyter notebook
      ```
    * Open `notebooks/fdl-project.ipynb` and run the cells.

