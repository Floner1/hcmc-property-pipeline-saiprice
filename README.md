# hcmc-property-pipeline-saiprice
# hcmc-property-pipeline (SaiPrice)

A data pipeline for Ho Chi Minh City property listings. It scrapes the data, stores it in SQL, serves it through a Django API, and predicts price with a model trained on it.

## Status

Not started. Start date: July 2, 2026.

## Locked Scope (Summer 2026)

This is the full scope. Every stage ships before the next one starts.

1. **Scraper**: pull property listing data from HCMC real estate sites
2. **SQL Database**: store and normalize scraped listings
3. **Django Backend + API**: serve cleaned data through REST endpoints
4. **Frontend Dashboard**: basic UI to browse and filter listings
5. **ML Price Model**: predict price per listing from property features
6. **Render Deploy**: public deployment
7. **Research Writeup**: document method, data, and findings

No skipping ahead to the ML model because it's more interesting than the scraper.

## Stretch Goals (Year 12, not summer)

- Trend charts
- Map view

Don't touch these until the seven stages above are live in production. Building a map view in July means you've lost scope discipline.

## Open Decisions

These aren't locked yet. Decide before you write code, not while you're writing it.

**Source site for the scraper.** Office data used maisonoffice.vn. Residential listings need a different target. batdongsan.com.vn, nhatot.com, and alonhadat.com.vn are the common options. Pick one to start. Add a second only if the first breaks or has thin coverage.

**SQL engine.** PostgreSQL over SQL Server. It's free on Render and Django's ORM handles it cleanly. Use SQLite locally if you want, but design for Postgres from day one.

**Frontend approach.** Django templates with Chart.js, not a separate frontend framework. A decoupled React frontend looks better on a resume but costs a build step and CORS config you don't need this summer.

## Fallback Datasets

If the scraper breaks, gets rate-limited, or returns thin data, fall back to:

- Vietnam Housing Dataset 2024 (Kaggle)
- House Pricing HCMC (Kaggle)

This keeps the ML model and dashboard stages moving even if the scraper stage stalls.

## Tech Stack

- Python: scraping (BeautifulSoup/requests), ML (scikit-learn)
- PostgreSQL: database
- Django: backend + API
- Django templates + Chart.js: frontend
- Render: deployment

## Setup

```bash
git clone https://github.com/<your-username>/hcmc-property-pipeline.git
cd hcmc-property-pipeline
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Add database setup, environment variables, and migration steps once the Django backend stage starts.

## License

MIT
