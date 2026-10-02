# Eniac E-commerce Discount Strategy: Comparative Sales and Profitability Analysis

## 🎯 Project Overview

Eniac needs to understand whether its discount strategy supports sales performance without undermining profitability. This project uses exploratory sales analysis, comparisons of the same products under discounted and non-discounted conditions, and estimated profit margins, with a focus on Computers and Storage. The analysis provides evidence for more selective promotions and identifies where further testing is needed before changing pricing policy.

## 📊 Dataset & Sources

- **Source:** Eniac project data. **[Add the original provider or course name and a public source link, if available.]**
- **Data files:** `products_clean.csv`, `orders_clean.csv`, and `orderlines_clean.csv`.
- **Dataset dimensions:** **[Add row and column counts for each cleaned table.]** The Computers and Storage sales analysis covers **114,655 units sold**; this is a unit count, not a dataset row count.
- **Timeframe:** **[Add the verified start and end dates.]**
- **Comparison sample:** **66 high-end products** observed in both discounted and non-discounted conditions: **31 Computers** and **35 Storage products**.
- **Detailed analysis:** A further deep dive examines **7 Storage products**.
- **Key variables:** Product identifier, category/subcategory, order date, quantity, reference price, transaction unit price, and discount percentage. **[Check the exact column names against the notebooks.]**
- **Classification:** Discounted sales have `discount_pct > 0`. The non-discounted group includes `discount_pct <= 0`, so it may also contain sales above the reference price.
- **Preprocessing:** The analysis uses cleaned tables and retains category and subcategory information. **[Document the actual handling of missing values, duplicates, invalid prices, order status, and table joins.]**

**Limitations:** The product comparison uses total units sold, without normalising for time spent in each pricing condition. Seasonality, availability, product lifecycle, and unequal exposure can influence the results. Profitability calculations use assumed margins rather than verified procurement costs.

## 🚀 Key Findings & Results

- **Discounts dominate the observed sales mix:** Of the **114,655 units** sold in Computers and Storage, **104,669 (91.3%)** were discounted and **9,986 (8.7%)** were in the non-discounted group.
- **Most comparable products recorded higher total unit sales when discounted:** **49 of 66 products (74.2%)** sold more units in the discounted condition. Comparing the same products reduces differences in product mix, but does not establish a causal effect.
- **The pattern is more common in Storage:** **29 of 35 Storage products (82.9%)** recorded higher discounted unit sales, compared with **20 of 31 Computers (64.5%)**. This supports prioritising Storage for further promotion testing; it does not measure sales uplift or price elasticity.
- **Seasonality matters:** The seasonal analysis identified sales peaks around Black Friday and Christmas, while average discounts were relatively stable. The aggregate analysis did not show a clear relationship between average discounts and sales volumes.
- **Sales volume needs a profitability check:** The margin analysis examines selected high-end products, including a **7-product Storage deep dive**. Higher unit sales alone do not demonstrate higher profit; recommendations should consider discount depth and estimated unit contribution together.

**Business recommendation:** Use category- and product-specific promotions, evaluate estimated profit alongside units and revenue, and validate proposed changes with controlled tests.

### Profitability assumptions

The estimated margin approach uses the following reference-price margin assumptions:

| Category | Assumed margin |
| --- | ---: |
| Computers | 10% |
| Displays | 15% |
| Storage | 20% |
| Other categories | 50% |

Estimated cost is calculated as `reference_price × (1 − assumed_margin)`. Estimated unit profit is `transaction_unit_price − estimated_cost`, and estimated line profit is `quantity × estimated_unit_profit`. These are scenario estimates, not verified accounting profit.

## 🛠️ Technologies Used

**[Verify this list against the final notebooks before publishing.]**

- **Programming:** Python.
- **Data analysis:** pandas and NumPy.
- **Visualisation:** Matplotlib and/or Seaborn — retain only the libraries actually used.
- **Environment:** Jupyter Notebook or Google Colab — specify the environment used.
- **Approach:** Exploratory analysis, seasonal aggregation, within-product sales comparisons, and estimated profitability analysis.

## 📁 Project Structure


| Path | Purpose |
| --- | --- |
| `README.md` | Business context, findings, and instructions |
| `notebooks/discount_analysis.ipynb` | Sales overview, seasonality, and product comparisons |
| `notebooks/profitability_analysis.ipynb` | Margin assumptions and product profitability deep dive |
| `data/products_clean.csv` | Cleaned product data |
| `data/orders_clean.csv` | Cleaned order data |
| `data/orderlines_clean.csv` | Cleaned transaction line data |
| `images/` | Exported charts displayed below |
| `requirements.txt` | Dependencies required to reproduce the notebooks |

## 📈 Visualisations

**Publishing note:** The chart files were not available when this README was drafted. Add the actual exported plots at the paths below, or update the paths to match your existing files. Each plot should have a title, labelled axes, and units.

### 1. Discounted versus non-discounted product sales

![Total units sold under discounted and non-discounted conditions for comparable high-end products](images/discounted_vs_non_discounted.png)

*Compares total units sold for the same 66 high-end products under both pricing conditions. Label the axes “Non-discounted units sold” and “Discounted units sold”, distinguish Computers from Storage, and include an equality line.*

### 2. Storage profitability deep dive

![Estimated profitability for seven selected Storage products](images/storage_profitability.png)

*Shows the profitability measure used in the seven-product Storage analysis. State the metric and currency or percentage on the axis, and identify the margin assumptions in the chart or caption.*

## 🔗 How to Use This Project

1. **Start with the main analysis:** Open [discount_analysis.ipynb](notebooks/discount_analysis.ipynb) for the sales overview and product comparisons. 
2. **Review profitability:** Open [profitability_analysis.ipynb](notebooks/profitability_analysis.ipynb) to inspect the margin assumptions and product deep dive.
3. **Prepare the data:** Obtain the three cleaned CSV files from the documented source and place them where the notebooks expect them. Include datasets in the repository only where sharing is permitted.
4. **Install dependencies:** Once the repository contains a verified `requirements.txt`, run:

   ```bash
   python -m pip install -r requirements.txt
   ```

5. **Reproduce the results:** Open the notebooks in Jupyter or Google Colab, check the data paths, and run all cells in order. Run the cleaning workflow first if starting from raw data. **[Link that workflow if it is included.]**
6. **Check the outputs:** Confirm that the analysis reproduces the 114,655-unit category total and the 66-product comparison sample, then export the final plots to `images/`.

## 🚀 Future Work

- **Account for exposure:** Compare units per available selling day in each discount condition, rather than total units alone.
- **Separate seasonal effects:** Control for holiday periods, product lifecycle, and stock availability when assessing discount performance.
- **Improve profit estimates:** Replace assumed category margins with actual procurement costs and incorporate returns, fulfilment costs, and other relevant expenses.
- **Test pricing decisions:** Run controlled promotion experiments to estimate incremental sales and profit by category and product.
- **Extend the product analysis:** Investigate products with contrasting sales patterns and assess whether discount depth changes their contribution to profit.

## 📧 Contact

- **Email:** **m.snchezarias@gmail.com**
- **LinkedIn:** **linkedin.com/in/marco-sanchez-arias**
- **GitHub / Portfolio:** **[https://github.com/m-snchezarias]**
