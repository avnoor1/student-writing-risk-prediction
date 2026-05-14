# Student Writing Risk Prediction — Early Literacy Analytics

Predicting which primary school students are at risk of writing 
difficulties in Year 3, using early literacy, numeracy, 
socioeconomic, and disability data collected across Years 1 and 2.

## Business Problem

Early identification of at-risk students allows schools to deploy 
targeted interventions before writing difficulties become entrenched 
and harder to reverse. This analysis explores which early indicators 
— measurable in Kindergarten and Year 1 — most reliably predict 
Year 3 writing risk.

## Dataset

2,000 Australian primary school students across cohort years 
2016–2021. Features include Burt and Clay reading scores, text 
levels, writing vocabulary, numeracy assessments (counting, place 
value, addition, multiplication), socioeconomic status (SES), 
family background, disability classification, and NCCD funding status.

## Key Findings

- Students with low writing vocabulary at school entry (mean score 
  15.8) are significantly more likely to be at risk in Year 3 
  compared to non-at-risk students (mean 25.1) — Mann-Whitney U 
  test confirms this is highly significant (p < 0.0001)
- Cognitive disability is the strongest disability-related risk 
  factor — 54.8% of cognitively disabled students are flagged 
  as at-risk versus 25.6% of non-disabled students
- Early Burt reading scores show moderate negative correlation 
  (-0.36) with writing risk — stronger readers in Year 1 are 
  meaningfully less likely to struggle in Year 3
- SES shows a consistent relationship with outcomes across both 
  Year 1 and Year 2 cohorts
- Literacy and numeracy skills are positively correlated, 
  suggesting shared underlying developmental factors

## Models Built

| Model | Accuracy | ROC-AUC | F1 Score |
|---|---|---|---|
| Gradient Boosting | 71% | 0.74 | 0.46 |
| K-Nearest Neighbors | 67% | — | 0.45 |

K-Means clustering (k=3) used to identify natural student 
groupings across literacy and numeracy dimensions.

## Tools & Libraries

Python · pandas · NumPy · scikit-learn · seaborn · matplotlib · SciPy

## Project Structure

AvnoorThind.ipynb    # Full analysis: EDA, statistical testing, 
                     # classification models and clustering

## Limitations & Next Steps

- Class imbalance (~37% at-risk) limits F1 performance — 
  future work would apply SMOTE or class weighting
- Feature importance analysis would clarify which early 
  assessments carry most predictive weight
- External validation on a held-out school cohort would 
  strengthen generalizability claims
