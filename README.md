Climate Change and Renewable Energy: Web Scraping and Text Analysis
Project Overview

This project explores climate change and renewable energy through web scraping and text analysis.

The purpose of this assignment is to collect at least 50 publicly available news articles, extract their text, generate summaries, and analyze their relevance and sentiment.

The project uses Python libraries to compare web scraping techniques and apply text analysis algorithms.

Project Objectives
Compare BeautifulSoup and Scrapy as web scraping tools.
Conduct a performance benchmark between the two libraries.
Collect at least 50 climate change and renewable energy articles.
Extract article content using Trafilatura.
Apply TF-IDF to measure topic relevance.
Apply VADER to analyze article sentiment.
Generate summaries for each article.
Calculate a positive or negative importance score for each article.
Export the results into a CSV file.

Web Scraping Library Comparison

Two web scraping libraries were compared: BeautifulSoup and Scrapy.

BeautifulSoup

BeautifulSoup is a Python library used to parse HTML and XML documents. It is beginner-friendly and provides a straightforward way to extract information from webpages.

Scrapy

Scrapy is a Python web crawling framework designed for larger scraping projects. It supports concurrent requests, automatic scheduling and structured data extraction.

Benchmark Results

Both libraries were tested using the same five downloaded Wikipedia webpages. Each HTML document was processed ten times.

Measurement	BeautifulSoup	Scrapy Selector
Average processing time per page	0.2930 seconds	0.0810 seconds
Total processing time (5 pages)	1.4650 seconds	0.4048 seconds
Pages processed	5	5

Scrapy Selector was approximately 3.62 times faster in this particular HTML parsing experiment.

Selected Library

BeautifulSoup was selected for the main project because it is beginner-friendly, flexible and suitable for collecting 50 or more articles.

Requests was used to download webpages, BeautifulSoup to parse RSS feeds, and Trafilatura to extract article content.

The benchmark measured HTML parsing performance rather than the complete crawling capabilities of Scrapy.

Data Collection
Data Source

The project collected publicly available news articles from The Guardian using its RSS feeds.

The articles focused on the following topics:

Climate Change
Renewable Energy
Environment
Science
World News
Data Collection Results

A total of 53 unique relevant article URLs were discovered.

Of these:

50 articles were successfully extracted.
3 articles failed or were skipped.
The extraction success rate was 94.34%.
Article Extraction

The Requests library was used to retrieve webpage content.

BeautifulSoup was used to parse RSS feeds and identify article links and metadata.

Trafilatura was used to extract the main article text while reducing unnecessary webpage content.

The collected dataset includes article titles, URLs, topics, publication dates and extracted article text.

Output Files

The collected data was saved as CSV files in the data folder.

Text Analysis Methods

Two text analysis algorithms were applied to the 50 successfully extracted articles.

1. TF-IDF (Topic Relevance)

TF-IDF stands for Term Frequency–Inverse Document Frequency.

It was used to measure how closely each article's vocabulary relates to the research topic of climate change and renewable energy.

Cosine similarity was used to compare each article's TF-IDF vector with a predefined topic description.

The relevance score ranges from 0 to 1. A higher score indicates greater similarity to the research topic.

2. VADER (Sentiment Analysis)

VADER stands for Valence Aware Dictionary and sEntiment Reasoner.

It was used to analyze the emotional tone of each article.

VADER produces four sentiment measurements:

Positive sentiment
Negative sentiment
Neutral sentiment
Compound sentiment

The compound score ranges from -1 (most negative) to +1 (most positive).

3. Importance Score

The TF-IDF relevance score and VADER compound sentiment score were combined to calculate an importance score.

The formula used was:

Importance Score = 100 × Relevance Score × Compound Sentiment

This produces a score between -100 and +100.

A positive score indicates positive sentiment combined with topic relevance, while a negative score indicates negative sentiment combined with topic relevance.

4. Importance Direction

Articles were classified using the following thresholds:

Positive: Importance score greater than +2.
Negative: Importance score less than -2.
Neutral: Importance score between -2 and +2.

These thresholds were selected for this project as practical classification rules.

5. Article Summarization

An extractive summarization technique was implemented using TF-IDF.

The method identifies informative sentences within each article and selects up to three sentences to create a short summary.

The summaries use sentences from the original articles rather than generating new text.

Analysis Results

A total of 50 successfully extracted articles were analyzed using TF-IDF and VADER.

Importance Direction Distribution
Direction	Number of Articles	Percentage
Positive	29	58%
Neutral	11	22%
Negative	10	20%
Total	50	100%
Findings

The analysis classified 58% of the articles as positive, 22% as neutral and 20% as negative according to the combined importance score.

Articles with higher TF-IDF relevance and positive sentiment received higher positive importance scores.

Articles with higher relevance and negative sentiment received negative importance scores.

Articles with low relevance generally received importance scores closer to zero.

These results describe the combination of topic relevance and emotional language. They do not necessarily indicate whether an article supports or opposes climate action.

Limitations
VADER evaluates emotional language and may not fully understand the context of environmental reporting.
Negative sentiment does not necessarily mean an article is against renewable energy or climate action.
TF-IDF measures word importance and similarity rather than deeper semantic meaning.
Extractive summaries may occasionally include headings or sentences that are less informative.
The results depend on the articles collected and should not be considered representative of all climate news.
Conclusion

This project demonstrated how Python can be used to collect online news articles and apply text analysis techniques.

The comparison showed that Scrapy Selector was faster in the HTML parsing benchmark, while BeautifulSoup was selected for its simplicity and ease of use.

The combination of TF-IDF, VADER and extractive summarization provided a way to evaluate topic relevance, sentiment and importance across 50 climate-related news articles.

Installation and Usage
Requirements
Python 3.12
Anaconda or Miniconda
Jupyter Notebook
Environment Setup

The project was developed using a Conda virtual environment named climate-analysis.

To activate the environment:

bash
conda activate climate-analysis

Install Dependencies

Install the required Python packages using:

bash
pip install -r requirements.txt

Running the Project
Activate the climate-analysis environment.
Open Anaconda Navigator.
Launch Jupyter Notebook using the climate-analysis environment.
Open the project folder.
Run the notebooks in numerical order.
Review the collected articles and final analysis results in the data folder.
Output Files

The final analysis is available in:

data/analysis_results.csv

This file contains the article URLs, titles, topics, publication dates, summaries, relevance scores, sentiment scores, importance scores and importance directions.

Project Structure
text
climate-news-analysis/
│
├── data/
│   ├── discovered_articles.csv
│   ├── scraped_articles.csv
│   ├── failed_articles.csv
│   └── analysis_results.csv
│
├── notebooks/
│   ├── 01_setup.ipynb
│   ├── 02_library_comparison.ipynb
│   ├── 03_web_scraping.ipynb
│   └── 04_text_analysis.ipynb
│
├── reports/
│   └── benchmark_results.csv
│
├── requirements.txt
└── README.md


The actual virtual environment directory is not included in the submission.