# DA5401_DAL_Lab
# DA5401 - Assignment 4  
**Name:** Karan Kishore  
**Roll Number:** DA25D400
**Title:** GMM-Based Synthetic Sampling for Imbalanced Data

### Dataset downloaded as zip and assumed to be present in pwd (Present Working Directory)

---

## Description
This assignment explores GMM as an oversampling strategy for handling class imbalance in the credit card fraud detection dataset. The various methods tried are:
- Baseline (no resampling)  
- GMM1 (oversampling on minority datapoint to match the majority data points)
- GMM2 (CBU (CLustering based Undersampling) on Majority dataset and GMM based oversampling on minority dataset) for different majority:minority ratio like 100:1, 50:1, 25:1 and 10:1.

We use Logistic Regression as the base classifier and evaluate performance with **precision, recall, F1** for the fraud class (`Class = 1`). We finetune logisti

---

## ⚙️ Environment Setup (Windows)

```powershell
# 1. Delete old virtual environment (if exists)
<pre> ``` Remove-Item -Recurse -Force .\a3 ``` </pre>

# 2. Create a new virtual environment
python -m venv a3

# 3. Activate the virtual environment
.\a3\Scripts\activate

# 4. Upgrade pip
python -m pip install --upgrade pip

# 5. Install required libraries
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn jupyter

# 6. Save requirements
pip freeze > requirements.txt

## Environment Setup (Linux)

## ⚙️ Environment Setup (Linux / macOS / WSL)

```bash
# 1. Delete old virtual environment (if exists)
rm -rf a3

# 2. Create a new virtual environment
python3 -m venv a3

# 3. Activate the virtual environment
source a3/bin/activate

# 4. Upgrade pip
pip install --upgrade pip

# 5. Install required libraries
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn jupyter

# 6. Save requirements
pip freeze > requirements.txt
