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
🟡 In progress — **Sentiment distribution**-closed
- 89% of reviews scored positive, 9.5% negative, 1.5% neutral — consistent with the star rating distribution skewing toward 4-5 stars.
**VADER limitation identified**
44.9% of 1-star reviews (336 out of 749) were scored as net-positive by VADER, revealing a key limitation of lexicon-based sentiment analysis: it struggles with sarcasm, mixed-sentiment reviews (praise for one aspect alongside criticism of another), and mild negative language that doesn't trigger strong lexicon matches. This highlights why sentiment scores should complement — not replace — star ratings when assessing customer experience.
🟡 In progress-## Limitations
**VADER sentiment scoring on sarcastic/mixed reviews:** 44.9% of 1-star reviews (336 of 749) were initially scored as net-positive by VADER, a lexicon-based sentiment tool that scores text word-by-word without understanding context or sarcasm. This is a known limitation of lexicon-based approaches, not an implementation error.

**Resolution:** combined star rating with VADER's sentiment score to create a `final_sentiment` label — using the rating (a direct signal from the customer) for clear-cut cases, and VADER's judgment only for ambiguous 3-star reviews. This corrected ~10% of labels dataset-wide.

**Scope note:** a context-aware model (e.g. a transformer-based classifier) would likely resolve this limitation more directly, but was considered out of scope for this project to keep the analysis aligned with practical Data Analyst tooling rather than applied ML/NLP.

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
