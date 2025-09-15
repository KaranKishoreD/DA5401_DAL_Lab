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

## Overall analysis

As we can see above, setting the threshold higher can have a better performance balancing precision with recall. In our case, the models trained on GMMs are almost identical in performance.

- Baseline has a much lower recal compared to any of the GMM models. It increases by 10-15% using GMMs which is excellent as we are able to get the minority samples predictions more correctly.

- Factors such as Class ratio (majority: minority) seem to play a small role as well. As y increase in (x:y), i.e., the number of majority classes in CBU decreases, the recall tends to fall - this also shows that higher number of majority classes compared to minority is slightly better  (the weighted f1 score doesn't matter much though).

## Reasons why precision could be low:

- The dataspace could be non-linear in nature. So, a logistic regression based model may not be able to perform the classification.

- The best performing model, going by the numbers is the second GMM where CBU is done on the majority sample and oversampling using GMM is done on the minority sample (precision ~ 0.5787 and recall ~ 0.7703). However, the precision needs to be much higher for a "real-life" implemenatations: several factors can improve this, for example by choosing an appropriate classification method.

- The vanilla baseline model has a better precision but lower recall (0.6554). Here, recall is extremely important as we can't ignore a fraudulent transaction which leads me to the fact that GMM based sampling is better. Empirically, CBU undersampling and GMM based oversampling is slightly better as well as CBU just tries to remove datapoints that belong to a majority class cluster.

## Overall, GMM based model have a better recall and precision that can be imporoved using better clustering methods and finetuning them.
