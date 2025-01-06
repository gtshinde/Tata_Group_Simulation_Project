# Online Retail Dataset Analysis and Data Cleaning

## Executive Summary
The Online Retail dataset was analyzed for data quality issues and cleaned to improve usability and accuracy for further analysis. Below is an overview of the identified issues, cleaning approaches, and modifications applied to the dataset.

## Data Quality Issues and Cleaning Approaches
### Missing Values
- **Description**: 1,454 records with missing product descriptions.
- **CustomerID**: 135,080 records with missing CustomerID values (~50% of the dataset).

**Approach**:
- Removed rows with missing product descriptions.
- Retained rows with missing CustomerID as they may represent guest purchases.

### Negative Quantities
- **Details**: 10,624 records with negative quantities.
- **Observation**: Most are valid as they represent returns/cancellations (indicated by invoice numbers starting with 'C').

**Approach**:
- Preserved negative quantities as they represent valid returns.

### Price Issues
- **Details**: 2,517 records with zero or negative prices.

**Approach**:
- Investigated and removed rows with zero or negative prices as they were deemed errors or special cases.

### Cancelled Transactions
- **Details**: 9,288 cancelled invoices (invoices starting with 'C').

**Approach**:
- Added a 'Transaction_Type' column to distinguish returns (invoices starting with 'C') from purchases.

## Modifications Applied
- Added a new column, **'Transaction_Type'**, to categorize transactions as Returns or Purchases.
- Removed rows with missing product descriptions.
- Removed rows with zero or negative prices while preserving negative quantities (valid returns).
- Added a **'Total_Value'** column calculated as `Quantity * UnitPrice`.

## Dataset Reduction
- Original rows: **541,909**
- Cleaned rows: **540,453**
- The cleaning process preserved most of the data while addressing problematic entries.

## Additional Observations
- The dataset includes transactions from **37 different countries**.
- Missing CustomerID values are likely due to guest checkouts.
- Negative quantities are predominantly associated with return transactions (invoices prefixed with 'C').

## Tools and Skills Used
- **Tools**: Python (Pandas, NumPy), Excel
- **Skills**: Data Cleaning, Data Analysis, Data Validation, Business Insights

## Recommendations
WIP

