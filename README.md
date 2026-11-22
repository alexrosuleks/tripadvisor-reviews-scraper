# Tripadvisor Reviews Scraper: Tripadvisor Scraper API for Python & Node.js (2026)

Scrape Tripadvisor reviews for hotels, restaurants and attractions: rating, title, text, date, trip type and owner reply. No login needed. Export to CSV.

**[▶ Try the Tripadvisor Reviews Scraper free on Scrapely](https://scrape.ly/store/roamandroof/tripadvisor-reviews-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Tripadvisor data with the [Tripadvisor Reviews Scraper](https://scrape.ly/store/roamandroof/tripadvisor-reviews-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the tripadvisor scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Tripadvisor scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/roamandroof/tripadvisor-reviews-scraper) or from your code with the SDK.
- **Structured tripadvisor data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $0.59 per 1,000 review results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Tripadvisor changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Tripadvisor data can you extract?

Scrape Tripadvisor reviews for hotels, restaurants and attractions: rating, title, text, date, trip type and owner reply. No login needed. Export to CSV.

| Output field |
|---|
| `title` |
| `rating` |
| `travelDate` |
| `publishedDate` |
| `text` |
| `url` |
| `user` |
| `ownerResponse` |
| `placeInfo` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('roamandroof/tripadvisor-reviews-scraper').call({"startUrls": [{"url": "https://www.tripadvisor.com/Hotel_Review-g60763-d208453-Reviews-Hilton_New_York_Times_Square-New_York_City_New_York.html"}], "maxItemsPerQuery": 10, "reviewRatings": ["ALL_REVIEW_RATINGS"], "reviewsLanguages": ["ALL_REVIEW_LANGUAGES"], "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["RESIDENTIAL"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('roamandroof/tripadvisor-reviews-scraper').call(run_input={ "startUrls": [ { "url": "https://www.tripadvisor.com/Hotel_Review-g60763-d208453-Reviews-Hilton_New_York_Times_Square-New_York_City_New_York.html" } ], "maxItemsPerQuery": 10, "reviewRatings": [ "ALL_REVIEW_RATINGS" ], "reviewsLanguages": [ "ALL_REVIEW_LANGUAGES" ], "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "RESIDENTIAL" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/roamandroof~tripadvisor-reviews-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "startUrls": [
    {
      "url": "https://www.tripadvisor.com/Hotel_Review-g60763-d208453-Reviews-Hilton_New_York_Times_Square-New_York_City_New_York.html"
    }
  ],
  "maxItemsPerQuery": 10,
  "reviewRatings": [
    "ALL_REVIEW_RATINGS"
  ],
  "reviewsLanguages": [
    "ALL_REVIEW_LANGUAGES"
  ],
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "RESIDENTIAL"
    ]
  }
}
```

See every input option on the [Tripadvisor Reviews Scraper page](https://scrape.ly/store/roamandroof/tripadvisor-reviews-scraper).

## Pricing

**$0.59 per 1,000 review results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/roamandroof/tripadvisor-reviews-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Tripadvisor with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Tripadvisor with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a tripadvisor scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/roamandroof~tripadvisor-reviews-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Tripadvisor legal?** This scraper collects publicly available data. Check Tripadvisor's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Related Tripadvisor scrapers

- [Tripadvisor Scraper](https://github.com/alexrosuleks/tripadvisor-scraper): Scrape Tripadvisor hotels, restaurants and attractions: rating, ranking, price, address, phone, email and amenities. No…

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** tripadvisor reviews scraper, tripadvisor scraper, tripadvisor scraper api, tripadvisor scraper python, tripadvisor scraper node.js,
scrape tripadvisor, tripadvisor data extraction, tripadvisor crawler, tripadvisor api, export tripadvisor data to csv, tripadvisor-reviews-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/roamandroof/tripadvisor-reviews-scraper).
