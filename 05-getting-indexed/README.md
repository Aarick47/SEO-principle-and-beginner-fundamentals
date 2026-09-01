# 5. Getting Indexed

*Crawling and indexing are not the same thing. A page can be visited by Googlebot and still never make it into search results.*

## What This Chapter Covers

This chapter covers what indexing actually means, why a page Google has crawled might still be left out of the index, and the tools (like Search Console's URL Inspection) you use to find out why.

## Why It Matters

This is where a lot of beginner troubleshooting goes wrong. People check that Googlebot *visited* their page (via server logs or Search Console's crawl stats) and assume that's the same as being indexed. It isn't. Crawling is Google reading the page. Indexing is Google deciding the page is worth keeping and serving. A page can fail that second step for reasons that have nothing to do with whether it was reachable.

## Crawling vs. Indexing

- **Crawling**: Googlebot requests the URL and downloads/renders the content.
- **Indexing**: Google evaluates that content and decides whether to store it as a candidate for search results.

A crawled-but-not-indexed page usually means Google saw it and passed. That's a signal worth investigating, not ignoring.

## Why a Crawled Page May Not Get Indexed

- **`noindex` directive** — either a meta tag or an HTTP header explicitly telling Google not to index the page.
- **Thin or low-value content** — pages with very little unique text (placeholder pages, near-empty category pages) are common candidates for exclusion.
- **Duplicate content** — if the page is highly similar to another indexed page, Google may fold it into that page instead of indexing it separately.
- **Canonicalization pointing elsewhere** — if the canonical tag names a *different* URL as the authoritative version, Google will generally index that one instead.
- **robots.txt blocking** — technically prevents crawling rather than indexing, but the practical effect on visibility is the same.

## Example: Blocking a Page From the Index

```html
<meta name="robots" content="noindex">
```

Unlike `robots.txt`, this tag doesn't stop the page from being crawled — Google still requests it, reads the tag, and then deliberately leaves it out of the index. That distinction matters: use `noindex` (not `robots.txt`) when you want a page crawled but excluded from results, like a thank-you page or an internal search results page.

## Canonicalization and Duplicate Content

The same content is often reachable at multiple URLs without anyone intending it — `https://` vs `http://`, `www` vs no `www`, trailing slash vs none, or URLs with tracking parameters like `?utm_source=`. Google tries to group these into one canonical version so it doesn't index (and dilute) the same content multiple times. A `<link rel="canonical">` tag on each variant, pointing to the one you consider authoritative, makes that decision explicit instead of leaving it to Google's guesswork.

## Search Console's URL Inspection Tool

This is the most direct way to answer "why isn't this specific page indexed?" Paste in a URL and it shows the last crawl date, whether the page is indexed, and — if it isn't — the specific reason Google gives (excluded by `noindex`, duplicate without user-selected canonical, crawled but not indexed, etc.). It also has a "Request Indexing" action for after you've fixed the underlying issue.

## Sitemap vs. Indexing

A sitemap only tells Google a URL exists and asks it to be considered — it's not a directive to index it. Plenty of sitemap URLs never get indexed if Google judges them low-value. Submitting a sitemap helps with discovery; it has no direct control over the indexing decision.

## In This Chapter

- [What I Learned](what-i-learned.md) — a first-person account of hitting these exact issues on a real deployed site.
