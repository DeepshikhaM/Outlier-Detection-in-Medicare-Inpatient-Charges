# Outlier-Detection-in-Medicare-Inpatient-Charges

## Medicare Inpatient Hospitals Dataset

## Overview
The **Medicare Inpatient Hospitals by Geography and Service** dataset provides information on hospital discharges for Original Medicare Part A beneficiaries across **IPPS hospitals** (Inpatient Prospective Payment System). It contains details on hospital discharges, charges, and payments related to Medicare patients.

## Data Description
The dataset includes the following key fields:

- **DRG Definition:** Diagnosis-Related Group (DRG) classification system for hospital reimbursement.
- **Provider Id:** Unique identifier for the healthcare provider.
- **Provider Name:** Name of the hospital/provider.
- **Provider Street Address:** Physical address of the provider.
- **Provider City:** City where the hospital is located.
- **Provider State:** State where the hospital is located.
- **Provider Zip Code:** Zip code of the provider.
- **Hospital Referral Region Description:** Regional classification for patient referrals.
- **Total Discharges:** Number of inpatient discharges for a given DRG.
- **Average Covered Charges:** The average amount charged for a DRG across all providers.
- **Average Total Payments:** The total payment received for a DRG, including all sources of payment (Medicare, private insurers, patient payments, etc.).
- **Average Medicare Payments:** The average amount paid by Medicare for a DRG.

## Formulae Used in the Dataset

1. **Total Covered Charge Amount** = Sum of all covered charges.
2. **Average Covered Charges** = `Total Covered Charge Amount / Total Discharges`
3. **Average Total Payments** = `Total Payments / Total Discharges`
4. **Average Medicare Payments** = `Medicare Payment Amount / Total Discharges`

## Problem Statement
How can we identify and address anomalies or fraudulent activities in Medicare hospital payments by analyzing patterns in discharges, charges, and payments, and applying advanced anomaly detection techniques like PCA and KNN?

## Key Findings
1. **High-Quality Dataset**: The dataset contained 0 missing values and 0 duplicate rows, ensuring a robust foundation for analysis. Standardized column names and conversion of financial metrics into numeric formats facilitated efficient processing.
2. **Regional Disparities in Medicare Payments**: Significant state-level variations in Average Medicare Payments and Total Payments were observed, with some states exceeding 200% of the state average, requiring further investigation.
3. **Correlations and Payment Trends**: A strong positive correlation (R > 0.8) between Average Total Payments and Average Medicare Payments was found. However, some providers had payments up to 3x higher than the average, suggesting inefficiencies or fraudulent activities.
4. **Outlier Detection**: Using PCA and kNN, 5% of providers (8,154 out of 163,065 entries) were identified as anomalous, exhibiting 2.12 times higher Average Medicare Payments and 2.83 times higher Total Payments than normal providers.
5. **Engineered Features for Anomaly Detection**: Developed 20 advanced features, such as Medicare Payment Ratio and Provider Variability Index, to enhance anomaly detection. Outlier providers had a Medicare Payment Ratio exceeding 85%, compared to 77% for normal providers.
6. **Fraud and Efficiency Insights**: Outlier detection revealed potential fraudulent billing or inefficiencies, with flagged providers showing extreme metrics, such as Payments per Discharge up to $1,500 above the average and Covered Charges exceeding 1.83 standard deviations above state norms.
7. **Business Impact**: These insights can drive policy adjustments, audits, and resource allocation, potentially saving millions in Medicare reimbursements by addressing fraudulent claims and improving cost efficiency.
8. **Future Opportunities**: Integrating temporal trends, broader care settings (e.g., outpatient services), and predictive modeling can enhance fraud detection and healthcare policy development. Real-time anomaly detection could further optimize resource allocation and compliance monitoring.




## License
This dataset is publicly available and subject to relevant data usage policies.
