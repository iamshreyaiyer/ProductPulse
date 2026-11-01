# ProductPulse 📊
### Evidence-Driven Product Investigation & Decision Engine

ProductPulse is an end-to-end product analytics project that transforms raw e-commerce behavioural data into actionable business insights. It analyses user interactions, identifies unusual activity patterns, investigates potential product performance issues, and prioritizes investigations using a weighted decision-scoring framework.

The goal is to move beyond traditional descriptive analytics and demonstrate how data can support structured product investigation and decision-making.

---

## 🎯 Project Objectives

- Analyse e-commerce user behaviour and interaction patterns.
- Understand the relationship between product views, add-to-cart events, and transactions.
- Perform user-level, product-level, and category-level analysis.
- Identify unusual patterns and potential business anomalies.
- Investigate product performance using temporal and behavioural evidence.
- Develop a weighted investigation prioritization engine.
- Communicate findings through executive-level visualizations.

## 🗂️ Dataset

**Retailrocket Recommender System Dataset**

Source: [Kaggle — Retailrocket E-commerce Dataset](https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset)

The dataset contains approximately 2.75 million user interaction events, along with product properties and category information.

Files used:

- `events.csv`
- `category_tree.csv`
- `item_properties_part1.csv`
- `item_properties_part2.csv`

The event data contains three interaction types:

- `view`
- `addtocart`
- `transaction`

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Data analysis and business logic |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Google Colab | Development environment |
| Git & GitHub | Version control and project documentation |

## 🔍 Analytical Workflow

**1. Data Preparation and Validation**
- Dataset loading and structural validation.
- Missing-value and duplicate checks.
- Timestamp conversion and feature engineering.
- Historical product-category mapping.

**2. Exploratory Data Analysis**
- Event distribution analysis.
- Unique visitor and product analysis.
- User interaction patterns.
- Product and category-level behaviour.

**3. User Behaviour Analysis**
- Visitor-level event segmentation.
- Cart and transaction overlap.
- Visitor-product interaction analysis.
- Time between first cart and first transaction.

**4. Product and Category Investigation**
- Category-level engagement analysis.
- Product-level performance comparisons.
- Historical category reassignment analysis.
- Identification of low downstream activity.

**5. Temporal Analysis and Anomaly Detection**
- Daily and hourly activity patterns.
- Weekday versus weekend comparisons.
- Identification of unusual transaction activity.

**6. Investigation Prioritization**
- Weighted investigation scoring.
- Priority classification.
- Automated ranking of investigation candidates.

**7. Executive Reporting**
- Investigation ranking dashboard.
- Priority distribution visualization.
- Structured investigation records.

---

## 🚨 Key Business Findings

### 1. Transaction Activity Anomaly — September 17, 2015

A significant decline in transaction activity was observed on September 17 compared with other Thursdays.

Key observations:
- Transaction events per 1,000 views were approximately 4.58, compared with an average of 9.40 on other Thursdays.
- Transaction activity was approximately 51.3% lower on a per-view basis.
- Evening transaction activity showed an especially sharp decline.

**Business implication:** This pattern warrants investigation into checkout performance, payment processing, tracking instrumentation, and changes in traffic composition.

The available data identifies an anomaly but does not establish its underlying cause.

### 2. Weekend Transaction Activity

Weekend activity showed lower transaction activity relative to views compared with weekdays.

| Metric | Weekday | Weekend |
|---|---:|---:|
| Views | 2,041,498 | 621,335 |
| Add-to-cart events | 54,802 | 14,496 |
| Transactions | 18,636 | 3,806 |
| Transactions per 1,000 views | 9.13 | 6.13 |

**Business implication:** The difference may warrant investigation into traffic composition, user intent, and purchase behaviour across different days of the week.

This is an observational finding, not proof that weekends cause lower transaction activity.

### 3. Category 642 — Low Downstream Activity

An investigation into category 642 identified substantial browsing activity but very little downstream interaction.

| Metric | Result |
|---|---:|
| Views | 5,349 |
| Unique view visitors | 4,400 |
| Products observed | 481 |
| Add-to-cart events | 2 |
| Transactions | 0 |

Further investigation revealed that all 481 products had multiple recorded category assignments.

The products continued receiving views after their category reassignment, with 2,246 subsequent views across 312 products.

**Business implication:** Product classification changes significantly affected category-level interpretation. The low downstream activity remains an unresolved product-performance question requiring further investigation.

---

## ⚙️ Investigation Prioritization Engine

ProductPulse includes a weighted scoring framework to rank investigation candidates.

Five dimensions are evaluated on a scale of 1–5.

| Dimension | Weight |
|---|---:|
| Severity | 25% |
| Reach | 25% |
| Business Impact | 25% |
| Evidence Confidence | 15% |
| Investigation Ease | 10% |
| **Total** | **100%** |

The weighted score is normalized to a scale of 0–100.

### Priority Classification

| Score | Priority |
|---|---|
| 80–100 | Critical |
| 65–79.99 | High |
| 45–64.99 | Medium |
| Below 45 | Low |

### Investigation Ranking

| Investigation | Score | Priority |
|---|---:|---|
| September 17 Transaction Activity Anomaly | 83 | Critical |
| Weekend Transaction Activity | 72 | High |
| Category 642 Low Downstream Activity | 62 | Medium |

The scoring framework uses analyst-assigned assessments and configurable weights. These scores are intended to demonstrate structured prioritization rather than represent objectively measured business risk.

---

## 📈 Executive Dashboard

The project generates visual reports covering:

- Investigation priority scores.
- Ranked investigation candidates.
- Distribution of investigations across priority levels.

The dashboard provides a consolidated view of which business issues warrant further investigation.

---

## ⚠️ Limitations

- The dataset is observational and cannot independently establish causation.
- Historical product-category assignments can change over time.
- Category mapping does not cover every event.
- Revenue, profit, pricing, and inventory information are not available for reliable financial impact estimation.
- The prioritization framework includes analyst-assigned scores and assumptions.
- Further validation using operational and business data would be required before recommending actual product changes.

## 🚀 Future Enhancements

- Develop an interactive Streamlit dashboard.
- Integrate SQL-based analytical workflows.
- Automate anomaly detection and investigation candidate generation.
- Incorporate pricing, inventory, and revenue information.
- Improve prioritization through historical investigation outcomes.
- Add scenario analysis and decision simulation.

---

## 💡 Project Takeaway

ProductPulse demonstrates how Python-based analytics can connect behavioural data analysis, anomaly investigation, business reasoning, and decision prioritization in a single analytical workflow.

It showcases the application of data analytics to practical product and business investigation problems.

**Built with Python, Pandas, NumPy, and Matplotlib.**
