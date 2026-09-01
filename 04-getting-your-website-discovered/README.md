# 4. Getting Your Website Discovered

*Being technically ready doesn't matter if Google never finds the page in the first place. This chapter is about giving it a path.*

## What This Chapter Covers

This chapter covers how Google actually finds your URLs: internal links, external links, XML sitemaps, and Search Console. It also covers why discovery isn't instant, and what "crawl budget" means for a new or small site.

## Why It Matters

A page with perfect technical SEO and great content is still invisible if nothing points to it. Discovery is the step people forget because it feels passive — you assume that once a site is live, Google will "just find it" eventually. Sometimes it does. Often it doesn't, especially for pages buried deep in a site structure with no internal links pointing to them. Understanding discovery turns that from a waiting game into something you can actively influence.

## Key Concepts

- **Internal links** — links from pages Google already knows about to pages it doesn't. This is the main way large sites get new pages discovered quickly; an orphan page with zero internal links is often the real reason a "published" page never shows up.
- **External links (backlinks)** — links from other websites. These also serve as a discovery path, and additionally act as a trust/authority signal covered more in [Chapter 6](../06-getting-ranked/).
- **XML sitemaps** — submitting `/sitemap.xml` through Search Console gives Google an explicit list of URLs to check, which speeds up discovery especially for new sites with few backlinks yet.
- **Search Console** — Google's direct interface for site owners. Beyond sitemap submission, it lets you manually request indexing for a specific URL and see what Google has and hasn't found.
- **URL discovery** — Google needs *some* path to a URL, whether that's a link or a sitemap entry. No path in, no discovery, regardless of content quality.

## Sitemap Submission (Practical Steps)

1. Generate an XML sitemap listing your important URLs (most frameworks/CMSs can do this automatically).
2. Host it at a predictable path, typically `/sitemap.xml`.
3. Submit it in Search Console under **Sitemaps**.
4. Reference it in `robots.txt` too, so any crawler can find it without Search Console:

```text
Sitemap: https://example.com/sitemap.xml
```

## Why Discovery Can Take Time

Google allocates crawl resources based on a site's perceived size, authority, and update frequency — this is often called *crawl budget*. A brand-new domain with no backlinks and no history starts with very little of it, so new pages may not get crawled for days or weeks even after being submitted. This isn't a bug or a penalty — it's Google being conservative with a site it doesn't have much signal about yet. Consistent publishing and earning even a few quality backlinks tends to speed this up over time.

## In This Chapter

- [On-Page SEO](on-page-seo.md)
- [Internal Linking](internal-linking.md)
- [Content and Keywords](content-and-keywords.md)
