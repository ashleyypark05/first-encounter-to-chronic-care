# ASA DataFest 2026 — Healthcare Access & Patient Journey Analysis

Analysis of Stormont Vail Health patient data exploring provider access gaps, patient return patterns, and social determinants of health across census block groups in Kansas.

**Competition:** ASA DataFest 2026

---

## Research Questions

1. **Patient return patterns** — Which age-diagnosis combinations produce the highest rates of multiple-visit patients, and does the system retain patients who need ongoing care?

2. **Provider access gaps** — Are there geographic clusters with insufficient provider coverage (population-to-provider ratio > 3,500)?

3. **Social determinants** — Where is social burden concentrated geographically, and how does it relate to healthcare engagement?

---

## Notebook Summary

| Notebook | Description |
|---|---|
| `01_eda.ipynb` | Visit frequency overview, age/diagnosis distributions, return-rate heatmap by age x ICD-10 chapter |
| `02_access_gaps.ipynb` | Population-weighted DBSCAN clustering, KNN provider assignment, interactive Folium gap maps |
| `03_hypothesis_testing.ipynb` | 6 chi-square tests: age, diagnosis type, admission type, and interactions |
| `04_social_determinants.ipynb` | Social risk framework, domain prevalence, geographic concentration, MyChart engagement patterns |

---

## Key Findings

- **65+ patients with symptom-based diagnoses (ICD-10 R) have the highest return rates.** Young adults (21–39) return at significantly lower rates even when presenting with conditions requiring follow-up — all six hypothesis tests were statistically significant.
- **Several geographic clusters exceed the 3,500 population-per-provider threshold**, with single-visit patients in gap areas showing higher rates of chronic-condition diagnoses (E, M, I) that would typically require follow-up.
- **Social burden is concentrated in ~6.8% of the patient population**, with physical inactivity, stress, and utilities hardship appearing most frequently. Many patients face multiple simultaneous barriers, and burden is geographically clustered in specific census block groups.

---

## Methods

- **DBSCAN** (density-based spatial clustering, haversine metric) for population-weighted geographic cluster identification
- **BallTree KNN** for assigning providers to nearest population cluster
- **Chi-square tests** of independence for categorical visit-conversion hypotheses
- **Social risk flagging** for SDOH domain burden classification
- **Folium** for interactive geographic maps

---

## Setup

```bash
git clone https://github.com/your-username/datafest-2026-healthcare.git
cd datafest-2026-healthcare
pip install -r requirements.txt
```
