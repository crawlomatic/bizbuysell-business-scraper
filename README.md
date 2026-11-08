# BizBuySell Business For Sale Scraper | M&A & Private Equity Data

[![Apify Store](https://img.shields.io/badge/Apify%20Store-View%20Actor-brightgreen?logo=apify)](https://apify.com/misterkhan/bizbuysell-scraper)
[![GitHub stars](https://img.shields.io/github/stars/crawlomatic/bizbuysell-business-scraper?style=social)](https://github.com/crawlomatic/bizbuysell-business-scraper)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Python SDK](https://img.shields.io/badge/SDK-Python-3776AB?logo=python&logoColor=white)](https://github.com/apify/apify-client-python)
[![Node.js SDK](https://img.shields.io/badge/SDK-Node.js-339933?logo=node.js&logoColor=white)](https://github.com/apify/apify-client-js)

> Scrape businesses for sale, franchise opportunities, EBITDA, cash flow, gross revenue, and broker contacts across North America.

---

## ⚡ Quick Start

You can run this scraper directly via the **[Apify Store Web Console](https://apify.com/misterkhan/bizbuysell-scraper)** with zero setup, or integrate it into your Python / Node.js backend using the code below.

### 🐍 Python Quickstart

```bash
pip install apify-client
```

```python
from apify_client import ApifyClient

# Initialize the ApifyClient with your API token
# Get your token from https://console.apify.com/account/integrations
client = ApifyClient("YOUR_APIFY_TOKEN")

# Configure input parameters
run_input = {
  "startUrls": [
    {
      "url": "https://www.bizbuysell.com/businesses-for-sale/"
    }
  ],
  "maxItems": 25
}

print("🚀 Launching BizBuySell Business For Sale Scraper | M&A & Private Equity Data on Crawlomatic Engine...")
run = client.actor("misterkhan/bizbuysell-scraper").call(run_input=run_input)

# Fetch results from the Actor's default dataset
dataset_items = client.dataset(run["defaultDatasetId"]).list_items().items
print(f"✅ Successfully fetched {len(dataset_items)} records!")

for item in dataset_items[:3]:
    print(item)
```

---

### 🟢 Node.js / JavaScript Quickstart

```bash
npm install apify-client
```

```javascript
import { ApifyClient } from 'apify-client';

// Initialize the ApifyClient with your API token
const client = new ApifyClient({
    token: 'YOUR_APIFY_TOKEN',
});

// Configure input parameters
const input = {
  "startUrls": [
    {
      "url": "https://www.bizbuysell.com/businesses-for-sale/"
    }
  ],
  "maxItems": 25
};

console.log('🚀 Launching BizBuySell Business For Sale Scraper | M&A & Private Equity Data...');
const run = await client.actor('misterkhan/bizbuysell-scraper').call(input);

// Fetch results
const { items } = await client.dataset(run.defaultDatasetId).listItems();
console.log(`✅ Extracted ${items.length} records!`);
console.dir(items.slice(0, 3));
```

---

## What does BizBuySell Business Listings Scraper do?

BizBuySell Business Listings Scraper is an SMB acquisition, search fund, and M&A deal-sourcing tool that extracts **businesses for sale and franchises** directly from **BizBuySell.com**—capturing asking prices, annual owner cash flow / Seller's Discretionary Earnings (`cash_flow`), gross revenue (`gross_revenue`), city/county/state locations, business overview descriptions, and intermediary/broker details.

Whether you are screening cash-flowing service, HVAC, plumbing, manufacturing, or e-commerce businesses by SDE multiple (asking_price / cash_flow), building private equity roll-up pipelines, or connecting with active business brokers across the United States, this scraper delivers clean, structured records in seconds.

> 🛡️ **Zero Proxy Configuration Required:** Anti-blocking and regional routing are **handled automatically out of the box** — just paste your target URLs and click **Start**.

## What data can you extract with BizBuySell Business Listings Scraper?

**🏪 Business Headline & Identity** — listing `title`, unique BizBuySell listing `id`, and canonical `url` <br>
**💵 Asking Purchase Price** — formatted `asking_price` and parsed numeric `asking_price_raw` <br>
**📈 Cash Flow (SDE) & Gross Revenue** — reported annual owner `cash_flow` and top-line `gross_revenue` for instant valuation multiple screening <br>
**📍 Geographic Location** — `location` (city, county, and state) <br>
**📝 Business Summary & Intermediary** — executive `description` excerpt and listing business broker / M&A intermediary firm <br>

## Why scrape businesses for sale from BizBuySell?

**💪 Screen thousands of SMB acquisition targets by Cash-Flow Multiple** — export `asking_price` and `cash_flow` into Excel or Python to immediately isolate businesses trading at 2.5x–3.5x Seller's Discretionary Earnings (SDE) <br>
**🕵️ Power Search Fund and SBA 7(a) acquisition pipelines** — monitor newly listed HVAC, landscaping, medical, logistics, and B2B service companies across your target states before competing buyers see them <br>
**✨ Build active business broker relationship lists** — extract broker names across regional markets to source off-market deal flow or offer SBA lending, QoE accounting, and legal services <br>
**👍 Zero proxy or account setup** — built-in anti-blocking and residential proxy routing work out of the box <br>
**📩 Automate daily deal-flow alerts** — connect recurring runs to Google Sheets, Airtable, Notion, Make, or n8n <br>

## How do I use BizBuySell Business Listings Scraper?

BizBuySell Business Listings Scraper is designed for fast, zero-configuration operation in Apify Console:

1. Click **Try for free** on the Actor page to open Apify Console.
2. Paste one or more BizBuySell state, city, or industry search URLs into **Start URLs** (for example, `https://www.bizbuysell.com/california-businesses-for-sale/`).
3. Set **Max Results** (`maxItems`) to control how many business-for-sale listings to collect.
4. Click **Start** to launch the extraction run.
5. Download your SMB deal-flow dataset from the **Dataset** tab in Excel, CSV, JSON, or HTML table format.

## Input

BizBuySell Business Listings Scraper accepts a simple 2-parameter JSON configuration. Click on the [Input tab](https://apify.com/misterkhan/bizbuysell-scraper/input-schema) for the interactive form.

```json
{
  "startUrls": [
    {
      "url": "https://www.bizbuysell.com/california-businesses-for-sale/"
    }
  ],
  "maxItems": 30
}
```

**🏪 `startUrls`** — array of BizBuySell search URLs by state, metro, county, or industry vertical (e.g., `https://www.bizbuysell.com/california-businesses-for-sale/` or `https://www.bizbuysell.com/texas/service-businesses-for-sale/`) <br>
**🔢 `maxItems`** — maximum number of business-for-sale listings to collect per run (default: 30; Free plan runs collect up to 30 listings per run, while paid Apify plans support unlimited bulk runs) <br>

## Output sample

Results are streamed in real time to your default Apify Dataset. Each record represents a normalized BizBuySell business-for-sale listing with asking price, cash flow, gross revenue, and broker details:

```json
[
  {
    "id": "2249183",
    "title": "Established HVAC Service & Installation Company",
    "location": "Orange County, CA",
    "asking_price": "$1,650,000",
    "asking_price_raw": 1650000,
    "cash_flow": "$485,000",
    "gross_revenue": "$2,400,000",
    "description": "30-year commercial and residential HVAC contractor with 65% recurring maintenance contracts...",
    "broker": "Sunbelt Business Brokers",
    "url": "https://www.bizbuysell.com/Business-Opportunity/established-hvac-service-company/2249183"
  }
]
```

## How much does it cost to scrape BizBuySell business listings?

BizBuySell Business Listings Scraper uses **Pay-Per-Event (PPE)** pricing (apify-default-dataset-item) with a `$0.00` startup fee—you only pay for business listings delivered to your dataset:

**🆓 Free plan** — `$0.005` per listing ($5.00 / 1,000 listings, up to 30 listings/run) <br>
**🥉 Starter (Bronze) plan** — `$0.0014` per listing ($1.40 / 1,000 listings) <br>
**🥈 Scale (Silver) plan** — `$0.001` per listing ($1.00 / 1,000 listings) <br>
**🥇 Business+ (Gold) plan** — `$0.00075` per listing ($0.75 / 1,000 listings) <br>

With the monthly free credit on the Apify Free plan, you can extract **up to 1,000 BizBuySell business listings per month for free**.

> 💡 **Predictable, All-Inclusive Pay-Per-Event Pricing:** There is a **`$0.00` run start fee** and **no separate proxy configuration required**. You only pay the flat per-result rate above for data successfully delivered to your dataset — works out of the box on both **Free** and **Paid** Apify plans.

## How many results can you scrape with BizBuySell Business Listings Scraper?

BizBuySell Business Listings Scraper can extract **thousands of active business-for-sale listings per run** on paid Apify plans (up to 30 listings per run on the Free plan). Keep these tips in mind when building SMB acquisition feeds:

- **Undisclosed Cash Flow / Gross Revenue** — on BizBuySell, some sellers or brokers choose not to disclose `cash_flow` or `gross_revenue` on the public search card until a buyer signs a Non-Disclosure Agreement (NDA). When a seller hides those figures, the field returns "Not Disclosed" or null while still capturing `asking_price`, `location`, `description`, and broker.
- **Combine state and industry URL filters** — apply any industry category (service-businesses, manufacturing-businesses, restaurants), price range, or cash-flow filter on BizBuySell.com in your browser and paste the resulting URL into `startUrls`.
- **Pair with Google Maps for proprietary off-market deal sourcing** — combine listed BizBuySell deals with our [Google Maps B2B Lead & Contact Scraper](https://apify.com/misterkhan/google-maps-scraper) to identify off-market local competitors in the same county.

## Want to enrich businesses for sale with Google Maps, Emails, or Reviews?

Combine BizBuySell Business Listings Scraper with our published B2B acquisition and real estate Actors:

📍 **[Google Maps Places Scraper](https://apify.com/misterkhan/google-maps-scraper)** — extract local brokerages, property managers, commercial businesses, phones, websites, and ratings (From $0.55 / 1K) <br>
📧 **[Website Contact & Email Scraper](https://apify.com/misterkhan/contact-enricher-scraper)** — crawl brokerage and company domains for verified business emails, phone numbers, and social links (From $0.60 / 1K) <br>
⭐ **[Trustpilot Reviews Scraper](https://apify.com/misterkhan/trustpilot-reviews-scraper)** — extract company customer reviews, star ratings, verification status, and business replies (From $0.50 / 1K) <br>
🏡 **[Zillow Search Scraper](https://apify.com/misterkhan/zillow-scraper)** — extract US homes for sale, rentals, sold prices, Zestimates, beds/baths, and coordinates (From $0.90 / 1K) <br>
## Integrations and BizBuySell Business Listings Scraper

BizBuySell Business Listings Scraper integrates seamlessly with your search fund CRM, underwriting models, and automation tools via [Apify integrations](https://apify.com/integrations):

- **No-Code Automation** — trigger instant Slack or email alerts when businesses matching your cash-flow multiple hit the market via Make, Zapier, n8n, or Clay.
- **Spreadsheets & Deal Trackers** — sync business-for-sale records directly into Google Sheets, Airtable, Notion, HubSpot, Pipedrive, or BigQuery.
- **Webhooks** — send newly scraped listings to your AI deal-memo generator via HTTP webhook the moment a run completes.

## Using BizBuySell Business Listings Scraper with the Apify API

You can launch deal-sourcing runs and fetch dataset items programmatically using the official `apify-client` libraries for **Node.js** and **Python**, or connect this Actor directly to AI M&A screening agents via the **Apify MCP Server** (`https://mcp.apify.com`).

Check the [API tab](https://apify.com/misterkhan/bizbuysell-scraper/api) for ready-to-copy Node.js, Python, and cURL examples.

## Frequently asked questions about BizBuySell Business Listings Scraper

**📈 Does the scraper extract both Cash Flow (`cash_flow`) and Gross Revenue (`gross_revenue`)? <br>**
Yes. Whenever a seller publishes Cash Flow (Seller's Discretionary Earnings) or Gross Revenue on BizBuySell, both metrics are extracted alongside `asking_price` and `asking_price_raw`.

**🏪 Can I scrape specific industry categories (like HVAC, Laundromats, or SaaS/Online businesses)? <br>**
Yes. Select any industry or sub-sector on BizBuySell.com in your browser, copy the filtered URL from your address bar, and paste it into `startUrls`.

**🛡️ Do I need to configure proxies or a BizBuySell account? <br>**
**No — everything works out of the box with zero setup.** Regional routing, session management, and anti-blocking are handled automatically so you do not need to configure custom proxy settings.

## Is it legal to scrape public business-for-sale listings from BizBuySell?

Our scrapers are ethical and only extract publicly available business-for-sale listing summaries (asking prices, published cash flow/revenue figures, blind location labels, and public broker attributions) displayed to visitors on BizBuySell.com. They do not bypass NDAs or access confidential CIMs. For more details on the legality of web scraping, read Apify's guide on [is web scraping legal](https://blog.apify.com/is-web-scraping-legal/).

## Your feedback

We keep this Actor under active maintenance. If a run finishes successfully but returns fewer results than you expected, hangs, or errors — please **open an Issue before posting a public review** so we can diagnose and fix it for you.

**🛠️ How to report** — Use the Actor’s [Issues tab](https://apify.com/misterkhan/bizbuysell-scraper/issues/open) in Apify Console. Include the run ID, your input JSON, and what you expected vs. what you got. <br>
**⏱️ Response time** — We aim to reply within 24 hours on business days. <br>
**⭐ Reviews** — Happy with the results? A short positive review helps other users find a reliable scraper. Ran into a problem? Open an Issue first — we’ll work with you to resolve it before you leave a rating. <br>


---

## 🛡️ Architecture & Engine Reliability

This scraper runs on the **[Crawlomatic Engine](https://crawlomatic.com)**:
- **Zero Proxy Configuration:** Intelligent residential and datacenter proxy rotation with automated regional ccTLD binding.
- **WAF Bypass Engine:** Autonomous challenge solving for Cloudflare Turnstile, DataDome, PerimeterX, Kasada, and Akamai.
- **Pay-Per-Event (PPE) Pricing:** Transparent pay-as-you-go pricing with \$0 starting fee.

## 📄 License

Apache License 2.0. See [LICENSE](LICENSE) for details.

Developed & Maintained by **[Crawlomatic](https://crawlomatic.com)**.
