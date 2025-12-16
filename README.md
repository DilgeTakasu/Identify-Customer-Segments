# Identify Customer Segments (Unsupervised Learning)

This project applies **unsupervised learning** to identify population segments that are most representative of a mail-order company’s customer base in Germany. The resulting segments can be used to focus marketing efforts on groups with higher expected response/return rates. :contentReference[oaicite:0]{index=0}

## Dataset & Usage Restrictions
The datasets used in this project were provided by **Bertelsmann Arvato Analytics (via Udacity)** for educational purposes. 

It is provided through the Kaggle competition:
- https://www.kaggle.com/competitions/udacity-arvato-identify-customers/data

Due to the competition/provider terms, the raw dataset files are **not included** in this repository and are **not redistributed** here.  
To reproduce the results, please obtain the data directly from Kaggle/Udacity and follow the competition rules.

## Repository Contents
- `Identify_Customer_Segments.ipynb` main analysis notebook
- `README.md` — project overview and uunning code.

## Approach (High-Level)
1. **Preprocessing**
   - Missing-value codes were converted to `NaN`
   - High-missingness columns were removed
   - Rows were split by missingness threshold; analysis proceeded on the low-missingness subset
   - Categorical features were re-encoded; mixed features were engineered (e.g., `PRAEGENDE_JUGENDJAHRE`, `CAMEO_INTL_2015`)
2. **Feature Transformation**
   - Scaling via `StandardScaler`
   - Dimensionality reduction via **PCA**
   - Principal components were interpreted using feature loadings
3. **Clustering**
   - **KMeans** was applied in PCA space
   - The chosen number of clusters was selected using an elbow-style analysis
   - Customer cluster proportions were compared against the general population to identify over/underrepresented segments

## How to Run (If You Have the Data)
1. Place the provided Udacity project files in a local `data/` directory (example):
   - `Udacity_AZDIAS_Subset.csv`
   - `Udacity_CUSTOMERS_Subset.csv`
   - `AZDIAS_Feature_Summary.csv`
   - `Data_Dictionary.md`
2. Install requirements:
   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn jupyter

## Quick View (HTML Report)

A rendered HTML version of the notebook is included for quick browsing (no execution required):

- [HTML Report](./Identify_Customer_Segments.html)

