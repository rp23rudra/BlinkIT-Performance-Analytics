# BlinkIT Performance Analytics & Business Insights

An end-to-end retail analytics project analyzing BlinkIT grocery sales data to identify product, outlet, and location-level performance patterns and derive actionable business insights.

## 📌 Project Overview

This project analyzes BlinkIT grocery retail data containing **8,523 records across 12 attributes**.

The analysis covers:

- Product performance
- Outlet performance
- Outlet location performance
- Product fat-content analysis
- Outlet establishment trends
- Top-performing item IDs
- Business KPI analysis
- Data cleaning and validation
- Business recommendations

The project follows an end-to-end analytics workflow from raw data preparation to exploratory analysis, visualization, and business insights.

 

## 🎯 Business Objective

The objective is to understand:

1. Which product categories contribute the most revenue?
2. Which outlet types generate the highest sales?
3. Which location tiers perform better?
4. Which individual outlets are strongest?
5. Which products contribute the highest sales?
6. How does outlet establishment year relate to sales?
7. Where are potential areas for further business investigation?

 

## 📊 Dataset

The dataset contains **8,523 retail records** and the following 12 fields:

- Item Identifier
- Item Weight
- Item Fat Content
- Item Visibility
- Item Type
- Item MRP
- Outlet Identifier
- Outlet Establishment Year
- Outlet Size
- Outlet Location Type
- Outlet Type
- Item Outlet Sales

### Dataset Summary

| Metric | Value |
| | :|
| Records | 8,523 |
| Columns | 12 |
| Unique Item IDs | 1,559 |
| Unique Outlets | 10 |
| Total Sales | ₹18.59M |
| Average Sales | ₹2,181.29 |
| Average MRP | ₹140.99 |

 

## 🧹 Data Cleaning

The raw dataset was validated and transformed into an analysis-ready dataset using Python and Pandas.

### Data Quality Checks

- Verified dataset dimensions
- Validated column data types
- Checked missing values
- Checked duplicate records
- Validated categorical values
- Checked numerical ranges

### Cleaning Performed

#### Item Fat Content

Standardized inconsistent values:

- `LF` → `Low Fat`
- `low fat` → `Low Fat`
- `reg` → `Regular`

Final categories:

- Low Fat: 5,517
- Regular: 3,006

#### Item Weight

There were **1,463 missing values**.

A hierarchical imputation approach was used:

1. Median weight for the same `Item_Identifier`
2. Item-type median as a fallback

This recovered:

- 1,459 values using item-level information
- 4 values using item-type-level information

#### Outlet Size

There were **2,410 missing values**.

Missing outlet sizes were inferred using outlet characteristics and comparable outlets within the dataset.

Final distribution:

- Small: 4,798
- Medium: 2,793
- High: 932

### Final Validation

After cleaning:

- **8,523 rows × 12 columns**
- **0 missing values**
- **0 duplicate rows**

 

## 🔎 Exploratory Data Analysis

The analysis examined sales performance across multiple dimensions.

### Product Performance

The highest-revenue product categories were:

| Rank | Item Type | Sales |
| | | :|
| 1 | Fruits & Vegetables | ₹2.82M |
| 2 | Snack Foods | ₹2.73M |
| 3 | Household | ₹2.06M |
| 4 | Frozen Foods | ₹1.83M |
| 5 | Dairy | ₹1.52M |

The top three categories contributed approximately **40.92% of total sales**.

### Outlet Performance

| Outlet Type | Sales Share |
| | :|
| Supermarket Type1 | 69.48% |
| Supermarket Type3 | 18.58% |
| Supermarket Type2 | 9.96% |
| Grocery Store | 1.98% |

Supermarket Type1 is the largest contributor to overall sales volume.

However, Supermarket Type3 has the highest average sales per record:

**₹3,694.04**

compared with the overall average of **₹2,181.29**.

### Location Performance

| Location | Sales Share |
| | :|
| Tier 3 | 41.08% |
| Tier 2 | 34.81% |
| Tier 1 | 24.11% |

Tier 2 and Tier 3 locations together contribute **75.89% of total sales**.

### Fat Content

Low Fat products contribute:

**64.03% of total sales**

while Regular products contribute the remaining 35.97%.

 

## 💡 Key Business Insights

### 1. Supermarket Type1 drives sales volume

Supermarket Type1 contributes **69.48% of total sales**, making it the dominant outlet format in the dataset.

### 2. Supermarket Type3 shows high sales intensity

Although Supermarket Type3 has fewer records than Supermarket Type1, its average sales per record are **₹3,694.04**, the highest among outlet types.

This makes its operating characteristics worth investigating.

### 3. Tier 2 and Tier 3 locations dominate

Together, Tier 2 and Tier 3 locations account for **75.89% of total sales**, indicating stronger sales performance than Tier 1 locations in this dataset.

### 4. A small number of product categories drive substantial revenue

Fruits & Vegetables, Snack Foods, and Household products collectively account for **40.92% of total sales**.

These categories are therefore important for inventory availability and merchandising analysis.

### 5. Grocery Stores require further investigation

Grocery Stores contribute only **1.98% of total sales**, with average sales of **₹339.83** per record.

Rather than assuming poor performance is caused by one factor, further analysis of product mix, outlet format, and demand would be required.

 

## 📈 Visualizations

The project includes eight analytical visualizations:

1. Sales by Item Type
2. Sales by Outlet Type
3. Sales by Outlet Location
4. Sales by Fat Content
5. Sales by Outlet Establishment Year
6. Top 10 Item IDs by Sales
7. Sales by Outlet
8. Average Sales by Outlet Type

All exported visualizations are available in the [`visuals/`](visuals/) directory.

 

## 📊 Tableau Dashboard

> **Coming next:** Interactive Tableau dashboard with KPI cards, filters, sales breakdowns, outlet analysis, and business insights.

The dashboard will be added here after completion.

 

## 🛠️ Tools & Technologies

- **Python**
- **Pandas**
- **Matplotlib**
- **Jupyter Notebook**
- **Tableau**
- **Git & GitHub**

 

## 📁 Project Structure

```text
BlinkIT-Performance-Analytics/
│
├── data/
│   └── processed/
│       └── blinkit_analysis_ready.csv
│
├── notebooks/
│   └── 01_blinkit_data_cleaning.ipynb
│
├── visuals/
│   ├── 01_sales_by_item_type.png
│   ├── 02_sales_by_outlet_type.png
│   ├── 03_sales_by_location.png
│   ├── 04_sales_by_fat_content.png
│   ├── 05_sales_by_establishment_year.png
│   ├── 06_top_10_items_by_sales.png
│   ├── 07_sales_by_outlet.png
│   └── 08_avg_sales_by_outlet_type.png
│
├── powerbi/
│
└── README.md
