# Reset Sleep System website

Marketing website for https://resetsleepsystem.com with a blog and generated sitemap. The paid PDF is deliberately excluded.

## One-time Cloudflare Pages setup

Import this GitHub repository using **Pages > Import an existing Git repository**.

| Setting | Value |
| --- | --- |
| Production branch | main |
| Framework preset | None |
| Build command | python3 build.py |
| Build output directory | dist |
| Root directory | leave blank |

No packages, deploy command, server or database required. Connect resetsleepsystem.com under the Pages project's Custom domains after the first successful deployment. Add www and redirect it to the apex if desired. Redirect the default pages.dev hostname to the custom domain with Cloudflare's documented redirect configuration.

Cloudflare rebuilds automatically when changes are saved to main. Never edit dist/: it is disposable build output.

## Blog editing dashboard

1. Open https://app.pagescms.org/ and sign in with GitHub.
2. Authorise Pages CMS to access only this repository.
3. Select LielGama/reset-sleep-system and branch main.
4. Open **Blog posts**. Create or edit a post, then save.
5. Leave **Publish this article** off while drafting. Turn it on to publish, then save.
6. Cloudflare automatically rebuilds the published page, blog listing and sitemap.

The dashboard also exposes **Homepage and SEO**, including the main headline, introduction, title and meta description. Each post supports its own title, meta description, date, URL slug, image, alt text, public-health source link and repeatable text sections. Add an empty line between paragraphs. This initial editor uses structured sections rather than a rich-text editor.

Use lowercase hyphenated slugs, keep published slugs stable, and supply image alt text. Deleting a post or making it a draft removes it from the next successful build and sitemap. The build cleans previous output. Draft content still exists in this public repository; do not put confidential information in drafts. Dates do not schedule publishing: the Publish switch controls inclusion.

## Search launch

Verify a Domain property for resetsleepsystem.com in Google Search Console with the exact TXT record Google supplies. Submit https://resetsleepsystem.com/sitemap.xml once. The sitemap then updates at the same URL when posts change; Google decides when to fetch and index it. Inspect the homepage and posts after launch. Rankings, traffic and sales are not guaranteed.

Structured data identifies the educational ebook and blog articles without invented reviews, qualifications or offers. No analytics, advertising pixels or contact forms are installed. Check the host's actual privacy practices and revise the privacy notice before adding tracking or marketing tools.

Before advertising, verify current price, refund terms, seller identity and support contact on Payhip and add a verified direct contact to the site. The Payhip listing was not accessible for independent verification during development. The original PDF still shows sleepresetsystem.com; correct that in the product source separately. This repository only includes the first-page cover image and never the full paid PDF.

## Developer workflow

Run `python3 build.py` from the repository. The build uses Python's standard library, copies public assets to dist/, generates the pages and includes only published posts in sitemap.xml. Non-main Cloudflare previews carry noindex metadata. Edit build.py for layouts and policy pages; .pages.yml configures the editor.
