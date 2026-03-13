# Visual Check Command

Quick visual verification of the website at multiple breakpoints using Playwright.

## Quick Overview
- Takes screenshots at desktop (1920px), tablet (768px), and mobile (375px) widths
- Checks for obvious visual glitches
- Verifies brand colors and typography are consistent
- Reports any visual regressions

## Steps
1. Start `zola serve` at http://localhost:1111 if not already running
2. Take screenshots at these viewport sizes:
   - Desktop: 1920x1080
   - Tablet: 768x1024
   - Mobile: 375x812
3. For each screenshot, verify:
   - No text overflow or cutoff
   - Colors match brand (#AD544B terracotta, #FFF8F3 floral white)
   - Typography looks good (Funnel Display for headings, system sans for body)
   - Spacing is consistent
   - All images and logos display correctly
4. Report any visual issues found

## Use This Command When
- Making CSS changes and want to verify they look good
- Before pushing changes to production
- After updating design elements
