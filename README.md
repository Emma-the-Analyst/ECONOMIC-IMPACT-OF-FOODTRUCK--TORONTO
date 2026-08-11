# Food Truck Economic Impact Study – Toronto

**A Data-Driven Analysis of the Relationship Between Food Trucks and Restaurants in Toronto (1969–2024)**

---

## Table of Contents

1. [Project Abstract](#1-project-abstract)
2. [Stages](#2-stages)
   - [I. Requirement Gathering](#i-requirement-gathering)
     - [i. Objectives](#i-objectives)
     - [ii. Business Problem](#ii-business-problem)
     - [iii. Questions Asked](#iii-questions-asked)
     - [iv. Solution](#iv-solution)
     - [v. Users](#v-users)
     - [vi. Data Source](#vi-data-source)
     - [vii. Data Dictionary](#vii-data-dictionary)
     - [viii. Tools Used](#viii-tools-used)
   - [II. Development (Cleaning and Visualization)](#ii-development-cleaning-and-visualization)
     - [a. Loading Dataset](#a-loading-dataset)
     - [b. Checking for Missing (Null) Values](#b-checking-for-missing-null-values)
     - [c. Checking for Duplicates](#c-checking-for-duplicates)
     - [d. Outliers Check](#d-outliers-check)
     - [e. Data Type Check](#e-data-type-check)
     - [g. Visualization](#g-visualization)
   - [III. Analysis](#iii-analysis)
     - [i. Findings Documentation and Discovery](#i-findings-documentation-and-discovery)
3. [Recommendations](#3-recommendations)
4. [Conclusion](#4-conclusion)






## 1. Project Abstract

This project investigates the economic relationship between food trucks and traditional restaurants in Toronto. Using 55 years of business licensing data, unemployment statistics, and population estimates, we applied econometric modeling to determine whether food trucks compete with or complement brick-and-mortar restaurants.

Our findings reveal a **complementary relationship**—each additional food truck is associated with a **3.5-unit increase** in active restaurants. This challenges the common perception that food trucks threaten traditional restaurants.

The analysis provides data-driven policy recommendations for the **Food Trucks Association of Canada (FTAC)** to support a balanced and thriving local food service industry.


## 2. Stages

### I. Requirement Gathering

#### i. Objectives

- Examine trends in food truck and restaurant activity in Toronto from 1969 to 2024
- Evaluate the relationship between food trucks and restaurants using econometric models
- Determine whether food trucks compete with or complement traditional restaurants
- Provide actionable policy recommendations to industry stakeholders and policymakers

---

#### ii. Business Problem

Traditional restaurant owners perceive food trucks as a significant threat due to:

- **Lower operational costs** – Food trucks pay no rent or property taxes
- **Mobility advantages** – Food trucks can relocate to high-traffic areas
- **Pricing flexibility** – Lower overhead allows competitive pricing

This perception has led to calls for stricter regulations on food truck operations. However, **no empirical evidence exists for Toronto** to support or refute these claims. This study addresses that critical gap.

---

#### iii. Questions Asked

1. Do food trucks cause restaurant closures in Toronto?
2. Is there a complementary or competitive relationship between the two sectors?
3. How do unemployment rates affect food truck and restaurant activity?
4. How does population growth impact the food service industry?
5. What policies can support both food trucks and restaurants?

---

#### iv. Solution

**1. Develop a Model**

Develop a model to analyze the relationship between food trucks and restaurants while controlling for:

- **Unemployment rate** – Proxy for economic activity
- **Population** – Proxy for market size and demand
- **Lagged restaurant count** – To account for historical trends

**2. Build Interactive Visualizations**

Create a **Power BI dashboard** to visualize key trends and relationships in the data.



---

#### v. Users

| User Group | Description |
|------------|-------------|
| **Food Trucks Association of Canada (FTAC)** | Primary stakeholder for policy advocacy and industry support |
| **City of Toronto** | Municipal policymakers and licensing authorities |
| **Food Truck Operators** | Entrepreneurs seeking market insights and growth strategies |
| **Restaurant Owners** | Industry players concerned about competition and market dynamics |
| **Researchers** | Academics studying urban economics, food systems, and small business |

---

#### vi. Data Source

| Data | Source | Period | Link |
|------|--------|--------|------|
| Toronto Business Licensing Data | City of Toronto Open Data Portal | 1969–2024 | [Access Data](https://open.toronto.ca/dataset/municipal-licensing-and-standards-business-licences-and-permits/) |
| Unemployment Statistics | Statistics Canada | 2006–2014 | [Access Data](https://ouvert.canada.ca/data/dataset/ee0c0ab7-4897-494b-a1f7-0bf0e919f126/resource/7f4caf1f-fd62-4986-b228-a9ec52e1c1e) |
| Population Estimates | Statistics Canada | 2001–2023 | [Access Data](https://www150.statcan.gc.ca/t1/tbl1/en/cv.action?pid=1710015501) |

---

#### vii. Data Dictionary

**Municipal Licensing and Standards – Business Licences and Permits**

| Column | Description | Data Type |
|--------|-------------|-----------|
| `_id` | Unique row identifier for Open Data database | Integer |
| `Category` | Type of license or permit | String |
| `Licence No.` | Number of licenses issued by City of Toronto | Integer |
| `Operating Name` | Name that company operates under | String |
| `Issued` | Date of issue of license/permit | Date |
| `Client Name` | Name that the license is issued to | String |
| `Business Phone` | Client business phone number | String |
| `Business Phone Ext.` | Client business phone extension number | Integer |
| `Licence Address Line 1` | First line of client's business address | String |
| `Licence Address Line 2` | Client address town and province | String |
| `Licence Address Line 3` | Client address postal code | String |
| `Ward` | Client address ward number | String |
| `Conditions` | Restrictions on the license/permit | String |
| `Free Form Conditions Line` | Restrictions/comments on the license/permit | String |
| `Plate No.` | License identifying plate, issued to vehicles | String |
| `Endorsements` | Activity permitted under the license | String |
| `Cancel Date` | Date the license or permit was canceled | Date |
| `Last Record Update` | Date of the last update to the record | Date |

---

#### viii. Tools Used

| Tool | Purpose | Libraries / Features |
|------|---------|---------------------|
| **Python** | Primary data analysis and modeling | Pandas, Statsmodels |
| **Excel** | Initial data exploration and validation | Data preview, basic statistics |
| **Power BI** | Trend visualization and dashboard creation | Interactive charts, time-series plots |


---

### II. Development (Data Exploration, Cleaning, Manipulation and Visualization)

#### a. Checking for Missing (Null) Values

To ensure the datasets were complete and suitable for analysis, we conducted a thorough check for missing values across all relevant columns. For the food truck and restaurant databases, our main columns of interest were the `Category` and `Client Name` columns, since these would be used to determine which licenses were active in a specific year. For both columns of interest, there were no missing values. For the population estimates dataset, no missing values were recorded. For the labour force dataset, 20 missing values were identified in the value column and were dropped.

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/MISSING%20VALUE.png?raw=true)
![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/MISSING%20VALUE%20RESULT.png?raw=true)



#### b. Checking for Duplicates

To ensure the integrity of the datasets and eliminate redundant records, a thorough check for duplicate entries was conducted. For the Food Truck and Restaurant datasets, i focused specifically on the `Licence No.` and `Client Name` columns, as only licensees with unique license numbers and client names were considered valid. Using Python's Pandas library, these columns were standardized by converting them to lowercase and removing extra spaces to ensure uniformity. The `duplicated()` method to identify and remove any duplicate rows based on these two key columns. For the Labour and Population datasets, we conducted a broader check across all columns to identify duplicate rows without focusing on specific fields.

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/DUPLICATE%20CHECK.png?raw=true)

#### c. Outliers Check

Outliers were not checked in this project since the data was to be aggregated to yearly totals. With yearly aggregation, extreme values at the individual license level are smoothed out, making outlier detection less relevant for the analysis.










#### d. Data Extraction and Categorisation

To enable time series analysis and feed our intended models, we extracted yearly data summaries for our variables of interest. Following the Institute of Justice study, we extracted time series rows for these variables.

To ascertain which food trucks and restaurants were active per year, we used the following inclusion criterion:

*A license is considered active if it was issued on or before the year in question and it has not expired by the end of the year.*

A final data table consisting of yearly data for our model was then put together. It consists of yearly Toronto data for number of food trucks and restaurants (1969–2024), unemployment rate (2006–2024), and population data (2001–2023).


![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/FINDING%20ACTIVE%20FOOD%20TRUCK%20AND%20RESTAURANT.png?raw=true)

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/ACTIVE%20FOODTRUCK%20AND%20RESTAURANT%20RESULT.png?raw=true)

#### e. Univariate Trend Analysis

**Food Truck and Restaurant Trends**

The analysis examined the trends in the number of active food trucks and restaurants in Toronto from 1969 to 2024. The graph reveals distinct growth patterns for both sectors. The number of food trucks showed a steady increase starting in the late 1980s, with significant growth observed between 1990 and 2004, likely driven by increased urbanization, demand for mobile dining, and changing consumer preferences. However, a notable decline occurred after 2004, suggesting potential regulatory challenges or market saturation. In contrast, restaurants experienced consistent growth until the early 2000s, stabilizing thereafter with minor fluctuations. The trend also suggests that restaurants have shown greater resilience during economic downturns, such as the COVID-19 pandemic, likely due to their established customer base, diversified service models, and access to financial support programs.

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/TREND%20ANALYSIS%20FOR%20FOODTRUCK%20AND%20RESTAURANT.png?raw=true)

**Population Trend**

The population trend from 2000 to 2023 shows a steady and consistent increase, reflecting Toronto's ongoing urban growth and attraction as a metropolitan hub. This growth in population underpins the expanding demand for both food trucks and traditional restaurants, as a larger population offers a broader customer base for these businesses.

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/POPULATION%20TREND.png?raw=true)

**Unemployment Rate Trend**

The unemployment rate trend from 2006 to 2024 displays significant fluctuations, with notable peaks around 2009 (post-2008 financial crisis) and 2020 (COVID-19 pandemic). These economic downturns likely affected consumer spending and entrepreneurial activity, which are crucial for the food service industry. Despite these challenges, the gradual recovery in unemployment rates post-2020 indicates improving economic conditions, which could favor the resurgence and growth of food-related businesses.

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/UNEMPLOYMENT%20RATE%20TREND.png?raw=true)


#### f. Correlation Analysis

Correlation analysis was conducted to examine the relationships between key variables using scatter plots and trend lines, with R-squared values quantifying the strength of the relationships. The scatter plot reveals a positive relationship between the number of active food trucks and restaurants, with an R-squared value of 0.628, suggesting a complementary relationship rather than direct competition. The correlation between unemployment rate and food trucks is weak, with an R-squared value of 0.013, indicating that other factors likely play a larger role in determining food truck activity. Similarly, the relationship between unemployment and restaurants is very weak at 0.021, highlighting the resilience of established restaurants during economic downturns. The correlation between population and food trucks is also weak at 0.186, suggesting that food trucks may concentrate in areas with higher tourism or business activity rather than purely residential areas.

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/CORRELATION%20ANALYSIS.png?raw=true)


#### g. Visualization

Visualizations were created to analyze key trends in Toronto's food service industry. The data shows 1,217 food truck exits and 19,000 restaurant exits, with 1,577 new food truck entrants and 25,000 new restaurant entrants. The total active food truck count by category reveals NON-MOTORIZED REFRESHMENT VEHICLES leading with 7.9K, followed by MOTORIZED REFRESHMENT VEHICLES at 6.6K, SIDEWALK VENDING at 3.0K, HAWKER/PEDLAR WITH MOTOR VEHICLE at 1.2K, CURBLANE VENDING at 0.6K, and MOBILE VENDING at 0.3K each. Restaurant entrants show a steady increase over time with a peak around 2000, while food truck entrants peaked around 1990 and 2000 before declining after 2004. Food truck exits remained low until the 1990s before increasing, closely following entry patterns. Restaurant exits show a steady upward trend from the 1970s through the 2010s, with a significant peak around 2015, reflecting the competitive nature of the industry.

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/FOODTRUCK%20BI%20VIZ.png?raw=true)



### III. Analysis

#### i. Findings Documentation and Discovery

**Modeling**

A Pooled Ordinary Least Squares (POLS) regression model was developed to analyze the relationship between food trucks and restaurants in Toronto while controlling for unemployment rate, population, and lagged restaurant count. The model was specified as follows:
Restaurants_t = β₀ + β₁(Food Trucks_t) + β₂(Unemployment_t) + β₃(Population_t) + β₄(Restaurants_t-1) + ε_t


The Pooled OLS method was selected due to its suitability for analyzing time series data with a single entity, in this case, the city of Toronto. The model assumes no time-invariant characteristics that could bias the results, allowing all variations in the dependent variable to be attributed to the explanatory variables included in the model.


![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/POOLED%20OLS%20ESTIMATE.png?raw=true
)



**Estimation Results**

| Variable | Coefficient | P-Value | Significance |
|----------|-------------|---------|--------------|
| Food Trucks | 3.51 | < 0.05 | Significant |
| Unemployment Rate | 40.37 | < 0.05 | Significant |
| Population | 0.0019 | < 0.05 | Significant |
| Lagged Restaurants | 0.35 | 0.1711 | Not Significant |

The estimation yielded a statistically significant positive relationship between food trucks and restaurants (p < 0.05), with each additional food truck associated with a 3.51-unit increase in active restaurants. The unemployment rate showed a strong positive coefficient of 40.37, indicating that a 1% increase in unemployment is associated with an increase of 40.37 active restaurants. Population also showed a positive but smaller effect. The lagged number of restaurants was not statistically significant (p = 0.1711).

**Post Estimation Tests**

The Durbin-Watson test was conducted to assess the presence of autocorrelation in the residuals. The calculated statistic was 1.3648, indicating the presence of positive autocorrelation, which could affect the efficiency of the parameter estimates.

**Alternative Models**

Alternative models including ARIMA, Arellano-Bond, Two-Stage Least Squares (2SLS), and First Difference methods were evaluated. The ARIMA model failed to establish a direct relationship between variables. The Arellano-Bond model produced lower than expected coefficients and failed autocorrelation tests. The 2SLS approach encountered challenges in selecting the best instrumental variable. The First Difference Test produced invalid R-squared values. The Pooled OLS method emerged as the most appropriate choice for this study.



## 3. Recommendations

Based on the findings of this study, the following policy recommendations are proposed to support a balanced and thriving food service industry in Toronto:

**1. Support Collaborative Food Ecosystems**

Policies should encourage partnerships between food trucks and restaurants to maximize their collective impact. Culinary Hubs should be established in high-traffic areas such as Nathan Phillips Square and Harbourfront, where food trucks and restaurants share spaces to create vibrant dining destinations. Integrating food trucks into existing restaurant districts, such as the King Street West area, can enhance the area's appeal to both locals and tourists.

**2. Foster Entrepreneurship in the Food Industry**

Initiatives should be introduced to make entry into the food truck business more accessible. Programs like the City of Toronto's BusinessTO Support Centre could expand to offer specific training modules and funding options for food truck operators. Aspiring entrepreneurs could be offered micro-loans or grants to cover startup costs such as vehicle retrofitting and licensing fees. By targeting underrepresented communities, these programs could diversify Toronto's culinary offerings while driving inclusive economic growth.

**3. Invest in Infrastructure for Food Services**

Designated Food Truck Zones, such as those near Union Station or Harbourfront, should be developed to provide essential utilities like electricity and water while reducing congestion in high-demand areas. Drawing inspiration from successful models like Portland's food truck pods, semi-permanent food truck clusters could be introduced in emerging neighborhoods like Liberty Village or the Distillery District.

**4. Encourage Innovation in Food Services**

Supporting the adoption of technology can ensure the resilience of Toronto's food trucks and restaurants. Incentives should be offered for adopting delivery platforms and emerging trends like cloud kitchens. The city could partner with tech hubs in Toronto, such as MaRS Discovery District, to explore cutting-edge solutions tailored for the food service sector.

**5. Simplify and Modernize Licensing Processes**

Addressing barriers to entry for food trucks in Toronto is crucial. The current annual mobile vending permit fee of $6,377 should be reviewed to make the industry more accessible to small-scale entrepreneurs. An online "Fast-Track Licensing Portal" could be introduced to streamline approvals, reduce wait times, and improve transparency.


## 4. Conclusion

This study investigated the economic relationship between food trucks and traditional restaurants in Toronto using 55 years of business licensing data, unemployment statistics, and population estimates. The Pooled OLS regression analysis revealed a statistically significant positive relationship between food trucks and restaurants, with each additional food truck associated with a 3.51-unit increase in active restaurants. This finding challenges the common perception that food trucks pose a threat to traditional restaurants and instead points to a complementary relationship where both sectors thrive alongside each other.

The unemployment rate also showed a strong positive correlation with restaurant activity, suggesting that economic downturns may drive entrepreneurship and demand for affordable dining options. Population growth contributed positively to restaurant counts, reinforcing the role of market size in supporting the food service industry.

The analysis confirms that food trucks and restaurants are complements, not competitors. These findings provide a strong evidence base for policy reforms that support both sectors. By implementing collaborative strategies, reducing regulatory barriers, and investing in infrastructure, Toronto can position itself as a global leader in culinary diversity and innovation.

![Insert Image](images/conclusion.png)
