# SEO Check Command

Audit the website for search engine optimization best practices.

## Content Checks
1. **Frontmatter Analysis:**
   - Verify all pages have `title` and `description` in TOML frontmatter
   - Check description lengths (120-160 characters ideal)
   - Look for duplicate descriptions across pages
   - Verify meta descriptions are compelling

2. **Heading Hierarchy:**
   - Check each page has exactly one `<h1>` tag (the main title)
   - Verify heading hierarchy is logical (no skipping from h1 to h3)
   - Check that headings are descriptive

3. **Content Quality:**
   - Check page length (aim for 300+ words for blog posts, 150+ for pages)
   - Look for keyword usage in titles and first paragraphs
   - Verify internal linking (pages should link to related content)

## Technical Checks
1. **Sitemap & Feeds:**
   - Verify `sitemap.xml` is generated (check `public/sitemap.xml`)
   - Verify RSS feed is generated (check `public/feed.xml`)
   - Both should be referenceable from homepage

2. **URL Structure:**
   - Check URLs are clean and descriptive
   - Verify no duplicate content at different URLs
   - Check URL slugs match content

3. **Open Graph Meta Tags:**
   - Look for og:title, og:description, og:image in base.html
   - Verify they're present and populated dynamically

4. **Structured Data:**
   - Check if organization schema is included in base.html
   - Consider adding breadcrumb schema for pages

## Social & Mobile
1. **Mobile Friendliness:**
   - Use Playwright to verify mobile viewport works
   - Check touch targets are 48px minimum
   - Verify responsive images load correctly

2. **Social Sharing:**
   - Verify Open Graph image is available
   - Check social meta tags are correct

## Report Format
Provide findings grouped by:
- ✅ **Passed** - Already optimized
- ⚠️ **Warning** - Could be improved
- ❌ **Failed** - Needs attention

For each issue, suggest specific improvements with file locations.

## Quick Wins
Often includes:
- Adding missing descriptions to pages
- Improving heading structure
- Adding internal links
- Creating/updating sitemap
- Optimizing image alt text
