# Web Scraping Tools: Buy an API, a No-Code Scraper, or Build It Yourself? ScraperAPI's Plans and Real Per-Page Costs Compared

ScraperAPI's free plan gives you 1,000 credits a month and 5 concurrent threads. Hobby is $49/mo for 100,000 credits and 20 threads, Startup $149/mo for 1,000,000 and 50, Business $299/mo for 3,000,000 and 100. What those credits buy is HTML. The service rotates proxies, runs headless browsers, handles CAPTCHAs and retries failures; your code still does the parsing. If you want to click through a site and download a spreadsheet, no plan below will do that for you.

The rest of this page covers what each tier is sized for, what a single request really costs once credit multipliers apply, three limits that only show up in the feature table, and how the managed-API route compares with the no-code and AI-native tools you have probably already shortlisted.

> **Quick pick.** Test one real target on the free plan first: 1,000 credits/mo, 5 threads, plus a 7-day trial with 5,000 credits that doesn't ask for a card. Move to Hobby if most of your requests are plain pages. Move to Startup if you're hitting Google, Amazon or JavaScript-rendered pages, where a single request costs 5 to 25 credits. You need Business rather than Hobby if you want country-level geotargeting outside the US and EU.
> 👉 [Check the free plan and current prices](https://www.scraperapi.com/pricing?fp_ref=coupons)

## ScraperAPI plans compared

| Plan | Credits / threads | Price | Best for | Start |
| --- | --- | --- | --- | --- |
| Free | 1,000 / 5 | $0 | Testing one target before you pay | [Free plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Hobby | 100,000 / 20 | $49/mo | A single developer on mostly standard pages; US & EU geotargeting only | [Hobby at $49/mo](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Startup | 1,000,000 / 50 | $149/mo | Workloads dominated by 5 to 25 credit requests: marketplaces, SERPs, JS rendering | [Startup at $149/mo](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Business | 3,000,000 / 100 | $299/mo | Country-level geotargeting and unlimited analytics history | [Business at $299/mo](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Scaling | 5,000,000 / 200 | See pricing page | Teams that want pay-as-you-go past the monthly cap | [Scaling tier](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Professional | 10,500,000 / 300 | See pricing page | Recurring crawls in the millions of requests | [Professional tier](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Advanced | 21,500,000 / 500 | See pricing page | The largest published allowance short of a custom deal | [Advanced tier](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Enterprise | 22,000,000+ / 500+ | See pricing page | Custom volume and terms | [Enterprise tier](https://www.scraperapi.com/pricing?fp_ref=coupons) |

The monthly figures above are the ones published for the three entry paid tiers. The four largest tiers are sized by credit volume, and their current numbers plus annual billing options live on the same pricing page. Credits reset when your subscription renews; unused credits do not carry over.

## What ScraperAPI handles, and what it hands back

You send a URL and get the page back. In between, ScraperAPI picks a proxy, spins up a headless browser when the page needs JavaScript, deals with CAPTCHA challenges, and retries requests that fail. There are structured endpoints for common targets: Google, Amazon, and the other marketplaces listed in the credit table below, which return parsed results for those specific sites instead of raw HTML.

For everything else, the response is HTML and the selectors are yours. Your pipeline carries the parser, the schema, and the maintenance loop for when a target changes its markup. That is the honest trade. Teams that already have parsing code get the annoying half of scraping removed: proxy pools, browser fleets, retry logic, CAPTCHA handling. Teams that don't have parsing code are buying a fetch layer and still need to build the rest. Sending a request and getting HTML back in a few seconds is the whole product; nothing in the dashboard writes your extraction logic.

## What one request actually costs

A credit is not a page. A standard page costs 1 credit; harder targets and optional features cost more, and the multipliers are published.

| Request type | Credits |
| --- | --- |
| Standard page | 1 |
| Amazon, Walmart, eBay | 5 |
| Google, Bing (including subdomains) | 25 |
| LinkedIn | 30 |
| Bot-protection bypass (Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX/HUMAN, Akamai) | +10 |
| JavaScript rendering (`render=true`) | 10 |
| Premium proxies (`premium=true`) | 10 |
| Screenshot (`screenshot=true`) | 10 |
| Premium proxies + JS rendering | 25 |
| Ultra premium | 30 (paid plans) |
| Ultra premium + JS rendering | 75 (paid plans) |

Geotargeting, sessions, device type, output format and auto parsing add nothing to the bill.

Divide each plan's price by its allowance and the unit economics become obvious:

| Request | Credits | Hobby ($49) | Startup ($149) | Business ($299) |
| --- | --- | --- | --- | --- |
| Standard page | 1 | $0.49 / 1K | $0.15 / 1K | $0.10 / 1K |
| Page behind Cloudflare | 11 | $5.39 / 1K | $1.64 / 1K | $1.10 / 1K |
| Google SERP | 25 | $12.25 / 1K | $3.73 / 1K | $2.49 / 1K |
| Ultra premium + JS | 75 | $36.75 / 1K | $11.18 / 1K | $7.48 / 1K |

The Hobby to Startup jump is the one that decides most purchases. Startup triples the monthly price for ten times the credits, so every page costs roughly a third of what it costs on Hobby. Turn that around: Hobby's 100,000 credits is 100,000 standard pages, 20,000 Amazon pages, about 9,090 requests to a Cloudflare-protected page at 11 credits, or just 4,000 Google results at 25 credits. A SERP-heavy project that looks comfortably sized on paper can exhaust Hobby in a week.

Two features make the bill predictable before you commit. The Domain Cost Estimator in the dashboard returns the credit cost of any URL, and every response carries an `sa-credit-cost` header showing what that request actually spent. You can also set `max_cost` on a scrape to cap the spend on a single request.
👉 [See what Startup's 1M credits cost per month](https://www.scraperapi.com/pricing?fp_ref=coupons)

## Three limits that aren't in the headline price

**Geotargeting is tiered by plan.** Hobby and Startup cover the US and EU. Country-level targeting anywhere else starts at Business ($299/mo). If your project needs to see prices or ads as they appear in Brazil, Japan or India, the entry plans won't get you there, and that single requirement can double your monthly cost.

**Running out of credits stops the work.** When the allowance is gone, scraping pauses until renewal. Auto-upgrade, which bumps you to the next plan when credits hit zero, is opt-in and available on Hobby and above. Pay-as-you-go overage, billed per credit against a monthly cap you set, only exists from Scaling upward. On Hobby, Startup and Business, a busy month means an upgrade, not a bigger invoice.

**Concurrency overages are rejected, not billed.** Exceed your thread count and you get a 429 response asking you to slow down; there is no surcharge, and the request isn't queued. Analytics history is another small print item: 30 days on Hobby and Startup, unlimited from Business up.
👉 [Compare Hobby and Business on the pricing page](https://www.scraperapi.com/pricing?fp_ref=coupons)

## Which of the four tool categories you actually need

Almost every "best web scraping tools" list mixes four product types that solve different problems. Sort yourself first, then shop.

**Managed scraping API** (ScraperAPI, Oxylabs, Zyte). You have code and a parser, and you want someone else to own proxies, browsers and blocking. This is where ScraperAPI sits.

**AI-native APIs** (Firecrawl, Crawl4AI, ScrapeGraphAI). The output is Markdown or schema-shaped JSON aimed at an LLM, RAG index or agent. Useful when the destination is a model rather than a database table.

**No-code platforms** (Octoparse, Browse AI, ParseHub). Point at elements in a browser, get CSV or Sheets. No parser to maintain, less control over edge cases.

**Open-source frameworks** (Scrapy, Playwright, BeautifulSoup). Free, fully controllable, and you run the infrastructure, the proxy rotation and the retry logic yourself.

Volume gives you a second filter. Under about 1,000 pages a month, free tiers and local scripts cover it. Between 1,000 and 100,000 pages a month, a managed API is usually cheaper than the engineering time and proxy bills behind a homegrown stack. Past 100,000 pages monthly, the cost of blocked and failed requests tends to outweigh the subscription, which is when negotiated enterprise plans start to make sense.

One compliance note before any of this: check the target's robots.txt and terms, and if personal data is involved, keep collection minimal and decide how long you store it. RFC 9309 standardized the robots.txt format in 2022, so there's no ambiguity about what a crawler is expected to read.

## How ScraperAPI compares on price and fit

Competitor prices below are the verified entry figures. Billing units differ, which is why they can't be lined up side by side without conversion.

| Tool | Model | Entry price | Best fit |
| --- | --- | --- | --- |
| ScraperAPI | Managed API, credit-based | Free 1,000 credits; Hobby $49/mo | Developers who want HTML back and will write the parser |
| Firecrawl | AI-native API | $16/mo; free 1,000 credits/mo; 1 credit per basic page | LLM pipelines that want Markdown or structured JSON |
| Oxylabs | Managed API + proxy network | $49/mo for up to 98,000 results; per-1K by target: $0.50 Amazon, $1.00 Google, $1.15 elsewhere, $1.35 with JS | Large e-commerce and SERP work on protected sites |
| Bright Data | Enterprise API + proxy network | Usage-based, from about $1.50 per 1,000 records | Big crawls where getting blocked is the main risk |
| Apify | Actor marketplace + hosting | Free $5/mo credits; Starter $29/mo; Scale $199/mo | Teams that want ready-made scrapers plus somewhere to run them |
| Octoparse | No-code visual scraper | Free 10 tasks; Standard $69/mo billed annually | Analysts who want a point-and-click builder and cloud runs |
| Browse AI | No-code monitoring | Free 50 credits/mo; Starter $19/mo | Recurring monitoring with change alerts, no code |

The pricing-unit problem is worth understanding before you compare any two numbers. Zyte advertises $0.13 per 1,000 requests, but its actual rate for the same volume ranges from $0.06 to $16.08 per 1,000 depending on how hard the target site is. Oxylabs charges different rates per target and adds a premium for JavaScript rendering. Firecrawl and ScraperAPI both use credit systems where a "page" can cost anywhere from 1 to 75 credits. A $49 plan at one vendor and a $49 plan at another can differ by a factor of ten in what they actually deliver on your URLs.

## Don't start on a dead library

Half the tutorials still ranking for scraping queries recommend tools that stopped shipping years ago. If you're building your own stack, skip these:

| Dead tool | Status | Use instead |
| --- | --- | --- |
| PhantomJS | Archived 2018 | Playwright, Puppeteer |
| CasperJS | Depended on PhantomJS | Playwright, Puppeteer |
| Nightmare | Unmaintained since 2020 | Playwright |
| Splash | Deprecated by Scrapinghub | Scrapy-Playwright |
| undetected-chromedriver | Aging, last push July 2025 | Nodriver, Camoufox |
| puppeteer-extra-stealth | Unmaintained since July 2024 | Patchright, Camoufox |
| playwright-stealth | Unmaintained since November 2023 | Patchright, Camoufox |
| curl-impersonate | Unmaintained since July 2024 | curl_cffi |

The replacements are actively maintained and, in the stealth cases, built by people tracking the same detection changes the old plugins stopped following.

## FAQ

**How many pages do the 1,000 free credits actually get me?**
1,000 standard pages, or 200 Amazon pages at 5 credits, or 40 Google results at 25 credits, or roughly 90 requests to a Cloudflare-protected page at 11. Test with the URLs you actually care about, not a homepage.

**Do I still have to write the parser?**
Yes, except for the structured endpoints (Google, Amazon and the other supported marketplaces). Everything else returns HTML, and the selectors, schema and storage are your responsibility.

**Can it get past Cloudflare?**
Bypassing Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX/HUMAN and Akamai is priced at 10 extra credits per request, so it's a supported path rather than an edge case. Whether a specific site works depends on what that site runs and how often it changes; run the URL through the Domain Cost Estimator and set `max_cost` before you scale up.

**What happens when I hit my credit limit mid-month?**
Requests stop until renewal. Auto-upgrade can move you to the next tier automatically if you turn it on. Pay-as-you-go overage only exists from the Scaling tier upward.

**Is there an annual discount?**
Annual plans exist and can renew early for a fresh credit batch. The current discount, currency and billing terms are on the pricing page, and they're worth checking before you pick a tier, since the per-credit rate changes more from tier to tier than from monthly to annual.

## What to pick

If you have working code and need a reliable fetch layer, start on the free plan, run ten of your real URLs through the Domain Cost Estimator, and pick the tier whose credits cover your worst month at the multipliers you actually hit. Standard-page scraping fits Hobby at $49. SERP, marketplace or JavaScript-heavy work usually needs Startup at $149. Country-level geotargeting outside the US and EU forces Business at $299.

If you want a CSV without writing code, Octoparse or Browse AI fits better. If the output feeds an LLM or a RAG index, Firecrawl's Markdown and JSON output saves you a conversion step. If you want full control and have the engineering time, Scrapy and Playwright are free and stay free.

Before you enter card details, confirm three things on the pricing page: the currency and billing period on the tier you chose, whether annual billing lowers the per-credit rate for that tier, and the credit cost of your top three target domains. Those three numbers decide whether the plan you picked survives contact with your actual workload.
👉 [Start on the free plan and price your own URLs](https://www.scraperapi.com/pricing?fp_ref=coupons)
