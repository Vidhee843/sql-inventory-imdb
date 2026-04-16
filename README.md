# SQL Inventory Database & IMDb Web Scraping 🗄️

A data wrangling project combining relational database design, complex SQL querying, and web scraping — covering the full data pipeline from collection to analysis.

## Overview
Two-part project: (1) designed and queried a multi-table relational inventory database, and (2) scraped and enriched 500 top-voted IMDb movies using BeautifulSoup.

## Tech Stack
- **Language:** Python, SQL
- **Libraries:** BeautifulSoup, Pandas, sqlite3
- **Database:** SQLite / MySQL
- **Tools:** Jupyter Notebook

## Part 1 — SQL Inventory Database

### Schema Design
Built a normalized relational database covering:
- Products, suppliers, warehouses, orders
- Complex relationships with foreign keys
- Business-realistic constraints and data

### SQL Queries
Wrote complex queries covering:
- Multi-table **JOINs** (INNER, LEFT, RIGHT)
- **Aggregations** (GROUP BY, HAVING, COUNT, SUM, AVG)
- **Date functions** for order and inventory analysis
- Subqueries and CTEs for supplier/warehouse analysis

## Part 2 — IMDb Web Scraping

### What Was Scraped
- **500 top-voted IMDb movies** (2018–2020)
- Fields: title, rating, votes, genre, director, runtime, year

### Pipeline
1. **Scraping** — BeautifulSoup to extract movie data from IMDb
2. **Cleaning** — handled missing values, type conversion, deduplication
3. **Transformation** — enriched dataset with calculated fields
4. **Export** — clean CSV ready for analysis

## Project Structure
```
sql-inventory-imdb/
│
├── part1_sql/
│   ├── schema.sql          # Database schema creation
│   ├── queries.sql         # All SQL queries with comments
│   └── data/               # Sample data for seeding
├── part2_scraping/
│   ├── scraper.ipynb       # IMDb scraping notebook
│   ├── cleaning.ipynb      # Data cleaning pipeline
│   └── data/               # Raw and cleaned datasets
└── README.md
```

## How to Run

**Part 1 — SQL Database:**
```bash
# Create and seed the database
sqlite3 inventory.db < part1_sql/schema.sql

# Run queries
sqlite3 inventory.db < part1_sql/queries.sql
```

**Part 2 — Web Scraping:**
```bash
# Install dependencies
pip install beautifulsoup4 pandas requests

# Run the scraping notebook
jupyter notebook part2_scraping/scraper.ipynb
```

## Course
MISM 6205 — Data Wrangling for Business, Northeastern University (Fall 2024).
