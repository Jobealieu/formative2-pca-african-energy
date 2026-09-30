# Formative 2: PCA from Scratch on African Energy Data (Pair 18)

**Group:** Alieu O Jobe, Dianah Gasasira Shimwa

We implement Principal Component Analysis from scratch with numpy (matplotlib only for plots) on
Our World in Data energy data for 57 African countries, 2000 to 2022 (1,299 rows).

## Dataset
- Source: https://github.com/owid/energy-data
- 11 raw columns used, 16 features after encoding
- 240 missing values (GDP missing for about 11% of rows), filled by country, then region, then overall median
- Non numeric columns: `country` (kept as a label) and `region` (one hot encoded)

## What the notebook does
1. Loads and cleans the data, imputes missing values, encodes region, standardizes with z = (x - mean) / std
2. Computes the covariance matrix and its eigenvalues and eigenvectors
3. Sorts components by explained variance and picks the number of components dynamically (90% threshold)
4. Projects the data and plots the original feature space next to the principal component space
5. Benchmarks an optimized version (vectorized, eigh, chunked, float32) on up to 1 million rows

## Files
- `Template_PCA_Formative_2_Pair18.ipynb`: the completed notebook with all outputs
- `data/owid-energy-data.csv`: the raw dataset
- `docs/task_sheet.pdf`: our group contribution sheet

## How to run
Open the notebook in Google Colab and click Runtime, then Run all. The first cell downloads the data automatically.
