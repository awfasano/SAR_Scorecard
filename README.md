## 📘 Purpose

This repo is designed to provide **comprehensive indicator coverage** across all eight South Asia Region (SAR) countries, spanning both national (`admin0`) and subnational (`admin1`) levels. Each location–indicator combination includes up to two data points: one for the **most recent value** and one for the **previous value**.

---

## 📊 Database Structure

### ✔️ Admin Unit Coverage

The database currently accounts for the following number of administrative level 1 (admin1) regions:

| Country | Admin1 Units |
|---------|--------------|
| AFG     | 34           |
| BGD     | 8            |
| BTN     | 20           |
| IND     | 36           |
| LKA     | 9            |
| MDV     | 20           |
| NPL     | 7            |
| PAK     | 7            |
| **Total** | **141**     |

In addition to subnational data, national-level data (admin0) is also included for each country.

---

## Indicator Categories — Included

Indicators are grouped by their primary data methodology. Links point to the repositories where calculations currently live.

### 🛰️ Proxied Indicators — Included
- **Exposure to hazardous air quality (PM2.5)** — https://github.com/awfasano/SAR-Scorecard-Exposure-to-Hazardous-Air-Quality/tree/main  
- **Greenhouse gas emissions (kilotons CO₂)** — https://github.com/awfasano/sar-scorecard-ghg-emission-kilotons-co2  
- **Rural access to an all-season road (SDG 9.1.1, RAI)** — https://github.com/awfasano/SDG-Indicator-911  
- **Access to electricity (% of population)** — computed via Survey repo: https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  

### 🧮 Calculated Indicators — Included
- **Gross Domestic Product (GDP)** — https://github.com/awfasano/SAR-Scorecard---GDP/tree/main  
- **Hectares of key ecosystems -- https://github.com/awfasano/millions-of-hectacres
- **Percentage of terrestrial and marine areas protected  -- https://github.com/awfasano/millions-of-hectacres

### 📝 Indicators From Surveys — Included
- **Percentage of population with a financial account** — https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  
- **Percentage of population with access to basic hygiene** — https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  
- **Percentage of population using the internet** — https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  
- **Poverty headcount ratio at $2.15/day** — https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  
- **Poverty headcount ratio at $6.85/day** — https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  
- **Percentage of population with access to basic sanitation** — https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  
- **Percentage of wage and salaried workers** — https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  
- **Percentage of population with access to basic drinking water** — https://github.com/awfasano/Survey-Calculations-SAR-Scorecard
- **Gini coefficient** — computed via Survey repo: https://github.com/awfasano/Survey-Calculations-SAR-Scorecard  
  

---

## Not in github repo
- Population at high risk from climate-related hazards  
- Proportion of fish stocks within biologically sustainable levels  
- Percentage of terrestrial and marine areas protected  
- Percentage of children experiencing learning poverty  
- Average income shortfall  
- Tax Revenue as a percentage of GDP  
- Percentage of children under five who are stunted  
- Percentage of population facing food insecurity  
- Percentage of population covered by social protection  
- Percentage of youth not in education, employment, or training (NEET)  

---

## 🗂️ Variable Descriptions

| Variable Name        | Description |
|----------------------|-------------|
| `country_wb`         | ISO3 country code (e.g., `AFG` for Afghanistan). |
| `level0_code`        | Code for the top-level country or region. |
| `level0_name`        | Name of the top-level entity (e.g., Afghanistan). |
| `level1_code`        | Code for first-level admin unit (e.g., province/state). |
| `level1_name`        | Name of the first-level administrative unit. |
| `level2_code`        | Code for second-level admin unit (optional). |
| `level2_name`        | Name of the second-level admin unit (optional). |
| `disputed`           | Flag for disputed territory (`ND` = Not Disputed / No Data). |
| `outcome_area`       | Development theme or outcome area (e.g., Vision, People, Planet). |
| `scorecard_side`     | High-level pillar the indicator supports (e.g., Client Context). |
| `indicator`          | Short name/code of the indicator. |
| `indicator_label`    | Full label or description of the indicator. |
| `value`              | Measured value (may be blank if not available). |
| `year`               | Year of the observation. |
| `measurement_type`   | Indicates if value is `recent`, `previous`, or other metadata. |

---

### 🧮 Data Shape Expectation

Assuming **30 indicators** and **2 measurement types** (recent and previous), the expected row count is:

- **Admin0 Level**: 8 countries × 30 indicators × 2 = **480 rows**
- **Admin1 Level**: 141 units × 30 indicators × 2 = **8,460 rows**

**Total expected rows: ~8,940**  
*(Note: actual number may differ depending on available indicators and missing values)*

---

## 🛠️ Future Additions

- Support for **level2** (district-level) granularity as data becomes available.
