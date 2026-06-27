# hcmc-property-pipeline (SaiPrice)

A data pipeline for Ho Chi Minh City property listings, with a price prediction model served through a Django API and dashboard.

## What it does

SaiPrice scrapes property listing data from HCMC real estate sites, cleans it, and stores it in PostgreSQL. A Django REST API serves the data, and a dashboard lets visitors browse and filter listings. A machine learning model estimates price from listing features such as location, size, and property type.

## Status

In development. Build started July 2026.

| Stage | Status |
|---|---|
| Scraper | Not started |
| SQL database | Not started |
| Django backend + API | Not started |
| Frontend dashboard | Not started |
| ML price model | Not started |
| Deployment (Render) | Not started |
| Research writeup | Not started |

## Roadmap

Planned for a later phase:

- Price trend charts over time
- Interactive map view of listings

## Tech Stack

- Python: scraping (BeautifulSoup/requests), machine learning (scikit-learn)
- PostgreSQL: database
- Django: backend and REST API
- Django templates + Chart.js: dashboard
- Render: deployment

## Data

Listings are scraped from HCMC real estate sites. If scraped coverage is thin, the project falls back to two public Kaggle datasets: Vietnam Housing Dataset 2024 and House Pricing HCMC.

## Setup

```bash
git clone https://github.com/<your-username>/hcmc-property-pipeline.git
cd hcmc-property-pipeline
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Database setup and environment variable instructions will be added once the backend stage is built.

## License

MIT
