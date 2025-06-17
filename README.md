## 📘 Purpose

This database is designed to provide **comprehensive indicator coverage** across all eight South Asia Region (SAR) countries, spanning both national (`admin0`) and subnational (`admin1`) levels. Each location-indicator combination includes up to two data points: one for the **most recent value** and one for the **previous value**.

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

### Indicator Categories

Indicators are grouped by their primary data methodology. The code for each category of indicators can be found in the corresponding GitHub repository linked in the titles below.

#### 🛰️ [Proxied Indicators](https://github.com/awfasano/Proxied-Calculations-SAR-Scorecard)

* Percentage of population exposed to hazardous air quality
* Population at high risk from climate-related hazards
* Hectares of key ecosystems
* Percentage of population with access to electricity
* Proportion of fish stocks within biologically sustainable levels
* Greenhouse gas emissions
* Percentage of rural population with access to an all-season road
* Percentage of terrestrial and marine areas protected

#### 🧮 [Calculated Indicators](https://github.com/awfasano/Calculated-Indicators-SAR-Scorecard)

* Gini coefficient
* Percentage of children experiencing learning poverty
* Average income shortfall
* Tax Revenue as a percentage of GDP
* Gross Domestic Product (GDP)

#### 📝 [Indicators From Surveys](https://github.com/awfasano/Survey-Calculations-SAR-Scorecard)

* Percentage of population with a financial account
* Percentage of children under five who are stunted
* Percentage of population facing food insecurity
* Percentage of population with access to basic hygiene
* Percentage of population using the internet
* Poverty headcount ratio at $2.15/day
* Poverty headcount ratio at $6.85/day
* Percentage of population with access to basic sanitation
* Percentage of population covered by social protection
* Percentage of wage and salaried workers
* Percentage of population with access to basic drinking water
* Percentage of youth not in education, employment, or training (NEET)

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

## 📌 Notes on Indicators and Naming

- All indicators from the **Country Scorecard (CSC)** should be represented at the national level, even when subnational data is unavailable.
- Indicators must be included under **each outcome area**, even if repeated. This ensures filtering by any outcome area is complete.
- For user clarity, indicator names should match those shown on the CSC site as closely as possible (e.g., prefer "Greenhouse Gas Emissions" over just "GHG Emissions").
- Some indicators originally meant for aggregates (e.g., "countries with high inequality") are replaced with more granular equivalents like the **Gini coefficient** for country-level analysis.

---

## 🛠️ Future Additions

- Support for **level2** (district-level) granularity as data becomes available.
- Updates for new or revised indicators based on CSC expansion.
- Improvements to metadata fields including `source`, `unit`, and `notes`.
