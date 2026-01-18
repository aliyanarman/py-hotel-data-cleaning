# Hotel Data Cleaning (Pandas)

This repository contains a reproducible data-cleaning pipeline for a hotel booking dataset using Python and pandas. The goal is to resolve common real-world data quality issues before analysis or modeling.
#### Note :
This project focuses on data hygiene and logical consistency, not feature engineering or imputation. All ambiguous records are either corrected deterministically or removed for analytical reliability.

## Dataset Issues Addressed

* Inconsistent string formatting (whitespace, casing)
* Invalid or malformed date values
* Check-out dates earlier than check-in dates
* Inconsistent categorical values (payment status, country names)
* Missing or invalid numerical values (price, number of guests)
* Missing contact information

## Cleaning Logic

The notebook performs the following operations in-place on existing columns:

1. Trim whitespace across all string columns
2. Parse date columns with coercion for invalid values
3. Nullify logically invalid date ranges (check-out < check-in)
4. Standardize categorical fields (e.g., payment status)
5. Replace zero or negative prices with nulls
6. Normalize email casing
7. Enforce valid guest counts (>= 1)
8. Drop rows missing critical analytical fields

No new columns are created. All transformations overwrite existing fields to preserve schema integrity.

## File Structure

* `hotel_data_cleaning.ipynb` – Main data-cleaning notebook
* `hotel_data.csv` – Raw input dataset

## Requirements

* Python 3.9+
* pandas
* numpy

## Usage

Open the notebook and run all cells sequentially:

```bash
jupyter notebook hotel_data_cleaning.ipynb
```

The final dataframe is clean and ready for downstream analysis, reporting, or modeling.

