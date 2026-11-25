# Exploratory Data Analysis (EDA) of House Prices — Ames Housing Dataset

A complete, end-to-end **Exploratory Data Analysis (EDA)** project on the [Ames Housing Dataset](https://www.kaggle.com/c/house-prices-advanced-regression-techniques) (`train.csv`, ~1,460 rows × 81 columns), built without machine learning modelling to practice data inspection, cleaning, statistical analysis, and visual storytelling.

---

## Project Objectives & Guiding Questions
1. **Target Distribution:** How is `SalePrice` distributed, and is it skewed?
2. **Feature Correlations:** Which numerical features correlate most strongly with `SalePrice`?
3. **Quality Impact:** Does overall quality (`OverallQual`) change price in a clear, ordered way?
4. **Location Effects:** Do some neighborhoods consistently cost more than others?
5. **Outlier Analysis:** Are there outliers, and are they data errors or real but unusual sales?
6. **Missing Data:** Which columns have missing values, and which represent `"feature absent"` rather than missing data?

---

## Tech Stack
* **Language:** Python 3
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`
* **Environment:** Google Colab / Jupyter Notebook

---

## EDA Workflow Covered
1. **Setup & First Look:** Dataset shape, data types, `.info()`, and missing-value percentages.
2. **Variable Classification:** Separating continuous, discrete, nominal, and ordered ordinal variables (`ExterQual`, `KitchenQual`, and conceptual ordinal `OverallQual`).
3. **Descriptive Statistics:** Mean, median, mode, standard deviation, variance, range, IQR, skewness, and kurtosis across key features.
4. **Data Quality & Cleaning:** Duplicate checks, string standardization, encoding feature-absent `NA` values (`PoolQC`, `Alley`, `Fence`, `FireplaceQu`, `GarageType`) as `"None"`, neighborhood-median imputation for `LotFrontage`, and range validation.
5. **Univariate Analysis:** Raw vs. log-transformed `SalePrice` distributions, boxplots by `OverallQual` and `Neighborhood`, and category countplots.
6. **Bivariate & Multivariate Analysis:** Covariance vs. Pearson/Spearman correlations, annotated scatter plots, KDE pairplots, and masked upper-triangle correlation heatmaps.
7. **Outlier Detection:** Comparison of IQR (`1.5 × IQR`) and Z-score (`|z| > 3`) methods on `GrLivArea` and `SalePrice`.
8. **Summary Dashboard:** A 2×2 visual summary exported as `eda_dashboard.png`.

---

## Key Takeaways
* **`SalePrice` is right-skewed** (`mean > median`), and a logarithmic transform brings it close to a normal distribution.
* **`OverallQual` and `GrLivArea`** show the strongest positive correlations with `SalePrice`.
* **Price rises monotonically** across quality tiers `1–10` and varies substantially across neighborhoods.
* **Extreme large-area, low-price sales** (`GrLivArea > 4,000 sq ft`) distort linear trends and are separated in `df_clean`.
* **Most `NA` entries denote absent amenities** (no pool, alley, fence, fireplace, or garage) rather than missing records.

---

## Repository Structure
```text
├── EDA_Project_House_Prices_Colab.ipynb   # Complete annotated Colab notebook
├── eda_dashboard.png                      # 4-panel visual summary dashboard
└── README.md                              # Project documentation
