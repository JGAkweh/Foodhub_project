# FoodHub Order Analysis

**Program:** Code4Food Security Fellowship — Blossom Academy × WFP Ghana × KOICA  
**Author:** Justina Ama Enyonam Acolatse  
**Tools:** Python · pandas · numpy · matplotlib · seaborn

---

## Project Overview

FoodHub is a food aggregator platform that connects customers with multiple restaurants through a single smartphone app. As the number of restaurant partners and orders grows, the company needs data-driven insights to improve customer satisfaction, optimise delivery operations, and maximise revenue.

This project performs a full exploratory data analysis of FoodHub's order dataset, answering 13 structured business questions and closing with concrete, evidence-based recommendations for the operations and marketing teams.

---

## Dataset

**File:** `foodhub_order.csv`  
**Size:** 1,898 orders with no missing values

| Column | Description | Type |
|---|---|---|
| `order_id` | Unique identifier for each order | Integer |
| `customer_id` | Unique identifier for each customer | Integer |
| `restaurant_name` | Name of the restaurant | Text |
| `cuisine_type` | Type of cuisine ordered | Text |
| `cost_of_the_order` | Total order cost in USD | Float |
| `day_of_the_week` | Weekday or Weekend | Text |
| `rating` | Customer rating: 3, 4, 5, or 'Not given' | Text |
| `food_preparation_time` | Restaurant preparation time (minutes) | Integer |
| `delivery_time` | Delivery time after preparation (minutes) | Integer |

**Engineered features added during analysis:**

- `rating_numeric` — numeric version of `rating`, with `'Not given'` as `NaN`
- `total_time` — sum of `food_preparation_time` and `delivery_time`
- `commission_earned` — per-order revenue calculated using FoodHub's tiered commission structure

---

## Repository Structure

```
FoodHub_Order_Analysis/
│
├── FoodHub_Order_Analysis_Complete.ipynb   # Main analysis notebook
├── foodhub_order.csv                       # Source dataset
├── README.md                               # This file
│
└── plots/                                  # Exported visualisations
    ├── plot_q1_rating_status.png
    ├── plot_q2a_cost.png
    ├── plot_q2b_times.png
    ├── plot_q2c_cuisine.png
    ├── plot_q2d_day_rating.png
    ├── plot_q3_top5_restaurants.png
    ├── plot_q4_weekend_cuisine.png
    ├── plot_q5_cost_brackets.png
    ├── plot_q7_cost_vs_rating.png
    ├── plot_q8_delivery_vs_rating.png
    ├── plot_q9_promo_restaurants.png
    ├── plot_q10_revenue.png
    ├── plot_q11_total_time.png
    └── plot_q12_delivery_day.png
```

---

## How to Run

1. Clone or download this repository.
2. Ensure the following libraries are installed:

```bash
pip install pandas numpy matplotlib seaborn
```

3. Place `foodhub_order.csv` in the same directory as the notebook.
4. Open `FoodHub_Order_Analysis_Complete.ipynb` in Jupyter Notebook or JupyterLab and run all cells in order.

---

## Analysis Structure

The notebook is organised into five sections:

| Section | Content |
|---|---|
| 1. Setup | Library imports, data loading, initial inspection |
| 2. Data Preparation | Feature engineering (`rating_numeric`, `total_time`) |
| 3. Exploratory Data Analysis | Questions 1–12 with visualisations and written answers |
| 4. Business Analysis | Revenue modelling, promotional eligibility |
| 5. Conclusions & Recommendations | Summary findings and six strategic recommendations |

---

## Key Findings

| Metric | Value |
|---|---|
| Total orders | 1,898 |
| Unique customers | 1,200 |
| Unique restaurants | 178 |
| Unrated orders | 736 (38.78%) |
| Average delivery time | 24.16 minutes |
| Average total wait time | 51.5 minutes |
| Orders above $20 | 555 (29.24%) |
| Orders exceeding 60 minutes | 200 (10.54%) |
| Total net revenue (commission) | $6,166.30 |
| Top restaurant | Shake Shack (219 orders, 11.5% share) |
| Most ordered cuisine | American (584 orders, 30.8%) |
| Peak demand period | Weekends (71.2% of all orders) |

---

## Promotional Offer Eligibility

Restaurants qualifying for the promotional offer (more than 50 rated orders **and** average rating above 4.0):

| Restaurant | Rated Orders | Average Rating |
|---|---|---|
| The Meatball Shop | 84 | 4.510 |
| Blue Ribbon Fried Chicken | 64 | 4.330 |
| Shake Shack | 133 | 4.280 |
| Blue Ribbon Sushi | 73 | 4.220 |

---

## Recommendations

1. **Close the rating gap** — 38.78% of orders have no rating. A post-delivery push notification could recover substantial feedback data.
2. **Diversify restaurant partnerships** — five restaurants account for 33% of all orders. Expanding the active partner base reduces concentration risk.
3. **Staff more drivers on weekdays** — weekday delivery is 5.87 minutes slower than weekend delivery despite lower demand, suggesting a driver availability gap.
4. **Target the 60-minute threshold** — 10.54% of orders exceed 60 minutes total wait time. Setting a platform cap on preparation time and issuing real-time alerts to restaurants could bring this figure down significantly.
5. **Use the promotional criteria as a quality programme** — share rating benchmarks with all restaurant partners so they can track progress toward eligibility.
6. **Launch a high-value customer loyalty programme** — the 29.24% of orders above $20 generate a disproportionate share of FoodHub's revenue and are ideal candidates for premium membership incentives.

---

## Skills Demonstrated

- Data cleaning and feature engineering with pandas
- Exploratory data analysis across categorical, ordinal, and continuous variables
- Business logic implementation using custom functions and `.apply()`
- Grouped aggregations with `groupby()` and multi-condition filtering
- Data visualisation with matplotlib and seaborn (histograms, bar charts, pie charts, violin plots, box plots, scatter plots)
- Translation of analytical findings into actionable business recommendations

---

## About the Author

Justina is a Ghana-based data analyst with a background in Natural Resource Management and a career trajectory focused on food security and climate data. This project was completed as part of the Code4Food Security Fellowship at Blossom Academy, a fully funded programme in partnership with WFP Ghana and KOICA.

Connect on [LinkedIn](https://www.linkedin.com) | View more projects on [GitHub](https://github.com)
