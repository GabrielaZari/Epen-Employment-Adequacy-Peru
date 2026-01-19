# Employment Adequacy in Lima,Peru: An Age-Group Analysis using EPEN (INEI)

## Project Overview

This project analyzes **employment quality in Peru** through an age-group lens, focusing on **young adults (18–29)** and **prime-age adults (30–49)**. Using data from the **Encuesta Permanente de Empleo Nacional (EPEN)** published by the **National Institute of Statistics and Informatics (INEI)** (http://bit.ly/3ZjzK7L), the analysis explores trends in:

- Adequate employment  
- Access to health insurance  
- Average monthly income  
- Average weekly working hours  

The project emphasizes **data literacy, methodological transparency, and responsible interpretation of official labor statistics**, and is designed as a portfolio piece for applied social data analysis.

---

## Motivation and Research Interest

My interest in this topic emerged from a broader concern with **labor market recovery and job quality in Lima, Peru**, particularly after the COVID-19 pandemic. While employment rates are often reported as headline indicators, they can mask important dimensions of **job adequacy, income stability, and access to social protection**, especially for younger workers.

This project aims to move beyond employment status alone and examine **how job quality differs by age group**, using official survey-based indicators published by INEI.

---

## Data Source

- **Survey**: Encuesta Permanente de Empleo Nacional (EPEN)  
- **Institution**: Instituto Nacional de Estadística e Informática (INEI)  
- **Period analyzed**: April–May–June quarter  
- **Years covered**: 2022, 2023, 2024, 2025  

Official documentation:
- EPEN Technical Sheet (INEI)  
- EPEN Variable Dictionaries (by year)

---

## Nature of the Dataset (Methodological Note)

Although the datasets retain survey-like variables (employment status, income, hours worked, health insurance, expansion factors), **they are not individual-level microdata**.

The EPEN files used in this project correspond to **processed and aggregated statistical dissemination datasets**, where:

- Each row **does not represent an individual respondent**
- The number of observations (~200 rows per quarter) is far smaller than the actual survey sample (≈4,000+ individuals per quarter)
- Variables reflect **pre-processed statistical groupings**, not raw responses

Therefore, all results should be interpreted as **descriptive indicators within the published EPEN aggregates**, not as direct estimates derived from individual-level microdata.

---

## Why the April–May–June Quarter?

The April–May–June quarter was selected because:

- It is **consistently available across multiple years**
- Key variables (working hours, income, employment status, health insurance) are **complete and comparable**
- Other quarters (e.g., Oct–Nov–Dec) present missing or inconsistent information for several variables
- The last quarter reported by INEI was the Apr-May-June quarter, so, I decided to compare the same quarter throught different years. This choice ensures **temporal comparability and analytical coherence**.

---

## Key Variables Used

| Concept | Variable(s) | Description |
|------|------------|------------|
| Age | `C208` | Age of respondent |
| Employment status | `OCUP300` | Occupied / Unemployed / Inactive |
| Working hours | `whoraT` | Total weekly hours worked |
| Income | `INGTOTP` | Main monthly labor income |
| Health insurance | `SEGURO1` | Affiliation to any health insurance |
| Desire to work more hours | `C333` / `P209H` | Underemployment condition |
| Expansion factor | `FAC_T300` (2022) / `fa_*` (2023–2025) | Survey weight |

---

## Definition of Adequate Employment

Following INEI’s operational definition, **adequate employment** includes occupied individuals who meet at least one of the following conditions:

1. Work **35 hours or more per week** and earn **at or above a reference minimum income**  
2. Work **less than 35 hours**, but **do not wish to work more hours**

I decided to base the analysis on this definition to be consistent with the INEI approach, but I deliberately added variables (health insurance, monthly income and weekly working hours) to complement this approach, since I wanted to explore other social factors that were related to work conditions. 

---

## Analytical Approach

The analysis is **descriptive and comparative**, and includes:

- Weighted indicators using official expansion factors  
- Comparison by age group (18–29 vs 30–49)  
- Time-series comparison across years (2022–2025)  
- Visualization of trends in:
  - Adequate employment
  - Health insurance coverage
  - Average income
  - Average working hours  

All computations were performed using **Python (pandas, numpy, matplotlib)**.

---

## Key Findings (Based on Published EPEN Aggregates)

### Adequate Employment
- Younger workers show **greater volatility** across years  
- Prime-age adults exhibit **more stable trajectories**  
- The sharp increase observed in 2025 should be interpreted **with caution**, as it may reflect changes in data composition rather than pure labor market improvement  

### Health Insurance Coverage
- Adults consistently show **higher access to health insurance**  
- A temporary decline is observed in 2024, followed by recovery in 2025  
- Persistent age-related gaps remain evident  

### Income
- Average monthly income is higher for adults across all years  
- The sharp rise in 2025 suggests **possible compositional or reporting effects**, not necessarily real wage growth  

### Working Hours
- Both groups consistently exceed the 35-hour threshold  
- Younger workers often report **equal or higher weekly hours**, raising questions about job quality versus workload  

---

## Limitations

- The data are **not individual-level microdata**  
- Results cannot be interpreted as national prevalence estimates  
- Changes across years may reflect:
  - Differences in aggregation  
  - Domain composition  
  - Publication criteria  
- Causal inference is **not possible**

---

## Future Work

Possible extensions of this project include:

- Replicating the analysis using **ENAHO microdata** (if access is available)  
- Comparing EPEN aggregated indicators with ENAHO individual-level estimates  
- Extending the analysis to:
  - Gender  
  - Urban vs rural domains  
  - Informality status  
- Incorporating confidence intervals if future releases allow variance estimation  

---

## Repository Structure

```text
├── notebooks
│   └── 01_empleo_juvenil_epen.ipynb
├── figures
│   └── employment_adequacy_2022_2025.png
├── README.md
