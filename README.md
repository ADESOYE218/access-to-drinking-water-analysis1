# access-to-drinking-water-analysis1
Data analysis project investigating global access to drinking water in 2020 using population size, urbanisation, water service levels, and income groups.
# Access to Drinking Water Analysis — 2020

## 📌 Project Overview

This project investigates **global access to drinking water in 2020**, using population size, urbanisation, water-service levels, and income groups to explore differences in access to drinking-water services.

The project is based on the **WHO/UNICEF Joint Monitoring Programme (JMP) Estimates on the Use of Water dataset for 2020**. The analysis was completed using Google Sheets, including data cleaning, calculations, descriptive statistics, pivot tables, and data visualisations.

## The project is aligned with **United Nations Sustainable Development Goal 6 (SDG 6): Clean Water and Sanitation**, which focuses on ensuring the availability and sustainable management of water and sanitation for all.

## 🎯 Project Objectives

The main objectives of this project were to:

* Understand and prepare the 2020 drinking-water dataset.
* Compare the dataset population with estimated global population figures.
* Analyse the distribution of urban and rural populations.
* Investigate drinking-water access at national, rural, and urban levels.
* Examine the central tendency and spread of water-access data.
* Explore the relationship between population size and water-access levels.
* Investigate differences in water access across income groups.
* Create meaningful visualisations to communicate the findings.

These objectives follow the structure of the integrated project, which includes population size, access by area, access by population size, and access by income group.


## 📊 Dataset

The analysis uses the **WHO/UNICEF Joint Monitoring Programme (JMP) Estimates on the Use of Water dataset for 2020**.

The original dataset contains **16 features**, including population information and water-service-level percentages.

### Main variables

| Variable       | Description                                          |
| -------------- | ---------------------------------------------------- |
| `name`         | Country or area name                                 |
| `income_group` | Country's income-group classification                |
| `pop_n`        | National population estimate, in thousands           |
| `pop_u`        | Urban population share (%)                           |
| `wat_bas_n`    | National share with at least basic water service (%) |
| `wat_lim_n`    | National share with limited water service (%)        |
| `wat_unimp_n`  | National share with unimproved water service (%)     |
| `wat_sur_n`    | National share using surface water (%)               |
| `wat_bas_r`    | Rural share with at least basic water service (%)    |
| `wat_lim_r`    | Rural share with limited water service (%)           |
| `wat_unimp_r`  | Rural share with unimproved water service (%)        |
| `wat_sur_r`    | Rural share using surface water (%)                  |
| `wat_bas_u`    | Urban share with at least basic water service (%)    |
| `wat_lim_u`    | Urban share with limited water service (%)           |
| `wat_unimp_u`  | Urban share with unimproved water service (%)        |
| `wat_sur_u`    | Urban share using surface water (%)                  |

The dataset contains four service levels rather than five because **“at least basic” combines safely managed and basic services**.


## 🧹 Data Preparation

Several data-cleaning and transformation steps were completed before analysis.

### Data cleaning

The original CSV data contained semicolon-separated values in some rows, which caused several records to be imported incorrectly. These rows were identified and corrected using the `value_cnt` feature and filtering.

### Additional calculated features

The spreadsheet was expanded with additional features, including:

* `value_cnt`
* `pop_u_val`
* `pop_r`
* `pop_n (m)`
* `wat_bas_n (rounded)`
* `pop_u (rounded)`
* `pop_r (rounded)`

This resulted in **23 features** in the completed dataset.

### Population calculations

`pop_u_val` was calculated to estimate the actual number of people living in urban areas for each country. `pop_r` was calculated as the rural population share, based on the assumption that urban and rural shares together equal 100%.

### Handling water-access values

A rounded basic-water-access feature was created to handle values exceeding the logical maximum of 100%. Some resulting errors were converted to `NAN` so that the statistical calculations could be completed correctly.


# 🔎 Key Findings

## 1. Population Comparison

The dataset's population totals were compared with estimated global population figures for 2020.

| Measure                                  |             Value |
| ---------------------------------------- | ----------------: |
| Estimated world population               |     7,821,000,000 |
| Dataset national population              |     7,786,695,108 |
| Estimated world urban population         |     4,301,550,000 |
| Dataset urban population                 |     4,375,308,463 |
| Percentage difference — total population |         **0.44%** |
| Percentage difference — urban population |         **1.70%** |
| Population difference                    |    **34,304,892** |
| Average population                       | **7,803,847,554** |

The dataset's national population is very close to the estimated world population, with a difference of approximately **0.44%**. The difference for the urban population is approximately **1.70%**.

## The project used an estimated 2020 world population of **7.821 billion** and an estimated global urban share of **55%** for comparison.

## 2. Water Access by Area

The analysis compared water access at **national, rural, and urban** levels.

### Average water-access levels

| Service level | National (%) | Rural (%) | Urban (%) |
| ------------- | -----------: | --------: | --------: |
| Basic         |    **89.86** | **81.34** | **94.69** |
| Limited       |         3.87 |      5.84 |      3.28 |
| Unimproved    |         4.42 |      8.73 |      1.72 |
| Surface       |         1.92 |      4.22 |      1.72 |

### Key observations

* Urban areas had the **highest average basic water access**, at **94.69%**.
* Rural areas had a considerably lower average basic access level of **81.34%**.
* The difference between urban and rural basic access was approximately **13.35 percentage points**.
* Rural areas had higher average levels of **limited, unimproved, and surface-water access**.
* Unimproved water access averaged **8.73% in rural areas**, compared with only **1.72% in urban areas**.
* Surface-water access averaged **4.22% in rural areas**, compared with **1.72% in urban areas**.

These results indicate that the type of area is an important factor when examining access to drinking water. The project specifically investigates national, rural, and urban service levels using measures of central tendency and spread.


## 3. Distribution and Variability of Water Access

Descriptive statistics were calculated for all **12 water-access features**, covering national, rural, and urban service levels. These included the maximum, minimum, mean, median, mode, first quartile, third quartile, interquartile range (IQR), and standard deviation.

### Selected results

| Service level | Area     | Mean (%) | Median (%) |       IQR | Standard Deviation |
| ------------- | -------- | -------: | ---------: | --------: | -----------------: |
| Basic         | National |    89.86 |      97.35 |     14.24 |              15.09 |
| Basic         | Rural    |    81.34 |      90.73 | **34.29** |          **21.51** |
| Basic         | Urban    |    94.69 |      98.11 |  **7.39** |           **8.04** |
| Limited       | National |     3.87 |       0.47 |      4.85 |               6.96 |
| Limited       | Rural    |     5.84 |       1.81 |      8.55 |               8.70 |
| Limited       | Urban    |     3.28 |       0.50 |      3.97 |               5.64 |
| Unimproved    | National |     4.42 |       0.85 |      5.25 |               7.17 |
| Unimproved    | Rural    |     8.73 |       3.23 | **13.11** |          **11.83** |
| Unimproved    | Urban    |     1.72 |       0.35 |      2.06 |               3.23 |
| Surface       | National |     1.92 |       0.00 |      1.88 |               3.92 |
| Surface       | Rural    |     4.22 |       0.22 |      6.16 |               6.85 |
| Surface       | Urban    |     1.72 |       0.35 |  **0.16** |           **0.87** |

### Key observations

* The national basic-service mean was **89.86%**, while the median was **97.35%**, showing that many countries had high basic access.
* Rural basic access had the greatest variability, with an **IQR of 34.29** and standard deviation of **21.51**.
* Urban basic access was much less variable, with an **IQR of 7.39** and standard deviation of **8.04**.
* Rural areas consistently showed greater variation across the lower water-service levels.
* The mode for basic access was **100%** across national, rural, and urban basic-service distributions.

A box-and-whisker visualisation was created to compare the distributions of all 12 water-access features.


## 4. Water Access by Population Size

The project also investigated whether water-service levels varied according to population size.

Three **100% stacked column charts** were created to compare:

* National population size versus the four national water-service levels.
* Urban population share versus the four urban water-service levels.
* Rural population share versus the four rural water-service levels.

Population values were rounded or aggregated where necessary to make the visualisations easier to interpret without removing data from the dataset.

### Visualisation approach

The 100% stacked format was appropriate because the four service levels represent percentages that together describe the distribution of water-service access.

For urban and rural analysis, population shares were rounded to whole numbers and aggregated using averages to make the charts more readable.

The analysis provides a way to explore whether differences in water access are associated with population size or with the proportion of a country's population living in urban or rural areas.


# 💰 5. Water Access by Income Group

The project used a pivot table to investigate the relationship between **income group, population size, urbanisation, and national water access**. The income groups were converted to numerical values to make them easier to order and visualise.

### Income-group coding

| Code | Income Group        |
| ---: | ------------------- |
|    0 | NAN / Unidentified  |
|    1 | Low income          |
|    2 | Lower middle income |
|    3 | Upper middle income |
|    4 | High income         |

### Income-group results

| Income Group        |   Population* | Basic Access (%) | Limited (%) | Unimproved (%) | Surface Water (%) | Urban Population (%) |
| ------------------- | ------------: | ---------------: | ----------: | -------------: | ----------------: | -------------------: |
| NAN                 |        37,264 |            97.18 |        0.15 |           2.39 |              0.32 |                61.46 |
| Low income          |       590,425 |            62.82 |       16.55 |          15.21 |              5.42 |                36.04 |
| Lower middle income |     3,399,310 |            82.21 |        5.69 |           7.90 |              4.29 |                48.79 |
| Upper middle income |     2,547,619 |            96.43 |        1.56 |           1.48 |              0.57 |                64.69 |
| High income         |     1,212,076 |        **99.56** |        0.18 |           0.24 |              0.02 |            **79.36** |
| **Grand Total**     | **7,786,695** |        **89.86** |    **3.87** |       **4.42** |          **1.92** |            **61.89** |

*Population is represented using the dataset's `pop_n` values, which are in thousands. The table values are therefore displayed in thousands.

### Key observations

* **High-income countries** had the highest average basic water access at **99.56%**.
* High-income countries also had the highest average urban population share at **79.36%**.
* **Low-income countries** had the lowest average basic water access at **62.82%**.
* Low-income countries had the lowest average urban population share at **36.04%**.
* Low-income countries had the highest average:

  * **Limited access:** 16.55%
  * **Unimproved access:** 15.21%
  * **Surface-water access:** 5.42%
* Upper-middle-income countries had a high average basic access level of **96.43%**.
* Lower-middle-income countries had an average basic access level of **82.21%**.
* The unidentified/NAN group had a high average basic access value of **97.18%**, but these records do not have an identified income classification.

### Overall income-group insight

The analysis shows a strong pattern in the dataset: **higher-income groups generally have higher average basic drinking-water access and lower average shares of limited, unimproved, and surface-water access**.

There is also an observable relationship between income group and urbanisation. The higher-income groups have higher average urban population shares, while the lower-income group has a substantially lower urban share.

## The pivot-table analysis was specifically designed to compare population totals, average urban population share, and average national water-service levels across income groups.

# 📈 Visualisations

The completed analysis includes the following visualisations:

### 1. Population Comparison

Comparison of:

* Estimated world population
* Dataset population
* Estimated urban population
* Dataset urban population

### 2. Urban vs Rural Population

A line chart comparing national population size with urban and rural population shares.

### 3. Water Access Distribution

A box-and-whisker chart comparing the five-number summaries and distributions of all 12 national, rural, and urban water-service features.

### 4. National Water Access vs Population

A 100% stacked column chart comparing national population size with the four national water-service levels.

### 5. Urban Water Access vs Population Share

A 100% stacked column chart comparing urban population share with urban water-service levels.

### 6. Rural Water Access vs Population Share

A 100% stacked column chart comparing rural population share with rural water-service levels.

### 7. Income Group Analysis

A visualisation of the pivot-table results comparing income groups with population, urbanisation, and water-service levels.

The project instructions specify these three 100% stacked charts and the income-group visualisation as part of the completed analysis.



# 🧮 Statistical Analysis

The following descriptive statistics were used:

* Maximum
* Minimum
* Mean
* Median
* Mode
* First quartile (Q1)
* Third quartile (Q3)
* Interquartile range (IQR)
* Standard deviation
* Range

These measures were used to understand both the **central tendency** and **spread** of drinking-water access across national, rural, and urban areas.


# 🛠️ Tools & Skills

### Tools

* **Google Sheets**
* Spreadsheet formulas
* Pivot tables
* Data filters
* Data visualisation

### Skills demonstrated

* Data cleaning
* Data transformation
* Exploratory data analysis
* Descriptive statistics
* Population analysis
* Percentage calculations
* Data aggregation
* Pivot-table analysis
* Data visualisation
* Interpretation of statistical results
* Analytical storytelling

### Google Sheets functions used

Examples of spreadsheet functions used during the project include:

* `COUNTA()`
* `IF()`
* `IFERROR()`
* `ROUND()`
* `ROUNDUP()`
* `MAX()`
* `MIN()`
* `AVERAGE()`
* `MEDIAN()`
* `MODE()`
* `QUARTILE()`
* `STDEV()`
* `ABS()`


# 🌍 Connection to SDG 6

This project relates directly to **United Nations Sustainable Development Goal 6: Clean Water and Sanitation**.

SDG 6 focuses on ensuring access to water and sanitation for all. By analysing drinking-water access across countries, population sizes, urban and rural areas, and income groups, this project highlights differences in access to basic water services and the populations that experience lower levels of service.

The project therefore provides a data-driven way of exploring one aspect of global water inequality.



# 📁 Repository Structure

```text
access-to-drinking-water-analysis/
│
├── README.md
│
├── data/
│   └── Estimates-on-the-use-of-water-2020.csv
│
├── analysis/
│   └── Access-to-Drinking-Water-2020.xlsx
│
└── visualisations/
    ├── population-analysis
    ├── water-access-analysis
    └── income-group-analysis


> **Note:** Update the filenames/folders above to match the exact files you decide to upload to GitHub.



# 📌 Project Status

**Completed**

The project includes:

* Data import and cleaning
* Feature creation and transformation
* Population comparison
* Urban and rural population analysis
* National water-access analysis
* Descriptive statistical analysis
* Box-and-whisker visualisation
* Population-size analysis
* National, urban, and rural 100% stacked charts
* Income-group pivot-table analysis
* Income-group visualisation
* Interpretation of findings

The completed spreadsheet contains the original dataset features together with the additional calculated features required for the analysis.


# 💡 Overall Conclusion

The analysis demonstrates that access to drinking water varies considerably across **area type, population characteristics, and income groups**.

At the national level, the average basic water-service access was approximately **89.86%**. However, the results reveal a clear difference between urban and rural areas: urban areas had a higher average basic access level (**94.69%**) than rural areas (**81.34%**).

The income-group analysis shows an even stronger pattern. **High-income countries averaged 99.56% basic water access**, while **low-income countries averaged 62.82%**. Low-income countries also had substantially higher average shares of limited, unimproved, and surface-water access.

Overall, the findings suggest that **income level and area type are important factors associated with differences in drinking-water access within this dataset**. Higher-income and more urbanised groups generally show greater access to basic water services, while lower-income and rural populations show greater exposure to lower service levels.



# 📚 Data Source

**WHO/UNICEF Joint Monitoring Programme (JMP) — Estimates on the Use of Water, 2020**

The project dataset and analysis follow the structure and methodology provided in the ExploreAI integrated project **“Access to drinking water.”**



Data Analysis Project — Access to Drinking Water, 2020
