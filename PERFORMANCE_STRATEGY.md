# Avenue Landing Page Performance Strategy

Status: Wireframe baseline  
Primary target: interactive in under 2 seconds on a mid-range mobile device over a typical 4G connection

## Current Loading Model

The landing page is intentionally static:

- Plain HTML
- One production CSS file
- No JavaScript
- No framework or component library
- No external font request
- One small visible image: the Avenue logo
- No screenshots, video, map SDK, analytics, or third-party embeds

Because the page has no client-side application boot process, it becomes interactive as soon as the HTML is parsed. CSS affects rendering but does not block interaction setup through JavaScript.

## Performance Budget

These are release gates, not suggestions.

| Resource | Budget |
| --- | --- |
| Initial HTML | `<= 10 KB` uncompressed |
| Critical CSS | `<= 15 KB` uncompressed |
| Initial JavaScript | `0 KB` preferred, `<= 10 KB` only if justified |
| Above-the-fold images | `<= 40 KB` total |
| Initial transferred payload | `<= 100 KB` compressed |
| Initial network requests | `<= 6` |
| Third-party requests | `0` before consent |
| Total Blocking Time | `< 100 ms` |
| Largest Contentful Paint | `< 1.8 s` |
| Cumulative Layout Shift | `< 0.05` |
| Interaction to Next Paint | `< 200 ms` |

The requested under-2-second Time to Interactive target is supported by keeping initial JavaScript at zero. We will also monitor LCP, INP, CLS, and Total Blocking Time because they give a more useful picture of current user experience.

## Asset Priorities

### 1. Images

Current priority:

- `assets/avenue-logo-96.png`: approximately `8 KB`
- Explicit `width` and `height` attributes prevent layout shift.
- The landing page does not load the larger source logo or app screenshots.

Rules for future imagery:

- Prefer AVIF, with WebP fallback where needed.
- Export images at the maximum rendered size, not the source-device size.
- Use `srcset` and `sizes` for responsive image selection.
- Keep a hero image below `80 KB`; target `40–60 KB`.
- Keep below-the-fold images below `50 KB` each.
- Add `loading="lazy"` only to below-the-fold images.
- Never lazy-load the LCP image.
- Always include image dimensions or `aspect-ratio`.
- Do not add autoplay video, animated GIFs, or background video to the landing page.

The existing app screenshots are design references. They are not part of the wireframe payload.

### 2. Fonts

Current priority:

- Use the operating system UI font stack.
- No Google Fonts request.
- No font JavaScript.
- No font-related render delay or flash caused by a remote stylesheet.

If a branded font is approved later:

- Self-host one WOFF2 variable font.
- Subset it to the Latin characters actually needed.
- Keep the font file below `40 KB`.
- Use `font-display: swap`.
- Preload only the single above-the-fold font file.
- Do not load separate files for four weights.
- Retain the system stack as fallback.

### 3. Libraries and JavaScript

Current priority:

- No UI framework.
- No animation library.
- No icon library.
- No carousel.
- No map SDK.
- No client-side form framework.
- No JavaScript on the production landing page.

Allowed additions must prove a user-facing requirement that HTML and CSS cannot meet. Any new script requires:

- A stated purpose
- A size estimate
- `defer` or module loading
- No render-blocking placement
- A check against the `10 KB` initial-JavaScript budget

Analytics, chat, heatmaps, and consent tools must not load before consent and must not enter the critical rendering path.

## What We Trimmed

- Removed the Google Fonts `@import`.
- Replaced DM Sans with a system font stack for the wireframe.
- Removed the landing-page reference to `script.js`.
- Replaced the `92 KB` source logo with an approximately `8 KB` display asset.
- Moved interaction-specimen CSS out of the production landing-page stylesheet.
- Kept app screenshots off the production landing page.
- Avoided scroll animation and Intersection Observer code.

## Rendering Rules

- Keep the top of the page server-rendered/static.
- Put essential content directly in HTML.
- Do not hide initial content pending JavaScript.
- Avoid CSS that triggers large layout shifts after load.
- Use CSS Grid and Flexbox without layout-measuring scripts.
- Keep above-the-fold selectors simple.
- Minify HTML and CSS for production deployment.
- Serve Brotli or gzip compression when hosting supports it.
- Use long-lived cache headers for versioned assets.

GitHub Pages handles compression and caching, but filenames should be versioned when assets change significantly to avoid stale caches.

## Verification

Before release:

1. Run Lighthouse mobile in an incognito profile.
2. Test with simulated mobile throttling and a mid-tier device profile.
3. Confirm no third-party requests in the network panel.
4. Confirm the initial page has no JavaScript request.
5. Confirm the LCP asset is not lazy-loaded.
6. Confirm all images have fixed dimensions.
7. Confirm transferred payload and request counts stay within budget.
8. Test once on a real iPhone over cellular data.

Performance is a release criterion. A feature that breaks the budget must be simplified, deferred, or removed.
