# E-commerce Revenue Prediction 🌐

A machine learning project that predicts whether an e-commerce browsing session will generate revenue using Decision Tree Classification, with a focus on model optimization through pre-pruning and post-pruning.

## 📌 Project Overview

This project uses e-commerce session data to classify whether a visitor's session results in revenue. It explores how Decision Tree pruning and hyperparameter tuning can improve classification performance.

## 🎯 Objectives

- Explore and preprocess the e-commerce dataset.
- Convert Boolean and categorical features into numerical representations.
- Build a baseline Decision Tree Classifier.
- Apply **pre-pruning** using `max_depth` and `min_samples_split`.
- Apply **post-pruning** using cost-complexity pruning (`ccp_alpha`).
- Compare manual hyperparameter selection with GridSearchCV.
- Evaluate models using the F1-score.
- Visualize the trained Decision Trees.

## 📊 Dataset

**File:** `shop_smart_ecommerce.csv`

The dataset contains 12,330 sessions and 18 columns, including:

- **Browsing activity:** Administrative, Informational, and ProductRelated pages and their durations.
- **Behavioral metrics:** BounceRates, ExitRates, PageValues, and SpecialDay.
- **Visitor information:** Month, VisitorType, Weekend, Region, Browser, OperatingSystems, and TrafficType.
- **Target variable:** Revenue — whether the session generated revenue.

## 🛠️ Technologies Used

- Python
- Pandas
- Scikit-learn
- Matplotlib
- Jupyter Notebook

## ⚙️ Project Workflow

### 1. Data Preprocessing
- Inspect dataset structure and missing values.
- Convert Boolean features into integer values.
- Encode Month using a manual mapping.
- Apply one-hot encoding to VisitorType.
- Separate features (`X`) and target (`y`).

### 2. Baseline Decision Tree
- Train a Decision Tree Classifier.
- Generate predictions on the test dataset.
- Evaluate performance using the F1-score.
- Visualize the tree structure.

### 3. Pre-Pruning
Control tree complexity using:
- `max_depth`
- `min_samples_split`

Test different parameter combinations manually and with GridSearchCV, using F1-score as the selection metric.

### 4. Post-Pruning
Apply cost-complexity pruning using `ccp_alpha`.

- Generate candidate alpha values with `cost_complexity_pruning_path()`.
- Compare manual alpha selection with GridSearchCV.
- Select the best alpha using cross-validation.
- Evaluate the selected model on the test dataset.
- Visualize the post-pruned tree.

## 📈 Evaluation Metric

**F1-score** is used to evaluate the balance between precision and recall for the positive class (`Revenue = 1`).

The project uses **0.55 as the target F1-score benchmark**.

The final test score should be reported after running the notebook; no performance result is assumed here.

## 🚀 How to Run

1. Clone this repository.
2. Install the required libraries:

   ```bash
   pip install pandas scikit-learn matplotlib jupyter
   ```

3. Keep `shop_smart_ecommerce.csv` in the same directory as the notebook.
4. Launch JupyterLab:

   ```bash
   jupyter lab
   ```

5. Open `Ecommerce-Revenue-Prediction.ipynb` and run the cells in order.

## 🔮 Future Improvements

- Compare Decision Tree performance with Random Forest and other classification algorithms.
- Use cross-validation consistently for hyperparameter selection.
- Evaluate precision, recall, confusion matrix, and ROC-AUC.
- Compare model complexity, training time, and generalization performance.
- Experiment with alternative feature encoding strategies.

---

**Key Learning:** This project explores how Decision Tree complexity, pre-pruning, post-pruning, and hyperparameter tuning influence classification performance.