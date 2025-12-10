# Stocks – Final Project for EDAV (Fall 2025)

This repo contains my EDAV final project, which explores how COVID-19 and recent market shifts (including the AI boom) affected the **movie/media industry**. I look at:

- U.S. theatrical box office revenue and number of releases  
- AMC’s theatre footprint by state (2019 vs 2024)  
- Stock performance of movie/media companies compared with major sector ETFs  

The project is implemented as a **Quarto book** and styled with the **Litera** Bootswatch theme.

---

## Repo structure

- `index.qmd` – Introduction and overview of the project  
- `data.qmd` – Data description and missing-value analysis  
- `results.qmd` – Main graphs and findings  
- `conclusion.qmd` – Takeaways, limitations, and possible next steps  
- `data/` – Clean CSV files used directly in the book  
- `data-raw/` – Jupyter notebooks and scripts used to download / scrape and clean data  
- `docs/` – Rendered HTML book (output folder for GitHub Pages)

---

## Data sources

1. **U.S. box office by year**  
   - Source: [Box Office Mojo – yearly box office](https://www.boxofficemojo.com/year/)  
   - Collected via `pandas.read_html()` in `data-raw/movie-boxoffice.ipynb`.  
   - Used for total domestic box office, year-over-year change, and number of releases.

2. **Movie/media stock prices (2019–2025)**  
   - Source: [Yahoo Finance](https://finance.yahoo.com/) via the `yfinance` Python package.  
   - Tickers include theater chains (AMC, CNK, IMAX), studios (DIS, CMCSA, PARA, WBD, FOXA), streamers (NFLX, ROKU), diversified media (SONY), plus the S&P 500 index (`^GSPC`).  
   - Downloading and cleaning code: `data-raw/movie-stocks.ipynb`.

3. **Sector ETF prices**  
   - Source: sector ETFs from Yahoo Finance (e.g., technology, energy, financials, etc.), also pulled with `yfinance`.  
   - Used to benchmark movie/media stocks against the broader market.  
   - Cleaning is included in `data-raw/movie-stocks.ipynb`.

4. **AMC theatres and screens by state (2019 vs 2024)**  
   - Source: AMC’s *“U.S. Markets – Theatres & Screens”* tables from the 2019 and 2024 10-K filings on the AMC investor relations site:  
     - 2019 10-K: <https://investor.amctheatres.com/sec-filings/all-sec-filings/content/0001411579-20-000027/amc-20191231x10k.htm>  
     - 2024 10-K: <https://investor.amctheatres.com/sec-filings/all-sec-filings/content/0001411579-25-000042/amc-20241231x10k.htm>  
   - Tables were copied into Excel and saved as `AMC_theatres_screens_by_market_2019.xlsx` and `AMC_theatres_screens_by_market_2024.xlsx` in `data/`.  
   - These are used to calculate percent change in AMC theatres by state and to build the choropleth map.

All scraped / processed data are saved as CSVs in `data/` so the book can be rendered without re-running the scraping notebooks.

---

## Theme

The book uses the **Litera** Bootswatch theme, set in `_quarto.yml`:

```yaml
format:
  html:
    theme: litera
