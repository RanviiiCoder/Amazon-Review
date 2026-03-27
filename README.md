# Amazon Review Scraper with Sentiment Analysis

A Python-based tool that collects Amazon product reviews and performs sentiment analysis using either OpenAI's GPT API or a rule-based approach. The tool processes reviews, generates summaries, and provides statistical analysis of customer feedback.

## Features

- **Review Collection**: Scrapes Amazon product reviews (with fallback to sample data for demonstration)
- **Dual Sentiment Analysis Modes**:
  - OpenAI GPT-3.5 Turbo (if API key provided)
  - Rule-based analysis (keyword matching)
- **Review Summarization**: Generates concise summaries of each review
- **Data Export**: Saves results to CSV and JSON formats
- **Statistical Analysis**:
  - Sentiment distribution
  - Average ratings
  - Rating vs. sentiment correlation

## Prerequisites

- Python 3.7+
- OpenAI API key (optional - falls back to rule-based analysis if not provided)

## Installation

1. Clone this repository or download the notebook

2. Install required packages:
```bash
pip install requests beautifulsoup4 pandas openai tiktoken fake-useragent
Usage
Running in Google Colab
Open the notebook in Google Colab

Set up your OpenAI API key (optional):

Add to Colab Secrets as OPENAI_API_KEY

Or enter it when prompted

Run all cells sequentially

Running Locally
Ensure all dependencies are installed

Modify the scrape_reviews_with_fallback() function to use your target Amazon product URL

Run the main function:

python
result_df = main()
Code Structure
setup_api_key(): Handles OpenAI API key configuration

scrape_reviews_with_fallback(): Attempts web scraping or falls back to sample data

rule_based_analysis(): Performs sentiment analysis using keyword matching

process_review_with_llm_fallback(): Attempts OpenAI analysis, falls back to rule-based

main(): Orchestrates the entire workflow

diagnostic_check(): Verifies system configuration

Output
The tool generates:

CSV File (amazon_reviews_analysis.csv): Complete analysis with all review data

JSON File (amazon_reviews_analysis.json): Structured data for programmatic access

Sample Output Statistics
text
Sentiment Distribution:
  Positive: 5 reviews (50.0%)
  Neutral: 3 reviews (30.0%)
  Negative: 2 reviews (20.0%)

Average Rating: 4.00 stars

Rating vs Sentiment:
  Negative: 2.50 stars
  Neutral: 4.00 stars
  Positive: 4.60 stars
Configuration Options
MAX_REVIEWS: Number of reviews to process (default: 10)

REQUEST_DELAY: Delay between requests (default: 3 seconds)

MAX_RETRIES: Number of retry attempts (default: 2)

USE_OPENAI: Auto-detected based on API key availability

Limitations
Web scraping may be blocked by Amazon's anti-bot measures

Sample data is used when scraping fails (for demonstration purposes)

Rule-based analysis has limited accuracy compared to LLM-based analysis

Free tier of OpenAI API has rate limits

Troubleshooting
Common Issues
API Key Not Working:

Verify your API key in OpenAI dashboard

Check if you have credits available

The tool will automatically fall back to rule-based analysis

Scraping Blocked:

Amazon may block automated requests

The tool automatically falls back to sample data

Consider using official Amazon API or pre-collected datasets

Rate Limits:

OpenAI free tier has rate limits

The tool will show "Rate limit hit" and fall back to rule-based analysis

Dependencies
requests: HTTP requests for web scraping

beautifulsoup4: HTML parsing

pandas: Data manipulation and analysis

openai: OpenAI API integration

tiktoken: Token counting for OpenAI

fake-useragent: Random user agent generation

License
This project is for educational purposes. Web scraping Amazon may violate their Terms of Service; use responsibly.

Author
Created as part of an assessment project for sentiment analysis and data collection.

Acknowledgments
Sample reviews data for demonstration purposes

OpenAI for GPT API

BeautifulSoup and Pandas libraries
