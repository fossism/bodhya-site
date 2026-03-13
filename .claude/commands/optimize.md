# Optimize Command

Run a comprehensive optimization audit on the Bodhya website across code, setup, UX, and interface.

## Instructions

### Phase 1: Code Quality & Build Check
1. Run `zola build` and report any warnings, errors, or compile-time issues
2. Analyze `templates/base.html`:
   - Check for unused CSS rules or redundant selectors
   - Look for repeated CSS patterns that could be abstracted
   - Verify all Tera template syntax is correct
   - Check for inline JavaScript best practices in `static/mobile-menu.js`
3. Review content TOML frontmatter consistency across all markdown files
4. Check for broken internal links in content files (e.g., `[link](../some-page)`)
5. Verify all SVG and image files in `static/` are being used (identify orphaned assets)

### Phase 2: Setup & Configuration
1. Verify `config.toml` settings are optimal:
   - Base URL correct for production
   - Feed generation enabled (good for SEO)
   - Taxonomies configured properly
2. Check `netlify.toml`:
   - Zola version matches what's installed locally
   - Build command is correct
   - Publish directory is correct
3. Ensure `.gitignore` is properly configured (should exclude `public/`)
4. Review `.claude/settings.local.json` — suggest any additional Playwright permissions if needed

### Phase 3: Performance & UX (Use Playwright)
Start `zola serve` at http://localhost:1111, then:

1. **Desktop View (1920px width):**
   - Take full-page screenshot of homepage
   - Verify hero section loads correctly
   - Check all feature cards are aligned and readable
   - Verify footer layout and social icons
   - Test all nav links

2. **Tablet View (768px width):**
   - Take full-page screenshot
   - Check responsive grid layout works
   - Verify text sizing is readable

3. **Mobile View (375px width - iPhone SE):**
   - Take full-page screenshot
   - Open hamburger menu and verify it displays correctly
   - Check text doesn't overlap navigation
   - Verify buttons are finger-friendly (48px+ height)
   - Test tap targets spacing

4. **Accessibility Checks:**
   - Verify color contrast between text and background meets WCAG AA (4.5:1 for body text)
   - Check that all images have alt attributes (if any)
   - Verify semantic HTML (`<header>`, `<main>`, `<footer>`)
   - Check heading hierarchy (`<h1>`, `<h2>`, etc.)

5. **Load Performance:**
   - Report on initial page load time
   - Check for render-blocking resources
   - Suggest image optimization opportunities

### Phase 4: Interface & Design Review
1. **Brand Consistency:**
   - Verify primary color `#AD544B` (terracotta) usage is consistent
   - Verify background `#FFF8F3` (floral white) is used correctly
   - Check that Funnel Display font is applied to display text
   - Verify font weights (300-800 variable range) are appropriate

2. **Visual Hierarchy:**
   - Check hero section stands out
   - Verify section spacing is consistent (padding/margins)
   - Look for visual balance on all pages

3. **Spacing & Alignment:**
   - Check grid alignment on feature cards
   - Verify button spacing and consistency
   - Check footer alignment and spacing

4. **Interactive Elements:**
   - Verify hover states on buttons and links
   - Check button styling matches brand
   - Test mobile menu slide-in animation smoothness

### Phase 5: Summary & Recommendations
Provide a prioritized list of improvements organized by:
- 🔴 **Critical** (breaks functionality or accessibility)
- 🟡 **Important** (impacts UX or performance)
- 🟢 **Nice to Have** (cosmetic or minor improvements)

For each issue, suggest a specific fix with the file and line numbers if applicable.

## Success Criteria
- All build warnings resolved
- No broken links
- Consistent mobile/tablet/desktop experience
- Meets WCAG AA color contrast standards
- All assets are optimized and used
- Setup is production-ready
