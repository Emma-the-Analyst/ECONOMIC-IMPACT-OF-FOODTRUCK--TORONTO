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
| **Python** | Primary data analysis and modeling | Pandas, NumPy, Statsmodels |
| **Excel** | Initial data exploration and validation | Data preview, basic statistics |
| **Power BI** | Trend visualization and dashboard creation | Interactive charts, time-series plots |
| **GitHub** | Version control and project documentation | Repository hosting, README |

---

**License Categories Extracted:**

| Food Truck Licenses | Restaurant Licenses |
|---------------------|---------------------|
| MOTORIZED REFRESHMENT VEHICLE OWNER | EATING ESTABLISHMENT |
| NON-MOTORIZED REFRESHMENT VEHICLE OWNER | |
| MOBILE VENDING (FOOD TRUCK) | |
| MOBILE VENDING (ICE CREAM TRUCK) | |
| SIDEWALK VENDING CURBLANE VENDING | |
| HAWKER/PEDLAR WITH MOTOR VEHICLE | |
