# 3. Getting Your Website Ready

*Technical foundations that make sure Google *can* crawl and understand your site, before you worry about anything else.*

## What This Chapter Covers

This chapter covers the technical baseline: robots.txt, XML sitemaps, canonical URLs, metadata, HTTP status codes, HTTPS, and mobile accessibility. None of this content ranks your site on its own — it just removes the friction that stops Google from doing its job correctly.

## Why It Matters

Search engines don't get any special access to your site. Googlebot is, functionally, a very fast, very literal visitor — it reads what's actually returned by your server, respects the rules you publish in robots.txt, and gives up if it hits errors or dead ends. A single misconfigured file can block an entire site from being crawled at all, silently. Getting this layer right is table stakes: it doesn't win you rankings, but skipping it can lose you all of them.

## Key Concepts

- **robots.txt** — a plain-text file at your domain root that tells crawlers which paths they're allowed to request. It does *not* hide pages from search results by itself (a disallowed page can still get indexed if it's linked elsewhere); it just blocks crawling.
- **XML sitemap** — a list of URLs you want indexed, usually at `/sitemap.xml`. It's a hint, not a guarantee — think of it as a map you hand Google, not an instruction.
- **Canonical URLs** — a `<link rel="canonical">` tag that tells Google which version of a page is the "real" one when duplicates exist (e.g. with and without a trailing slash, or with tracking parameters).
- **Metadata** — the `<title>` and meta description. These don't directly move rankings, but they shape how Google understands the page and how it's presented in results.
- **HTTP status codes** — `200` means "here's the page." `301`/`302` redirect. `404`/`410` mean gone. `500` means broken. Crawlers treat these very literally; an accidental `404` on a real page removes it from consideration.
- **HTTPS** — encrypted connections are close to a hard requirement now, both for user trust and as a baseline signal search engines expect.
- **Mobile accessibility** — Google primarily crawls and indexes the mobile version of your pages ("mobile-first indexing"). If your mobile page is missing content your desktop page has, that missing content effectively doesn't exist to Google.

## Example: A Minimal robots.txt

```text
User-agent: *
Allow: /

Sitemap: https://example.com/sitemap.xml
```

This allows all crawlers to access the entire site and points them to the sitemap. It's often all a small site needs — the mistake to watch for is an overly broad `Disallow: /` left over from a staging environment.

## Practical Tips

- Check your sitemap actually returns valid XML at its published URL — a 404'd sitemap link is more common than you'd expect.
- Don't block CSS/JS in robots.txt — Google renders pages like a browser, and needs those files to understand the layout.
- Verify canonical tags point to themselves on the "real" version of a page, not accidentally to your homepage.

## In This Chapter

- [robots.txt](robots-txt.md)
- [Sitemap](sitemap.md)
- [Search Console](search-console.md)
