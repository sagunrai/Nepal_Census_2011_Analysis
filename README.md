<a id="top"></a>

<div align="center">

# Nepal Census 2011: Data Mining Project

**Exploring population, migration, housing, education and mortality in Nepal's 2011 census**

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-data%20analysis-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-classification-F7931E?logo=scikitlearn&logoColor=white)

[📄 Read the full report (PDF)](Nepal_Census_2011_Project_Report.pdf) ·
[📓 Browse the notebooks](Notebooks/)

</div>

---

<a id="contents"></a>

## Contents

- [About](#about)
- [Key findings at a glance](#key-findings)
- [Explore the results](#explore-results) (click each section to expand)
- [Model results](#model-results)
- [Methodology](#methodology)
- [Project structure](#project-structure)
- [How to run](#how-to-run)
- [Limitations](#limitations)

---

<a id="about"></a>

## About

This project analyses the **2011 Nepal Population and Housing Census**, published by the Central Bureau of Statistics (CBS) Nepal.

The goal is to turn raw census records into insights that can support planning and policy, using exploratory data analysis (EDA), visualisation and simple classification models.

**Questions the project answers**

| Type | Example question |
|------|------------------|
| Descriptive | How many households, deaths and absentees are there in each district? |
| Diagnostic | Why are absentees concentrated in certain age groups and destinations? |
| Predictive | Can we predict the reason for absence, or the type of house ownership? |
| Comparative | How do urban and rural areas, or ecological belts, differ? |

[⬆ Back to contents](#contents)

---

<a id="key-findings"></a>

## Key findings at a glance

| Area | Finding |
|------|---------|
| 🧳 **Absentees** | Most absentees are men (about 250,000 men vs 35,000 women in the charts), and ages 21 to 30 are the largest group. |
| 💼 **Why they leave** | Private-sector jobs are by far the main reason, followed by institutional jobs, being a dependent, and study. |
| 🌍 **Where they go** | The Middle East and India are the top destinations, followed by ASEAN countries. |
| 🏠 **Housing** | Most households own their home. Mud-bonded brick or stone walls and galvanized-iron roofs are the most common. |
| 🔥 **Energy** | Firewood is the main cooking fuel. Electricity is the main source of lighting. |
| 👩 **Women and land** | Most households have no female land owner. |
| ⚰️ **Mortality** | Kathmandu records the most deaths. Elderly people (60+) account for the most deaths. Of deceased persons, about 56% are male and 43% female. |
| 🏙️ **Urban vs rural** | Rural VDCs far outnumber urban municipalities, both nationally and in Kathmandu district. |

[⬆ Back to contents](#contents)

---

<a id="explore-results"></a>

## Explore the results

> Click a section to expand it. All charts are in the [full report](Nepal_Census_2011_Project_Report.pdf).

<details>
<summary><b>🗺️ 1. Administrative geography</b></summary>

<br>

Maps every VDC/municipality to its district, development region, ecological belt and urban/rural type.

- Nepal has **75 districts**: 39 in the Hill belt, 20 in the Terai and 16 in the Mountain belt.
- Rural areas dominate. Kathmandu district has far more rural VDCs than urban ones.

</details>

<details>
<summary><b>🧳 2. Absentees: migration and absence</b></summary>

<br>

Household members who were away from home at the time of the census, mostly abroad.

- Young men aged **21 to 30** are the largest group.
- **Private service or job** is the leading reason by a wide margin.
- The **Middle East** and **India** are the top destinations.
- Business-related absences last longest on average, and most absences are under five years.

</details>

<details>
<summary><b>🏠 3. Households: housing and land ownership</b></summary>

<br>

Housing type, building materials, utilities, house ownership and female land ownership.

- Most houses are **owned**, and **rented** is the second largest group.
- **Mud-bonded brick or stone** is the most common wall type and **galvanized iron** the most common roof.
- **Tap or piped water** is the leading drinking-water source, followed by tubewells.
- **Firewood** is the main cooking fuel, ahead of LP gas. **Electricity** is the main lighting source.
- Most households have **no female land owner**.

</details>

<details>
<summary><b>👤 4. Individuals: education, religion, work and disability</b></summary>

<br>

Person-level records linked to households.

- **Class 5** and **SLC or equivalent** are the most common education levels.
- **Hindu** is the largest religion, followed by Buddhist, Islam, Kirat and Christian.
- **Skilled agriculture, forestry and fishery workers** are the largest occupation group.
- **Own-account workers** are the largest employment-status group, followed by employees.
- The vast majority of individuals are recorded as not disabled.

</details>

<details>
<summary><b>⚰️ 5. Deaths: mortality patterns</b></summary>

<br>

Deaths recorded in the 12 months before the census.

- **Kathmandu** has the most recorded deaths.
- Deaths rise sharply with age: **60+** is the largest group, then adults aged 15 to 59, then children.
- About **55.9% male**, **43.0% female** and 1.1% not stated.
- The district mortality rate per 100 households is highest in districts such as **Kalikot** and **Terhathum**.

</details>

[⬆ Back to contents](#contents)

---

<a id="model-results"></a>

## Model results

Two classifiers were trained. Accuracy and recall below are calculated from the confusion matrices in the report.

| Task | Accuracy | Majority-class baseline | Best class | Weakest classes |
|------|----------|-------------------------|-----------|-----------------|
| Predict **reason of absence** | 73.4% | 72.2% (always "Pvt. service/job") | Pvt. service/job: 93% recall | Business, Conflict and Others are almost never predicted correctly |
| Predict **house ownership** (Decision Tree) | 86.6% | 84.3% (always "Own") | Own: 96% recall | Rented: 40% recall. Institutional and Others are rarely identified |

**What this means:** both models beat the baseline only slightly. The data is heavily imbalanced, so the models mostly learn to predict the biggest class. Better results would need class balancing (for example class weights or resampling) and more informative features.

[⬆ Back to contents](#contents)

---

<a id="methodology"></a>

## Methodology

```mermaid
flowchart LR
    A[Raw census<br/>records] --> B[Cleaning<br/>missing values, duplicates]
    B --> C[Transformation<br/>encoding, grouping]
    C --> D[EDA<br/>statistics and distributions]
    D --> E[Visualisation<br/>matplotlib, seaborn]
    E --> F[Classification<br/>Decision Tree and others]
    F --> G[Insights and report]
```

- **Language and libraries:** Python, pandas, numpy, matplotlib, seaborn, plotly, pyreadstat, scikit-learn
- **EDA:** descriptive statistics, distributions, grouping and aggregation by district, region and ecological belt
- **Modelling:** classification of reason of absence and of house ownership type

[⬆ Back to contents](#contents)

---

<a id="project-structure"></a>

## Project structure

```
.
├── Notebooks/                              # Jupyter notebooks, one per topic
├── Nepal_Census_2011_Project_Report.pdf    # Full project report
├── .gitignore
└── README.md
```

[⬆ Back to contents](#contents)

---

<a id="how-to-run"></a>

## How to run

```bash
# 1. Clone the repository
git clone https://github.com/sagunrai/Nepal_Census_2011_Analysis.git
cd Nepal_Census_2011_Analysis

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn plotly scikit-learn pyreadstat jupyter

# 3. Start Jupyter and open a notebook
jupyter notebook
```

[⬆ Back to contents](#contents)

---

<a id="limitations"></a>

## Limitations

- Both classification models are dominated by the largest class, so their accuracy is only slightly above a naive baseline.
- Results describe 2011 only. Nepal has changed administratively since then (VDCs were replaced by municipalities and rural municipalities), so district and VDC names may not match current boundaries.

[⬆ Back to top](#top)
