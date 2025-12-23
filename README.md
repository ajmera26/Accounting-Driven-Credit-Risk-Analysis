# Accounting-Driven Credit Risk Analysis

## Overview

This project analyses corporate financial statement data to assess **bankruptcy risk** using a deliberately small and interpretable set of **accounting-based financial ratios**.

The objective is to identify key financial drivers of corporate distress while maintaining **model transparency**, which is critical in regulated banking and credit-risk environments. The analysis prioritises **financial reasoning and explainability** over algorithmic complexity.

---

## Data Source

- **Dataset:** Taiwanese Bankruptcy Prediction Dataset  
- **Source:** UCI Machine Learning Repository  
- **Observations:** 6,819 firms  
- **Target variable:** `Bankrupt?` (binary indicator of corporate bankruptcy)  
- **Class imbalance:** ~3.2% bankrupt firms  

The dataset consists entirely of **anonymised accounting-derived ratios** and is used for academic and portfolio demonstration purposes.

---

## Methodology

### Accounting-Led Feature Selection

Rather than using all available variables, the model focuses on a compact set of ratios spanning standard credit-analysis dimensions.

**Profitability**
- ROA (after tax)  
- Operating profit rate  
- Operating gross margin  

**Liquidity**
- Working capital relative to equity  
- Current liabilities relative to total liabilities  

**Leverage**
- Total debt relative to net worth  
- Interest-bearing debt interest rate  

**Cash Flow & Earnings Quality**
- Cash flow rate  
- Operating funds to liabilities  
- Retained earnings to total assets  

This restrained feature selection improves **interpretability, stability, and governance**, which are essential in credit-risk modelling.

---

### Modelling Approach

- **Model:** Logistic Regression  
- **Rationale:**
  - Transparent and interpretable coefficients  
  - Widely used in credit-risk applications  
  - Suitable for highly imbalanced datasets  

- **Imbalance handling:** Class-weighted loss function  

- **Evaluation metric:** ROC–AUC  

---

## Results

- **Test ROC–AUC:** **0.88**, indicating strong discriminatory power despite significant class imbalance.
- The model intentionally prioritises **recall of bankrupt firms**, reflecting credit-risk practice where failing to identify distressed entities is more costly than generating false positives.

---

### Key Drivers of Bankruptcy Risk

#### Strongest Risk-Reducing Factors (Negative Coefficients)

- **ROA (after tax)** – strong profitability significantly reduces distress risk  
- **Working capital / equity** – liquidity buffers improve firm resilience  
- **Cash flow rate** – cash generation is a critical survival signal  
- **Operating gross margin** – business model strength and pricing power  
- **Retained earnings / total assets** – long-term capital accumulation  

#### Strongest Risk-Increasing Factors (Positive Coefficients)

- **Operating profit rate** – very high values likely reflect volatility rather than stability  
- **Total debt / total net worth** – higher leverage increases insolvency risk  
- **Operating funds / liability** – weak standalone effect but directionally consistent  

Coefficient estimates are interpreted with **accounting judgement**, recognising that financial ratios can exhibit dataset-specific and conditional relationships rather than direct economic causality.

---

## How to Run

1. Clone the repository  
2. Install required packages listed in `requirements.txt`  
3. Run notebooks sequentially from the `notebooks/` directory  

All file paths are relative and platform-independent.

---

## Limitations

- Bankruptcy is used as a **proxy for credit default**, not a loan-level outcome  
- No macroeconomic or forward-looking variables included  
- Static, cross-sectional analysis  

These design choices were intentional to maintain clarity and interpretability.

---

## Planned Extensions

- Incorporation of macroeconomic indicators  
- Stress-testing under adverse scenarios  
- Extension towards an **IFRS-9-style Expected Credit Loss (ECL)** framework  
- Comparison with tree-based models while preserving explainability  

---

## Skills Demonstrated

- Financial statement analysis  
- Credit-risk reasoning  
- Interpretable machine learning  
- Handling imbalanced financial datasets  
- Risk governance and model transparency  

---

### Final Note

This project emphasises **financial intuition, accounting judgement, and explainability**, aligning closely with how credit-risk models are evaluated and governed in real banking environments.
