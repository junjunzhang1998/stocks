# Movie Stocks – Final Project for EDAV (Fall 2025)

This repo contains source files for my team's final project for our Exploratory Data Analysis and Visualization class. Our project explores how COVID-19 affected the **movie/media industry**. We looked at U.S. theatrical box office revenue and releases, AMC’s theatre footprint by state (2019 vs 2024), stock performance of movie/media companies compared with major sector ETFs, and stock performance of sub-industries within the movie industry. 

## Repo structure

- `index.qmd` – Introduction and overview  
- `data.qmd` – Data description and missing-value analysis  
- `results.qmd` – Main graphs and findings  
- `conclusion.qmd` – Takeaways and next steps  
- `data/` – Clean CSV files used in the book  
- `data-raw/` – Notebooks and scripts for scraping/cleaning  
- `docs/` – Rendered HTML book (for GitHub Pages)

## Data sources (brief)

1. **U.S. box office by year** – Box Office Mojo yearly tables, scraped via `pandas.read_html()` (`data-raw/movie-boxoffice.ipynb`).  
2. **Movie/media stock prices (2019–2025)** – Yahoo Finance via `yfinance` for theaters, studios, streamers, diversified media, and the S&P 500 (`data-raw/movie-stocks.ipynb`).  
3. **Sector ETF prices** – Sector ETFs from Yahoo Finance, used to benchmark movie/media stocks (`data-raw/movie-stocks.ipynb`).  
4. **AMC theatres & screens by state (2019 vs 2024)** – “U.S. Markets – Theatres & Screens” tables from AMC 2019 & 2024 10-Ks, copied to  
   `AMC_theatres_screens_by_market_2019.xlsx` and `AMC_theatres_screens_by_market_2024.xlsx` in `data/`.

All scraped / processed data are saved as CSVs in `data/` so the book can be rendered without re-running the scraping notebooks.

