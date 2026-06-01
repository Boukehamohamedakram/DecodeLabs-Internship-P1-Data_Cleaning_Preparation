# DecodeLabs Internship Project P1

## Overview

This repository contains the cleaned DecodeLabs dataset and the supporting documentation for the Data Cleaning & Preparation project.

> The most important file in this repository is the cleaned dataset: `data/raw/DecodeLabs_Cleaned_Dataset.xlsx`

## Dataset summary

- Records: `1,200`
- Columns: `14`
- Source file: `data/raw/DecodeLabs_Cleaned_Dataset.xlsx`
- Cleaning status: verified and ready for analysis

## QA Verification Summary

- Total Records: preserved at `1,200`
- Total Columns: preserved at `14`
- Duplicate `OrderID`: `0` → `PASS`
- Missing `CouponCode`: `309` → `0` (`NONE` imputed)
- Floating-point noise in `TotalPrice`: `29` rows → rounded to 2 decimal places
- Date format consistency: Excel serials normalized to `YYYY-MM-DD`
- Invalid `OrderStatus` values: `0`
- Invalid `PaymentMethod` values: `0`
- Invalid `Product` values: `0`
- `TotalPrice = Quantity × UnitPrice`: all match
- Final error rate:
  - Unique IDs: `0%`
  - Date format: `0%`

## Data cleaning change log

1. **TotalPrice / UnitPrice**
   - Issue: floating-point precision noise (>2 decimal places)
   - Action: rounded to 2 decimal places
   - Records affected: `29`
   - Status: `Resolved`

2. **CouponCode**
   - Issue: missing / null values
   - Action: imputed with `NONE` (no coupon applied)
   - Records affected: `309`
   - Status: `Resolved`

3. **Date**
   - Issue: Excel serial numbers / mixed date formats
   - Action: parsed and standardized to `YYYY-MM-DD`
   - Records affected: `1,200`
   - Status: `Resolved`

4. **OrderID**
   - Issue: duplicate unique identifiers
   - Action: verified uniqueness
   - Records affected: `0`
   - Status: `Verified`

5. **TotalPrice**
   - Issue: verified price consistency
   - Action: confirmed `TotalPrice = Quantity × UnitPrice`
   - Records affected: `0`
   - Status: `Verified`

6. **OrderStatus**
   - Issue: invalid/unexpected category values
   - Action: confirmed all values are within the expected set
   - Records affected: `0`
   - Status: `Verified`

7. **PaymentMethod**
   - Issue: invalid/unexpected category values
   - Action: confirmed all values are within the expected set
   - Records affected: `0`
   - Status: `Verified`

8. **Product**
   - Issue: invalid/unexpected category values
   - Action: confirmed all values are within the expected set
   - Records affected: `0`
   - Status: `Verified`

## Project structure

- `config/` — environment templates and configuration
- `data/raw/` — cleaned dataset and raw files
- `data/processed/` — transformed datasets and intermediate outputs
- `data/outputs/` — generated reports and visual outputs
- `docs/` — project documentation

## Usage

1. Open `data/raw/DecodeLabs_Cleaned_Dataset.xlsx` in Excel or a compatible viewer.
2. Use the cleaned dataset for downstream analysis or reporting.
3. Refer to the `docs/` folder for architecture, standards, and deployment notes.
