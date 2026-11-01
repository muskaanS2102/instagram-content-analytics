# Sales Insights Analysis — D2C Spice Brand

Analysis of two years of e-commerce sales for a direct-to-consumer spice brand, sold through Amazon, Flipkart, its own website and Instagram. The project answers four questions: where the revenue comes from, how much the Diwali season matters, which channels are worth investing in, and what 2026 might look like.

**Tools:** Python (pandas, matplotlib), SQL (SQLite), Jupyter

> **About the data:** The dataset is **synthetic**. I generated it with `src/generate_data.py` and modelled it on how a real D2C food brand operates: festive demand spikes, marketplace discounts, returns and a slow shift toward own channels. "Tadka & Co." is a fictional brand. Using synthetic data keeps real business numbers private while the analysis approach stays the same.

![Monthly revenue](images/monthly_revenue.png)

## Key findings

| | |
|---|---|
| **Revenue growth** | Net revenue grew **12%** from ₹46.4 lakh (2024) to ₹52.1 lakh (2025) |
| **Diwali effect** | Daily revenue in the 3 weeks before Diwali is **2.5×** the normal level |
| **Hero product** | The Festive Gift Box makes the most revenue of any product (~₹35 lakh net over two years) |
| **Channel shift** | The Website and Instagram share rose from **31% → 40%**, while Amazon fell from 46% → 39% |
| **Channel quality** | The Website has the lowest discount (8.7%) and return rate (2.9%). Flipkart has the highest of both (15.7% / 7.9%) |
| **2026 forecast** | ~₹58 lakh net revenue, with October as the peak month |

![Channel scorecard](images/channel_scorecard.png)

## Recommendations

1. **Plan stock and ads around Diwali.** Build up Gift Box and Saffron inventory by mid-September.
2. **Keep growing the Website and Instagram channels.** They need the smallest discounts and have the fewest returns, so each sale keeps more margin.
3. **Look into Flipkart's returns.** It has the highest discounts and the most returns, so check packaging and listing accuracy before spending more there.
4. **Use the Gift Box to win new customers**, then bring them back with basic-spice refills during the rest of the year.

## Project structure

```
├── analysis.ipynb        # full analysis with charts
├── sql/queries.sql       # business questions written in SQL
├── src/generate_data.py  # synthetic data generator (seeded, reproducible)
├── data/                 # orders.csv (~48k line items), products.csv
└── images/               # exported charts
```

## How to run

```bash
pip install pandas matplotlib jupyter
python src/generate_data.py      # recreates the dataset
jupyter notebook analysis.ipynb
```

## What I'd do next
- Replace the simple seasonal forecast with Prophet or SARIMA and measure its accuracy on held-out months
- Customer-level analysis (repeat purchase rate, RFM segments) once customer IDs are added
- A Power BI or Streamlit dashboard for the sales team
