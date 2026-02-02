# Recidivism-Audit-Report
# Recidivism Risk Prediction and Fairness Audit

## Project Overview
This project analyzes and audits a machine learning model trained on the **Recidivism__Beginning_2008.csv** dataset, which tracks three-year return-to-prison outcomes for individuals released from New York State correctional facilities.  

The primary goal is to evaluate **predictive performance** while critically assessing **algorithmic fairness**, identifying historical and structural bias, and applying **bias mitigation techniques** consistent with modern AI ethics frameworks.

---

## Objectives
- Build a baseline recidivism prediction model
- Evaluate model performance using accuracy and confusion-matrix metrics
- Audit fairness using quantitative fairness metrics
- Identify proxy variables and historical bias
- Apply pre-processing and post-processing bias mitigation techniques
- Analyze the accuracy–fairness trade-off
- Connect findings to broader AI ethics principles

---

## Dataset
**Source:** NYS Recidivism Dataset  
**Timeframe:** Releases beginning in 2008  
**Target Variable:**  
- `Returned_to_Prison_Within_3_Years` (Binary)

**Key Features Used:**
- Age at Release
- Gender
- Release Year
- County of Indictment

⚠️ *Note:* Several variables act as **proxies for race and socioeconomic status**, requiring careful ethical analysis.

---

## Methods

### Data Preprocessing
- Handling missing values
- Feature selection
- Label encoding for categorical variables (Gender, County)
- Train-test split

### Baseline Model
- Logistic Regression
- Optimized for predictive accuracy

### Fairness Metrics
The following fairness metrics were used to evaluate bias:
- **Statistical Parity Difference (SPD)**
- **Disparate Impact (DI)**
- **Equal Opportunity Difference (EOD)**
- **False Positive Rate (FPR) Disparity**

---

## Bias Mitigation Techniques

### 1. Reweighing (Pre-processing)
- Adjusts training sample weights to balance protected and unprotected groups

### 2. Equalized Odds (Post-processing)
- Adjusts decision thresholds to equalize error rates across groups

---

## Results Summary

| Model Version | Accuracy | Disparate Impact | SPD | EOD |
|--------------|--------|-----------------|-----|-----|
| Baseline | ~61.6% | 0.93 | 0.068 | 0.058 |
| Reweighing | ~61.5% | 0.99 | 0.014 | 0.008 |
| Post-Processing | ~61.8% | 1.00 | 0.000 | 0.000 |

**Key Insight:**  
Significant reductions in bias were achieved with **minimal loss in accuracy**, demonstrating that ethical alignment is a design choice rather than a technical limitation.

---

## Ethical Considerations
This project engages with the following AI ethics principles:
- **Justice & Fairness**: Avoiding discriminatory outcomes
- **Transparency & Due Process**: Highlighting explainability concerns
- **Non-Maleficence**: Preventing feedback loops that reinforce harm
- **Accountability**: Quantifying real-world consequences of misclassification

The findings show that recidivism models often predict **system contact**, not inherent criminal behavior.

---

## Tools and Libraries
- Python
- pandas
- numpy
- scikit-learn
- matplotlib / seaborn
- AI Fairness 360 (AIF360)

---

## References
- Angwin et al. (2016). *Machine Bias*. ProPublica.
- Hardt, Price, & Srebro (2016). *Equality of Opportunity in Supervised Learning*.
- Barocas & Selbst (2016). *Big Data’s Disparate Impact*.
- Chouldechova (2017). *Fair Prediction with Disparate Impact*.
- NIST (2023). *AI Risk Management Framework (AI RMF 1.0)*.
- EU AI Act (2024). *High-Risk AI Systems*.
- Bellamy et al. (2018). *AI Fairness 360 Toolkit*.

---

## Disclaimer
This project is for **educational and research purposes only**.  
The models and findings should **not** be used for real-world judicial or parole decisions without rigorous validation, transparency, and human oversight.

---


