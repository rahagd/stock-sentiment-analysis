# Exploratory Data Analysis of Financial News Sentiment

Scraping financial news headlines and visualizing sentiment scores for AAPL, TSLA, and NVDA.

## Objective
- Obtain financial news as text
- Visualize sentiment scores of selected companies

## Tools
Python, BeautifulSoup, NLTK (VADER), pandas, matplotlib, seaborn

## Method
1. Scraped ~300 headlines (about 100 per company) from Google News RSS
2. Scored each headline with VADER, extended with a custom financial lexicon
3. Visualized average sentiment and label distribution per company

## Results
![Sentiment overview](sentiment_overview.png)

- AAPL had the highest average sentiment (~0.12), followed by TSLA (~0.08) and NVDA (~0.06)
- NVDA had the largest share of negative headlines (~30%)
## Key Findings
- Cleaned 302 scraped headlines down to 296 after removing 6 duplicates
- Many headlines score exactly 0 (neutral), the largest bin in the distribution
- TSLA shows the most extreme negative outliers (higher volatility); AAPL's median is near zero
- Headline length is practically uncorrelated with sentiment (r = -0.03)
- Daily sentiment is noisy, and time coverage differs by company, so no reliable trend can be claimed
- Source names (e.g. "Yahoo Finance") dominated raw word counts and were removed as noise
- After cleaning, the most frequent terms were topical (SpaceX, merger, iPhone, Barclays, Musk)
  ## Conclusion
Sentiment across AAPL, TSLA and NVDA headlines is mostly mild and close to neutral. Differences between companies are small: AAPL scored highest on average, while TSLA showed the most extreme negative headlines (higher volatility). Headline length has no meaningful relationship with sentiment. Because the sample is small, covers a short and uneven time window, and relies on a general-purpose lexicon (VADER), these results are exploratory and should not be read as trading signals.
## Limitations
- VADER's general-purpose lexicon misreads some financial headlines, so I added custom financial words
- Small sample from a single source and a short time window
- Differences between companies are small and not statistically tested
- time Uneve coverage across companies (RSS returns only recent items)

## Future Work
- Replace VADER with FinBERT (a finance-trained model)
- Collect data over a longer period and from multiple sources

## Files
- `Untitled.ipynb`: the full analysis notebook
- `financial_news_sentiment.csv`: scraped headlines with sentiment scores
- `sentiment_overview.png`: results chart
