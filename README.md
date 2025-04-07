# 📰 Generalized News Scraper

This is a Python script that scrapes news article headlines from any website that offers date-based archives. It is designed to be flexible and easy to customize for different news platforms.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/status-active-brightgreen)

> A flexible and customizable Python script for scraping news article headlines from websites with date-based archives.

---
## 📂 Project Structure

```plaintext
news_scraper/
├── scraper.py              # Main scraper script
├── requirements.txt        # Required Python packages
└── output/                 # Folder where scraped Excel files will be saved
```

## 🔧 Features

- Scrapes article headlines from archive pages.
- Works for an entire year, day-by-day.
- Easily configurable for any news website.
- Includes retry mechanism for failed days.
- Random delays to avoid rate-limiting.
- Saves results as an Excel file.

## 🛠️ Setup Instructions

1. Clone the repository
```plaintext
git clone https://github.com/sipra1304/News_Scrapper.git
cd News_Scrapper
```
2. Install dependencies
```plaintext
pip install -r requirements.txt
```
3. Customize the script
```plaintext
Open scraper.py and modify the following parts:
- BASE_URL: Base URL of the news website.

- ARCHIVE_URL_TEMPLATE: The URL format to reach date-specific archives. You can use placeholders like {year}, {month}, {day}, {starttime}.

- article_filter(): A Python function to define what URLs count as valid article links based on their pattern.
```
### ✅ Example Usage

In scraper.py, set your year and run the script:

python scraper.py
By default, the script will scrape all news article headlines for the entire year specified and save them as an Excel file in the output/ folder.

### 🧩 Customization Guide

1. Archive URL Template
Some websites use a fixed date pattern. Others may include a starttime or offset number. Update the template accordingly:
```plaintext
ARCHIVE_URL_TEMPLATE = "https://example.com/archive/{year}/{month}/{day}/start-{starttime}/"
```
2. Filter Function
Customize the logic for identifying valid article links:

```plaintext
def article_filter(href):
    return "/news/" in href and "/article/" in href
```
You can also refine it to filter specific sections (like /sports/, /city/, etc.).

📦 Output Format

The script saves an Excel file named:
```plaintext
News_Archive_<YEAR>.xlsx
```
Each row contains:

- publish_date
- headline_category
- headline_text
- article_link

## ❗ Disclaimer

This tool is intended for educational and research purposes. Make sure you have permission to scrape content from any news website and that your usage complies with their terms of service.

