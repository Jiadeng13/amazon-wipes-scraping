# Amazon Wipes — Web Scraping

Scraping Amazon wipes listings into structured product data, plus a
search-demand analysis of the category.
Personal care category research · Google Colab / Python

## Objective
Extract structured wipes product data from Amazon — brand, count/pack
size, price — and understand the search terms that drive the category.

## What the notebook does (`Amazon_Wipes_Scraping_V2_05202026.ipynb`, 251 cells)
- **Scraping/extraction** — renders Amazon wipes pages with **Playwright**
  and parses them (including complete saved HTML files from Google Drive)
  with **BeautifulSoup**: brand (from URL/title patterns), count and pack
  size via a custom `extract_count_pack_from_text`, price and product
  details → `amazon_wipes_full_extract.csv`.
- **Search-demand analysis** — search terms classified into intent
  categories with the **OpenAI API (GPT-5)**, grouped into concepts with a
  regex-based `group_keyword_concept`, and aggregated into monthly-search
  charts.

## Tools & packages
- **Playwright (async)** — browser automation / page rendering
- **BeautifulSoup (bs4)** — HTML parsing and extraction
- **pandas / numpy** — cleaning and aggregation
- **matplotlib + seaborn** — charts
- **OpenAI API (GPT-5)** — LLM classification of search terms
- **Google Colab** — Drive-mounted HTML files and datasets

## Notes
Shared with credentials redacted — API keys are loaded from Colab Secrets
(`google.colab.userdata`), never hard-coded.
