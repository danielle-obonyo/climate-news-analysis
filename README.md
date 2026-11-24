# Climate Change and Renewable Energy: Web Scraping and Text Analysis

## 1. Project Overview

This project explores climate change and renewable energy through web scraping and text analysis.

The purpose is to collect at least 50 publicly available news articles, extract their text, generate summaries, and analyze their relevance and sentiment.

### Project Objectives

- Compare BeautifulSoup and Scrapy.
- Benchmark their performance.
- Collect at least 50 climate-related news articles.
- Extract article content using Trafilatura.
- Apply TF-IDF to measure topic relevance.
- Apply VADER to analyze sentiment.
- Generate summaries for each article.
- Calculate positive or negative importance scores.
- Export results into CSV files.

## 2. Web Scraping Library Comparison

### BeautifulSoup

BeautifulSoup is a Python library used to parse HTML and XML documents. It is beginner-friendly and provides a straightforward way to extract information from webpages.

### Scrapy

Scrapy is a Python web crawling framework designed for larger scraping projects. It supports concurrent requests, automatic scheduling and structured data extraction.

### Benchmark Results

Both libraries were tested using the same five downloaded Wikipedia webpages. Each HTML document was processed ten times.

| Measurement | BeautifulSoup | Scrapy Selector |
|---|---:|---:|
| Average processing time per page | 0.2930 seconds | 0.0810 seconds |
| Total processing time (5 pages) | 1.4650 seconds | 0.4048 seconds |
| Pages processed | 5 | 5 |

Scrapy Selector was approximately 3.62 times faster in this particular HTML parsing experiment.

### Selected Library

BeautifulSoup was selected for the main project because it is beginner-friendly, flexible and suitable for collecting 50 or more articles.

Requests was used to download webpages, BeautifulSoup to parse RSS feeds, and Trafilatura to extract article content.

The benchmark measured HTML parsing performance rather than the complete crawling capabilities of Scrapy.

## 3. Data Collection

### Data Source

Publicly available news articles were collected from The Guardian using its RSS feeds.

Topics included:

- Climate Change
- Renewable Energy
- Environment
- Science
- World News

### Data Collection Results

| Measurement | Result |
|---|---:|
| Unique relevant articles discovered | 53 |
| Successfully extracted articles | 50 |
| Failed or skipped articles | 3 |
| Extraction success rate | 94.34% |

### Article Extraction

- Requests retrieved webpage content.
- BeautifulSoup parsed RSS feeds and identified article links and metadata.
- Trafilatura extracted the main article text.

The dataset includes article titles, URLs, topics, publication dates and extracted article text.

## 4. Text Analysis Methods

Two text analysis algorithms were applied to the 50 successfully extracted articles.

### 4.1 TF-IDF (Topic Relevance)

TF-IDF stands for Term Frequency–Inverse Document Frequency.

It measured how closely each article's vocabulary relates to the research topic of climate change and renewable energy.

Cosine similarity compared each article's TF-IDF vector with a predefined topic description.

The relevance score ranges from 0 to 1. A higher score indicates greater similarity to the research topic.

### 4.2 VADER (Sentiment Analysis)

VADER stands for Valence Aware Dictionary and sEntiment Reasoner.

It analyzed the emotional tone of each article.

VADER produces four measurements:

- Positive sentiment
- Negative sentiment
- Neutral sentiment
- Compound sentiment

The compound score ranges from -1 (most negative) to +1 (most positive).

### 4.3 Importance Score

The TF-IDF relevance score and VADER compound sentiment score were combined.

**Formula:**

Importance Score = 100 × Relevance Score × Compound Sentiment

The result ranges from -100 to +100.

- Positive scores indicate positive sentiment combined with topic relevance.
- Negative scores indicate negative sentiment combined with topic relevance.
- Scores close to zero indicate low relevance, neutral sentiment, or both.

### 4.4 Importance Direction

Articles were classified using these thresholds:

- Positive: Importance score greater than +2.
- Negative: Importance score less than -2.
- Neutral: Importance score between -2 and +2.

These thresholds were selected as practical classification rules for this project.

### 4.5 Article Summarization

An extractive summarization technique was implemented using TF-IDF.

The method identifies informative sentences within each article and selects up to three sentences to create a short summary.

The summaries use sentences from the original articles.

## 5. Analysis Results

A total of 50 successfully extracted articles were analyzed using TF-IDF and VADER.

### Importance Direction Distribution

| Direction | Number of Articles | Percentage |
|---|---:|---:|
| Positive | 29 | 58% |
| Neutral | 11 | 22% |
| Negative | 10 | 20% |
| **Total** | **50** | **100%** |

### Findings

The analysis classified 58% of the articles as positive, 22% as neutral and 20% as negative according to the combined importance score.

Articles with higher TF-IDF relevance and positive sentiment received higher positive importance scores.

Articles with higher relevance and negative sentiment received negative importance scores.

Articles with low relevance generally received importance scores closer to zero.

These results describe topic relevance combined with emotional language. They do not necessarily indicate whether an article supports or opposes climate action.

### Limitations

- VADER may not fully understand the context of environmental reporting.
- Negative sentiment does not necessarily mean an article opposes climate action.
- TF-IDF measures word importance and similarity rather than deeper semantic meaning.
- Extractive summaries may occasionally include less informative sentences.
- Results depend on the articles collected and are not representative of all climate news.

## 6. Conclusion

This project demonstrated how Python can be used to collect online news articles and apply text analysis techniques.

The comparison showed that Scrapy Selector was faster in the HTML parsing benchmark, while BeautifulSoup was selected for its simplicity and ease of use.

The combination of TF-IDF, VADER and extractive summarization provided a way to evaluate topic relevance, sentiment and importance across 50 climate-related news articles.

## 7. Installation and Usage

### Requirements

- Python 3.12
- Anaconda or Miniconda
- Jupyter Notebook

### Environment Setup

The project was developed using a Conda virtual environment named `climate-analysis`.

Activate the environment:

```bash
conda activate climate-analysis
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Running the Project

1. Activate the `climate-analysis` environment.
2. Open Anaconda Navigator.
3. Launch Jupyter Notebook using the `climate-analysis` environment.
4. Open the project folder.
5. Run the notebooks in numerical order.
6. Review the collected articles and final results in the `data` folder.

### Output Files

The final analysis is available in `data/analysis_results.csv`.

It contains article URLs, titles, topics, publication dates, summaries, relevance scores, sentiment scores, importance scores and importance directions.

## 8. Project Structure

```text
climate-news-analysis/
├── data/
│   ├── discovered_articles.csv
│   ├── scraped_articles.csv
│   ├── failed_articles.csv
│   └── analysis_results.csv
├── notebooks/
│   ├── 01_setup.ipynb
│   ├── 02_library_comparison.ipynb
│   ├── 03_web_scraping.ipynb
│   └── 04_text_analysis.ipynb
├── reports/
│   └── benchmark_results.csv
├── README.md
└── requirements.txt
```

The actual virtual environment directory is not included in the submission. Its dependencies are listed separately in `requirements.txt`.
