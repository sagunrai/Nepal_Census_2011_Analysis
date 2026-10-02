<div align="center">

# Nepal Census 2011: Data Mining Project

**Exploring population, migration, housing, education and mortality in Nepal's 2011 census**

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-data%20analysis-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-classification-F7931E?logo=scikitlearn&logoColor=white)
![Data](https://img.shields.io/badge/Data-CBS%20Nepal%20Census%202011-green)

[📄 Read the full report (PDF)](Nepal_Census_2011_Project_Report.pdf) ·
[📥 Download the data](DATA_LINK) ·
[📓 Browse the notebooks](Notebooks/)

</div>

---

## 📑 Contents

- [About](#-about)
- [Key findings at a glance](#-key-findings-at-a-glance)
- [Explore the results](#-explore-the-results) (click each section to expand)
- [Model results](#-model-results)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Project structure](#-project-structure)
- [How to run](#-how-to-run)
- [Limitations](#-limitations)
- [Authors](#-authors)

---

## 📌 About

This project analyses the **2011 Nepal Population and Housing Census**, published by the Central Bureau of Statistics (CBS) Nepal. It was done for **Data Mining (AICC 301)** at the Department of Artificial Intelligence, Kathmandu University.

The goal is to turn raw census files into insights that can support planning and policy, using exploratory data analysis (EDA), visualisation and simple classification models.

**Questions the project answers**

| Type | Example question |
|------|------------------|
| Descriptive | How many households, deaths and absentees are there in each district? |
| Diagnostic | Why are absentees concentrated in certain age groups and destinations? |
| Predictive | Can we predict the reason for absence, or the type of house ownership? |
| Comparative | How do urban and rural areas, or ecological belts, differ? |

---

## ⚡ Key findings at a glance

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

---

## 🔍 Explore the results

> Click a section to expand it. Each section matches one dataset.

<details>
<summary><b>🗺️ 1. BatchId: administrative geography</b></summary>

<br>

Maps every VDC/municipality to its district, development region, ecological belt and urban/rural type.

- Nepal has **75 districts**: 39 in the Hill belt, 20 in the Terai and 16 in the Mountain belt.
- Rural areas dominate. Kathmandu district has far more rural VDCs than urban ones.

<p align="center">
  <img src="images/batch_districts_per_ecological_belt.png" width="48%" alt="Districts per ecological belt">
  <img src="images/batch_nepal_urban_rural.png" width="48%" alt="Urban vs rural VDCs in Nepal">
</p>

<details>
<summary>More charts</summary>

<p align="center">
  <img src="images/batch_vdcs_per_district.png" width="90%" alt="VDCs per district"><br>
  <img src="images/batch_urban_rural_per_district.png" width="90%" alt="Urban and rural per district"><br>
  <img src="images/batch_kathmandu_urban_rural.png" width="60%" alt="Kathmandu urban vs rural"><br>
  <img src="images/batch_districts_per_eco_dev_region.png" width="80%" alt="Districts per eco-development region"><br>
  <img src="images/batch_urban_rural_per_eco_dev_region.png" width="90%" alt="Urban and rural per eco-development region">
</p>

</details>

</details>

<details>
<summary><b>🧳 2. Absentee: migration and absence</b></summary>

<br>

Household members who were away from home at the time of the census, mostly abroad.

- Young men aged **21 to 30** are the largest group.
- **Private service or job** is the leading reason by a wide margin.
- The **Middle East** and **India** are the top destinations.
- Business-related absences last longest on average, and most absences are under five years.

<p align="center">
  <img src="images/absentee_age_groups.png" width="48%" alt="Absentees by age group">
  <img src="images/absentee_by_destination.png" width="48%" alt="Absentees by destination">
</p>
<p align="center">
  <img src="images/absentee_by_reason.png" width="48%" alt="Absentees by reason">
  <img src="images/absentee_by_sex.png" width="48%" alt="Absentees by sex">
</p>

<details>
<summary>More charts</summary>

<p align="center">
  <img src="images/absentee_by_district.png" width="90%" alt="Absentees by district"><br>
  <img src="images/absentee_age_distribution.png" width="70%" alt="Age distribution of absentees"><br>
  <img src="images/absentee_by_education.png" width="90%" alt="Absentees by education level"><br>
  <img src="images/absentee_duration_distribution.png" width="70%" alt="Duration of absence"><br>
  <img src="images/absentee_district_reason.png" width="90%" alt="Absentees by district and reason"><br>
  <img src="images/absentee_avg_duration_by_district.png" width="90%" alt="Average duration by district"><br>
  <img src="images/absentee_avg_duration_by_reason.png" width="70%" alt="Average duration by reason"><br>
  <img src="images/absentee_reason_by_destination.png" width="80%" alt="Reason of absence by destination">
</p>

</details>

</details>

<details>
<summary><b>🏠 3. Household: housing and land ownership</b></summary>

<br>

Housing type, building materials, utilities, house ownership and female land ownership.

- Most houses are **owned**, and **rented** is the second largest group.
- **Mud-bonded brick or stone** is the most common wall type and **galvanized iron** the most common roof.
- **Tap or piped water** is the leading drinking-water source, followed by tubewells.
- **Firewood** is the main cooking fuel, ahead of LP gas. **Electricity** is the main lighting source.
- Most households have **no female land owner**.

<p align="center">
  <img src="images/household_ownership_types.png" width="48%" alt="House ownership types">
  <img src="images/household_female_ownership.png" width="48%" alt="Households by female ownership">
</p>
<p align="center">
  <img src="images/household_cooking_fuel.png" width="48%" alt="Cooking fuel">
  <img src="images/household_lighting.png" width="48%" alt="Source of lighting">
</p>

<details>
<summary>More charts</summary>

<p align="center">
  <img src="images/household_per_district.png" width="90%" alt="Households per district"><br>
  <img src="images/household_roof_wall.png" width="90%" alt="Roof and wall type"><br>
  <img src="images/household_drinking_water.png" width="80%" alt="Source of drinking water"><br>
  <img src="images/household_ownership_by_district.png" width="90%" alt="Ownership type by district"><br>
  <img src="images/household_female_owned_by_district.png" width="90%" alt="Female-owned households by district">
</p>

</details>

</details>

<details>
<summary><b>👤 4. Individual: education, religion, work and disability</b></summary>

<br>

Person-level records linked to households.

- **Class 5** and **SLC or equivalent** are the most common education levels.
- **Hindu** is the largest religion, followed by Buddhist, Islam, Kirat and Christian.
- **Skilled agriculture, forestry and fishery workers** are the largest occupation group.
- **Own-account workers** are the largest employment-status group, followed by employees.
- The vast majority of individuals are recorded as not disabled.

<p align="center">
  <img src="images/individual_religion.png" width="48%" alt="Religion">
  <img src="images/individual_employment_status.png" width="48%" alt="Employment status">
</p>

<details>
<summary>More charts</summary>

<p align="center">
  <img src="images/individual_education_level.png" width="90%" alt="Level of education"><br>
  <img src="images/individual_occupation.png" width="90%" alt="Occupation distribution"><br>
  <img src="images/individual_disability.png" width="80%" alt="Type of disability">
</p>

</details>

</details>

<details>
<summary><b>⚰️ 5. Death: mortality patterns</b></summary>

<br>

Deaths recorded in the 12 months before the census.

- **Kathmandu** has the most recorded deaths.
- Deaths rise sharply with age: **60+** is the largest group, then adults aged 15 to 59, then children.
- About **55.9% male**, **43.0% female** and 1.1% not stated.
- The district mortality rate per 100 households is highest in districts such as **Kalikot** and **Terhathum**.

<p align="center">
  <img src="images/death_by_age_group.png" width="48%" alt="Deaths by age group">
  <img src="images/death_gender_pie.png" width="48%" alt="Gender of deceased persons">
</p>

<details>
<summary>More charts</summary>

<p align="center">
  <img src="images/death_by_district.png" width="90%" alt="Deaths by district"><br>
  <img src="images/death_age_group_per_district.png" width="70%" alt="Deaths by age group per district"><br>
  <img src="images/death_mortality_rate.png" width="90%" alt="District-wise mortality rate per 100 households">
</p>

</details>

</details>

[⬆ Back to top](#nepal-census-2011-data-mining-project)

---

## 🤖 Model results

Two classifiers were trained. Accuracy and recall below are calculated from the confusion matrices in the report.

| Task | Accuracy | Majority-class baseline | Best class | Weakest classes |
|------|----------|-------------------------|-----------|-----------------|
| Predict **reason of absence** | 73.4% | 72.2% (always "Pvt. service/job") | Pvt. service/job: 93% recall | Business, Conflict and Others are almost never predicted correctly |
| Predict **house ownership** (Decision Tree) | 86.6% | 84.3% (always "Own") | Own: 96% recall | Rented: 40% recall. Institutional and Others are rarely identified |

**What this means:** both models beat the baseline only slightly. The data is heavily imbalanced, so the models mostly learn to predict the biggest class. Better results would need class balancing (for example class weights or resampling) and more informative features.

<details>
<summary>📊 View the confusion matrices</summary>

<p align="center">
  <img src="images/absentee_confusion_matrix.png" width="70%" alt="Confusion matrix: reason of absence"><br>
  <img src="images/household_confusion_matrix_decision_tree.png" width="60%" alt="Confusion matrix: decision tree, house ownership">
</p>

</details>

---

## 📦 Dataset

The data comes from the **CBS Nepal National Population and Housing Census 2011** (SPSS `.sav` format). It is too large for the repository, so it is published separately.

**📥 [Download the data](DATA_LINK)**, then extract the files into a `data/` folder next to the notebooks.

| File | Contents | Size |
|------|----------|------|
| `BatchId.sav` | District and VDC codes, development region, ecological belt, urban/rural | 0.25 MB |
| `DEATH.SAV` | Deaths in the 12 months before the census | 0.27 MB |
| `ABSENTEE.SAV` | Household members living away, with destination and reason | 4.7 MB |
| `Household.SAV` | Housing, ownership, utilities, female land ownership | 37 MB |
| `Individual01.SAV` | Person-level demographics, education, occupation | 102 MB |
| `Individual02.SAV` | Person-level demographics, education, occupation | 233 MB |

---

## 🔬 Methodology

```mermaid
flowchart LR
    A[Raw census<br/>.sav files] --> B[Cleaning<br/>missing values, duplicates]
    B --> C[Transformation<br/>encoding, grouping]
    C --> D[EDA<br/>statistics and distributions]
    D --> E[Visualisation<br/>matplotlib, seaborn]
    E --> F[Classification<br/>Decision Tree and others]
    F --> G[Insights and report]
```

- **Language and libraries:** Python, pandas, numpy, matplotlib, seaborn, plotly, pyreadstat, scikit-learn
- **EDA:** descriptive statistics, distributions, grouping and aggregation by district, region and ecological belt
- **Modelling:** classification of reason of absence and of house ownership type

---

## 🗂️ Project structure

```
.
├── Notebooks/                              # Jupyter notebooks, one per dataset
├── images/                                 # Charts used in this README
├── Nepal_Census_2011_Project_Report.pdf    # Full project report
├── .gitignore
└── README.md
```

The `data/` folder is not tracked by Git. See [Dataset](#-dataset).

---

## 🚀 How to run

```bash
# 1. Clone the repository
git clone https://github.com/sagunrai/Nepal_Census_2011_Analysis.git
cd REPO_NAME

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn plotly scikit-learn pyreadstat jupyter

# 3. Download the data and extract it into a data/ folder (see Dataset above)

# 4. Start Jupyter and open a notebook
jupyter notebook
```

Run the notebooks one dataset at a time. If a notebook cannot find a file, check the path it reads from and adjust it to match your `data/` folder.

---

## ⚠️ Limitations

- Both classification models are dominated by the largest class, so their accuracy is only slightly above a naive baseline.
- Some sample sizes in the charts are smaller than the full census totals. See the report for details on which records were used.
- Results describe 2011 only. Nepal has changed administratively since then (VDCs were replaced by municipalities and rural municipalities), so district and VDC names may not match current boundaries.

---

## 👥 Authors

| Name | Role |
|------|------|
| **Sagun Rai** | Author |
| **Aarav Subedi** | Author |
| **Sunil Regmi** | Supervisor, Lecturer, Department of Artificial Intelligence |

Kathmandu University, Department of Artificial Intelligence, Dhulikhel, Kavre.
Submitted 2025-07-03.

**Data source:** Central Bureau of Statistics, Government of Nepal. National Population and Housing Census 2011.

[⬆ Back to top](#nepal-census-2011-data-mining-project)
