# Marketing Campaign Analysis

Exploratory data analysis and hypothesis testing on customer acquisition data, examining demographic, behavioral, and transactional factors through the lens of the marketing mix (4 Ps — Product, Price, Place, Promotion).

## Objective

As a data scientist, analyze customer response to marketing campaigns to understand what drives customer acquisition — using EDA, data cleaning, encoding, and statistical hypothesis testing on a dataset of 2,240 customers.

## Dataset

- **2,240 customer records** with demographic (birth year, education, marital status, income), behavioral (web visits, purchase channels), and transactional (spend by product category, campaign acceptance) attributes
- Full field definitions in [`data/data_dictionary.xlsx`](data/data_dictionary.xlsx)

## Key Steps Performed

1. **Data Cleaning** — Fixed data types (Income imported as string → float), imputed 24 missing Income values using the average grouped by Education and Marital Status, treated outliers in Age and Income
2. **Feature Engineering** — Derived `Customer_Age`, `Total_Children`, `Total_Spending`, `Total_Purchases`, and `Total_AcceptedCmp` from raw fields
3. **EDA** — Distribution analysis via histograms/boxplots, correlation heatmap across variables
4. **Encoding** — Ordinal encoding for Education, one-hot encoding for Marital Status, frequency encoding for Country
5. **Hypothesis Testing** — Tested 4 behavioral hypotheses about shopping channel preference and regional performance

## Key Findings

- **Older customers prefer in-store shopping** — store purchases increase with age, supporting the hypothesis
- **Customers with kids shop online more** — households with children show a higher share of web purchases (26% for no children vs. higher for 1+ children)
- **Store and web channels are complementary, not cannibalizing** — positive correlation observed between store and web purchase volume
- **US customers underperform** — total purchases from US customers are significantly lower than the rest of the world
- **Wine drives the most revenue**; gold products generate the least
- **Younger customers accept marketing campaigns at a higher rate**, with acceptance declining with age
- **Spain (SP)** has the highest number of customers who accepted the last campaign
- **Families with more children spend less overall**, particularly on luxury/discretionary items
- **Complaints are concentrated among customers with a basic education background**

Full findings and business recommendations in [`reports/Marketing_Campaign_Analysis_Report.docx`](reports/Marketing_Campaign_Analysis_Report.docx).

## Recommendations

- **Targeting:** Focus online campaigns on younger, child-bearing households; emphasize in-store promotions for older demographics
- **Product strategy:** Increase marketing investment in underperforming categories (fruits, gold, sweets)
- **Customer service:** Address dissatisfaction among less-educated customer segments to reduce complaints

## Tech Stack

- **Python 3**, Jupyter Notebook
- `pandas`, `numpy` for data manipulation
- `matplotlib`, `seaborn` for visualization
- `scikit-learn` (encoding, scaling) and statistical testing libraries

## Project Structure

```
├── notebooks/
│   └── Project1.ipynb                          # Full EDA, cleaning, encoding & hypothesis testing
├── reports/
│   ├── Marketing_Campaign_Analysis_Report.docx # Final written report with insights & recommendations
│   └── Marketing_Campaigns.docx                 # Supplementary project write-up
├── data/
│   ├── marketing_data.csv                       # Raw dataset (2,240 records)
│   └── data_dictionary.xlsx                     # Field definitions
├── docs/
│   └── problem_statement.docx                   # Original course project brief
└── README.md
```

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook notebooks/Project1.ipynb
```

## Author

Sanjay Gosai
*Applied Data Science with Python — Course-End Project*
