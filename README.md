# Customer Review Sentiment Analysis

Analyzing unstructured customer reviews to identify what drives negative experiences and where sentiment disagrees with star ratings — turning free-text feedback into a structured, queryable dataset.

**Dataset:** [Yelp Reviews Dataset](https://www.kaggle.com/datasets/omkarsabnis/yelp-reviews-dataset) — 10,000 Yelp reviews with star ratings and free-text content

---

## Project Goals
- Convert unstructured review text into structured sentiment scores
- Identify top complaint themes across low-rated reviews
- Find cases where sentiment and star rating disagree (e.g., positive text, low rating)
- Summarize findings in plain English using an LLM-assisted step

## Tools
`Python (Pandas, NLTK/VADER)` `SQL` `Power BI` `DAX`

## Project Structure
```
Review-Sentiment-Analysis/
├── data/          → raw and cleaned review data
├── sql/           → schema + analysis queries
├── python/        → text cleaning, sentiment scoring, EDA notebook
├── powerbi/       → .pbix dashboard file
├── images/        → dashboard screenshots
└── README.md
```

## Workflow
1. **Python (EDA):** validate data quality, explore review length, user/business review concentration
2. **Python (NLP):** clean review text, run sentiment scoring (VADER), extract keywords per sentiment category
3. **SQL:** store review metadata + sentiment scores; query rating-vs-sentiment mismatches, trends over time
4. **Power BI:** dashboard — sentiment trend over time, top negative themes, rating vs. sentiment scatter
5. **LLM add-on:** auto-generate a plain-English "top complaint themes" summary from the data

## Status
🟡 In progress — Structured EDA complete. NLP/sentiment analysis in progress.

## Key Findings (so far)

**Data quality**
- No missing values across any column (10,000 reviews)
- 3 near-empty reviews (1–4 characters, e.g. "X", "Go") identified and removed
- 2 duplicate review texts found — both legitimate (same user reviewing multiple locations of a chain business), not data errors

**Review activity concentration**
- 75% of reviewers contributed only a single review, while review activity is concentrated among a small group of highly active users (up to 38 reviews from one user) — a right-skewed distribution
- Businesses show a similar pattern: median business has 1 review, while the most-reviewed business has 37

*(More findings to be added as sentiment analysis and Power BI dashboard progress)*

## Dashboard Preview
*(screenshot to be added once Power BI dashboard is built)*
