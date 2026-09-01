# 2. Understanding Google

*Before you touch a single setting, you need a mental model of what Google is actually doing with your site.*

## What This Chapter Covers

This chapter breaks down the pipeline a page goes through on its way to appearing in search results: **discovery → crawling → indexing → ranking**. Every later chapter in this guide maps to one of these stages. Understanding the pipeline is what lets you diagnose *where* a page is stuck instead of guessing.

## Why It Matters

"My site isn't showing up in Google" isn't one problem — it's four possible problems, and the fix is different for each. A page that hasn't been discovered needs links or a sitemap. A page that's discovered but not crawled might be blocked by robots.txt. A page that's crawled but not indexed might have a `noindex` tag or thin content. A page that's indexed but not ranking is a relevance and quality problem, not a technical one. You can't fix the right problem until you know which stage you're actually in.

## The Four Stages

- **Discovery** — Google learns your URL exists. This happens through links from other pages, an XML sitemap, or a manual request in Search Console. No discovery, no crawl.
- **Crawling** — Googlebot requests the page and reads (and renders) what's there — HTML, and increasingly the JavaScript-rendered output too.
- **Indexing** — Google decides whether the page is worth storing, understands its content, and resolves which version is canonical if duplicates exist.
- **Ranking** — for a given search query, Google orders the indexed pages it considers relevant. This is the only stage that's query-dependent; a page doesn't have "a ranking," it has a ranking *per search term*.

## How These Stages Connect

They're sequential, but not guaranteed. Discovery doesn't force a crawl (crawling is prioritized by crawl budget and perceived importance). A crawl doesn't force indexing (Google filters out low-value or duplicate pages). Indexing doesn't force a ranking anywhere useful (an indexed page with three sentences of text can lose to a competitor with real substance). Each stage is a filter, not a formality.

## How Google Discovers URLs

In practice, Google finds new URLs through:

- **Links** — from other indexed pages, internal or external.
- **XML sitemaps** — a machine-readable list of URLs you want crawled, submitted through Search Console.
- **Manual submission** — the "Request Indexing" option in Search Console's URL Inspection tool.

A page with zero links pointing to it and no presence in a sitemap is called an *orphan page* — Google has no path to find it at all, no matter how good the content is.

## In This Chapter

- [Crawling, Indexing, Ranking](crawling-indexing-ranking.md)
- [How Google Discovers Pages](how-google-discovers-pages.md)
