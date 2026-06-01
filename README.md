# Reddit Scraper 💰 $1.25/1K

Scrape Reddit posts with their full nested comment threads, user profiles, and community pages. Search any subreddit or keyword and capture scores, awards and timestamps. Bodies come as AI-ready text, HTML and Markdown for LLMs. No login or developer token is needed.

**[Reddit Scraper 💰 $1.25/1K on Apify →](https://apify.com/blackfalcondata/reddit-scraper?fpr=1h3gvi)**

---

## 🚀 How to use this actor

> ### 💚 $5 free Apify credits — every month
> No credit card required. No commitment. Cancel anytime.

### 👉 [Sign up free on Apify →](https://console.apify.com/sign-up?fpr=1h3gvi)

1. **Click sign up** — pick GitHub, Google, or email; takes ~30 seconds
2. **Open this actor** — input is pre-filled with a working example
3. **Click Start** — export results as JSON, CSV, or Excel

Your **$5 monthly platform credit** is enough to run this actor right away — and again every month — scraping typically several hundred to several thousand results per run, depending on your input.

## Key features

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases

**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from the source on a schedule. Export to CSV, JSON, or directly to your database.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from the source.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

---

## Quick start

```json
{
  "startUrls": [
    {
      "url": "https://www.reddit.com/r/programming/"
    }
  ],
  "sort": "hot",
  "maxItems": 10,
  "maxComments": 50
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `startUrls` | array | — | Reddit URLs to scrape — subreddits, post pages, user profiles, community pages, or search result pages. Each URL determines what type of content is fetched. |
| `searchTerms` | array | — | Search Reddit for these terms. Each entry becomes an independent search. Search posts are lightweight discovery records (plus their comments) — see Search Type. |
| `searchType` | enum | `"posts"` | Type of results to return when using Search Terms. Post results are lightweight discovery records — id, url, title, subreddit and NSFW flag — plus their comment threads; scrape a result's URL directly for its full post fields (author, body, score, timestamp). |
| `sort` | enum | `"hot"` | Sort order for posts and search results. |
| `time` | enum | `"all"` | Restrict subreddit-feed results to a time window (applies to Top sort on feeds; search is not time-windowed). |
| `includeNSFW` | boolean | `false` | Include posts and communities marked as NSFW (18+). |
| `postDateLimit` | string | — | Skip posts older than this ISO-8601 date (e.g. "2024-01-01"). Applies to subreddit feeds and post URLs; search results carry no date and are not filtered. Leave blank for no date limit. |
| `maxItems` | integer | `100` | Maximum total records to save across all sources (posts, comments, users, communities). |
| `maxComments` | integer | `200` | Maximum number of comments to collect from each post page. |
| `includeCollapsed` | boolean | `true` | Expand and include comments that are initially collapsed (controversial or low-score). Enables deeper thread coverage, up to the comment and depth limits you set. |
| `commentDepth` | integer | `10` | Maximum reply nesting depth to collect (1 = top-level only). |
| `skipComments` | boolean | `false` | Do not collect comments from post pages — output posts only. |
| `descriptionFormat` | enum | `"all"` | Controls which body/description fields are included in output. "all" emits text + HTML + markdown variants. |
| `excludeEmptyFields` | boolean | `false` | Strip null and empty fields from output records to reduce payload size. |
| `includeRunMetadata` | boolean | `false` | Append a run-metadata record at the end of the dataset (run ID, timing, item counts). |

---

## Output fields

Every listing returns the same 20-field schema. Missing values are `null` — never omitted.

- `itemType`
- `id`
- `url`
- `title`
- `body`
- `bodyHtml`
- `contentHref`
- `postType`
- `language`
- `score`
- `upvoteRatio`
- `numComments`
- `awardCount`
- `author`
- `authorId`
- `community`
- `communityId`
- `createdAt`
- `icon`
- `nsfw`

---

## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "itemType": "post",
  "id": "t3_1ttjtwv",
  "url": "https://www.reddit.com/r/programming/comments/1ttjtwv/your_process_memory_is_a_file_the/",
  "title": "Your process' memory is a file: The underappreciated gem that is /proc/<pid>/mem",
  "body": null,
  "bodyHtml": null,
  "contentHref": "https://lcamtuf.substack.com/p/weekend-trivia-your-process-memory",
  "postType": "link",
  "language": "en",
  "score": 129,
  "upvoteRatio": 0.9708029197080292,
  "numComments": 1
}
```

*Truncated — full records contain 20 fields. See Output fields for the complete schema.*

**[Try Reddit Scraper 💰 $1.25/1K now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/reddit-scraper?fpr=1h3gvi)**

---

## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.005 |
| Result | $0.00125 |

See the [actor on Apify](https://apify.com/blackfalcondata/reddit-scraper?fpr=1h3gvi) for current pricing.

---

## FAQ

**How much does it cost?**
Pay-per-event pricing — you only pay for listings extracted. Apify's free $5 credit is enough to run thousands of results before you pay anything.

**Do I need an API key or credentials?**
No. Just sign up for Apify, paste your input, and click Start. No credit card required.

---

## Related products by Black Falcon Data

- [Whatnot Scraper](https://apify.com/blackfalcondata/whatnot-scraper?fpr=1h3gvi) — Whatnot live-shopping (social commerce) listings, sellers and shops

[Browse all Black Falcon Data actors →](https://apify.com/blackfalcondata?fpr=1h3gvi)

---

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. Sign up — $5 platform credit included
2. Open [Reddit Scraper 💰 $1.25/1K](https://apify.com/blackfalcondata/reddit-scraper?fpr=1h3gvi) and configure your input
3. Click **Start** — export results as JSON, CSV, or Excel

Need more later? [See Apify pricing](https://apify.com/pricing?fpr=1h3gvi).

---

## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---

*Last updated: 2026 06*
