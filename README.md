
# Credit Card Fraud Detection Using Quantum Machine Learning

This repository demonstrates a Quantum Machine Learning (QML) approach to detect credit-card fraud using Qiskit and classical preprocessing. The primary work is contained in the Jupyter notebook `QML (2).ipynb`. Model artifacts (saved VQC models) are included for convenience.

**Contents**
- `QML (2).ipynb`: Main notebook containing data loading, preprocessing, model construction (VQC), training, evaluation, and example frontend widgets.
- `requirements.txt`: Python dependencies needed to run the notebook.
- `vqc_fraud_model_*.json` / `vqc_fraud_model_*.pkl`: Example saved model artifacts.
- `LICENSE`: MIT license for this project.

**Highlights**
- Uses amplitude/feature/vector encodings + variational quantum circuits (VQC) from `qiskit-machine-learning`.
- Demonstrates data balancing, scaling, padding to power-of-two dimensions, and training a VQC classifier.
- Includes interactive `ipywidgets` frontend for quick manual predictions.

**Dataset**
- Dataset used: `mlg-ulb/creditcardfraud` (Kaggle). You can download it manually from Kaggle or use the `kagglehub` helper included in the notebook to download programmatically. The notebook expects `creditcard.csv` to be available in the working folder or the downloaded dataset path.

**Requirements**
- See `requirements.txt` for the package list. Key packages: `qiskit`, `qiskit-machine-learning`, `numpy`, `pandas`, `matplotlib`, `scikit-learn`, `ipywidgets`.

**Quick Setup (Windows / PowerShell)**

1. Open PowerShell and change into the project directory:

```powershell
Set-Location -LiteralPath 'C:\Users\ramdw\Desktop\Credit Card fraud detection Using QML'
```

2. (Recommended) Create and activate a virtual environment:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3. Install dependencies:

```powershell
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

4. If you plan to use Kaggle to download the dataset automatically, ensure credentials are configured or download the CSV manually and place `creditcard.csv` in the project folder.

**Run the notebook**

1. Start Jupyter Notebook or JupyterLab:

```powershell
jupyter notebook
# or
jupyter lab
```

2. Open `QML (2).ipynb` in the browser and run the cells sequentially.

Notes while running:
- The notebook contains `!pip install` cells for `qiskit` and `qiskit-machine-learning` — if you already installed from `requirements.txt`, you can skip rerunning those cells.
- Training a VQC may take time depending on the optimizer and number of iterations (the notebook uses `COBYLA` by default). Consider reducing `maxiter` during development.
- If you have access to an IBM Quantum backend and want to run on hardware, configure `IBMQ` credentials and replace the `Sampler` with appropriate primitives; otherwise the notebook uses simulator primitives.

**Saving and Loading Models**
- The notebook includes code to save trained `VQC` models using `vqc.save(<filename>)` and load them with `VQC.load(<filename>)`. Make sure the path is correct when loading.

**Common Commands**
- Create GitHub remote and push (example; replace `<your-repo>`):

```powershell
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin master
```

**Reproducibility & Pinning**
- For reproducible installs, consider pinning exact versions in `requirements.txt` (I can help set specific versions if you want to freeze them).

**Troubleshooting**
- If `qiskit` or `qiskit-machine-learning` fails to install, make sure you have a recent `pip` and Python 3.8+ (Qiskit requirements may vary). Use the `--user` flag or a virtual environment if permissions are an issue.
- If the notebook shows shape or padding errors, re-run the data-preparation cells in order to re-create `scaler`, `X`, and `y` before training.

**License**
- This project is available under the MIT License — see the `LICENSE` file.

**Contact**
- Questions or suggestions: open an issue in the GitHub repo or reach out on your preferred channel.

