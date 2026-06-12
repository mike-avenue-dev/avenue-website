# Avenue App Visual Audit

Sources:

- `IMG_1130.PNG`: Explore map and event preview
- `IMG_1133.PNG`: Event management list

Status: Proposed app-derived landing-page style guide  
Method: Values are inferred from 3x iPhone screenshots and normalized to CSS-like points. Exact source design files may differ by 1–3px or by minor color-rendering variation.

## Executive Summary

The app’s visual identity is defined by:

- Near-black navy typography rather than dark teal typography
- Warm off-white page backgrounds
- White cards with thin warm-gray borders
- Muted teal as the primary interactive color
- Orange used only for status and small accents
- Large, friendly radii with very limited shadow depth
- One geometric sans-serif with bold headings and restrained body copy

The landing page should inherit this system through surfaces, controls, cards, and hierarchy. It should not reproduce the density of the mobile screens or import the map’s category colors into marketing sections.

## Observed Color System

### Core product colors

| Token | Observed value | Proposed canonical value | Use |
| --- | --- | --- | --- |
| `app-ink` | `#1A1A2C` to `#0C0C15` | `#1A1A2E` | Headings, icons, high-emphasis text |
| `app-teal` | `#489C8F` to `#53B5A8` | `#4A9D91` | Primary controls, selected states, icons |
| `app-orange` | `#CC7C2D` to `#D76636` | `#E95D24` | Pending states, alerts, small accents |

The three core colors should remain the only chromatic brand colors on the landing page.

For small white button text, use the accessible teal tone `#397C72` (`4.88:1` contrast). This is a darker tonal variant of `app-teal`, not an additional brand color. The observed `#4A9D91` remains appropriate for large icons, selected backgrounds, and non-text UI.

### Surface and text neutrals

| Token | Observed value | Proposed value | Use |
| --- | --- | --- | --- |
| `surface-page` | `#F7F5F0` to `#F9F8F5` | `#F8F5F0` | Main warm page background |
| `surface-card` | `#FFFFFF` | `#FFFFFE` | Cards, controls, navigation surfaces |
| `surface-teal-soft` | approximately `#E4F2EF` | `#E4F2EF` | Selected tags, approved states |
| `surface-orange-soft` | approximately `#F8EBDD` | `#FEEBE6` | Pending tags, orange accents |
| `text-secondary` | `#605F5F` to `#787C81` | `#666762` | Body text and metadata |
| `text-muted` | `#9F9F9F` | `#8B8D88` | Placeholder and low-emphasis text |
| `border-subtle` | approximately `#E5E2DC` | `#E5E2DC` | Card and control outlines |

### Color application

- Use `app-ink` for primary headings. This is a key app characteristic.
- Use `app-teal` for the primary CTA, active navigation, icons, and selected controls.
- Use `app-orange` for no more than 10% of a section’s colored elements.
- Use warm surfaces instead of pure cool gray.
- Do not use category-map colors as general landing-page decoration.
- Avoid gradients. The app relies on flat fills and surface contrast.

## Border Radius

The source screenshots are 1290px wide, equivalent to approximately 430 logical points at 3x density.

| Component type | Observed logical radius | Proposed web token |
| --- | --- | --- |
| Small icon button | `14–16px` | `radius-control: 16px` |
| Filter chip / status pill | Fully rounded | `radius-pill: 999px` |
| Search field / segmented control | `22–26px` | `radius-field: 24px` |
| Standard event or metric card | `16–20px` | `radius-card: 20px` |
| Large preview / bottom sheet | `28–34px` | `radius-panel: 32px` |
| Bottom navigation surface | `26–30px` | `radius-navigation: 28px` |

### Radius rules

- Controls should feel more rounded than the current wireframe’s `6–8px`.
- Use four radius levels only: `16px`, `20px`, `24px`, and `32px`, plus pills.
- Parent containers must have a larger radius than nested controls.
- Avoid mixing square cards with highly rounded buttons in the same component.
- Do not round full-page sections; reserve radii for contained surfaces.

## Border and Shadow Depth

The app uses borders more often than shadows. Depth is shallow and functional.

### Observed hierarchy

1. **Flat controls:** white fill plus a thin warm-gray border
2. **Cards:** white fill, thin border, minimal ambient shadow
3. **Floating surfaces:** search bar, preview sheet, and bottom navigation use a slightly stronger shadow

### Proposed shadow tokens

```css
--border-subtle: 1px solid #e5e2dc;

--shadow-card:
  0 2px 8px rgba(26, 26, 46, 0.04);

--shadow-control:
  0 4px 14px rgba(26, 26, 46, 0.06);

--shadow-floating:
  0 12px 32px rgba(26, 26, 46, 0.10);
```

### Shadow rules

- Default cards use `shadow-card`, not `shadow-floating`.
- Buttons should not have a permanent shadow.
- Use `shadow-control` for search fields and raised navigation controls.
- Reserve `shadow-floating` for one hero product panel or a genuinely floating surface.
- Never stack multiple strong shadows in one viewport.
- Borders must remain visible when shadows are removed or unavailable.

## Typography Audit

The app appears to use one geometric sans-serif family, visually closest to SF Pro or a similar rounded grotesk. For the website, use the system UI stack first; it aligns closely with the iOS screenshots and avoids a font download.

### Observed mobile scale

| Role | Approximate app size | Weight | Characteristics |
| --- | --- | --- | --- |
| Screen title | `28–32px` | 700 | Tight tracking, near-black |
| Section title | `20–22px` | 700 | Strong grouping label |
| Card title | `18–20px` | 700 | One or two lines maximum |
| Control label | `15–17px` | 600–700 | Bold, direct |
| Body / metadata | `14–16px` | 400–500 | Medium gray |
| Chip / status | `13–15px` | 600–700 | Compact and legible |
| Micro label | `11–12px` | 700 | Uppercase where appropriate |

### Proposed landing-page scale

The website needs larger display sizes while preserving the app’s ratios and weight contrast.

| Token | Desktop | Mobile | Weight | Use |
| --- | --- | --- | --- | --- |
| `type-display` | `64px / 68px` | `48px / 52px` | 700 | Hero headline |
| `type-h2` | `44px / 48px` | `36px / 40px` | 700 | Major sections |
| `type-h3` | `24px / 30px` | `22px / 28px` | 700 | Cards and flow steps |
| `type-body-lg` | `18px / 29px` | `17px / 27px` | 400 | Hero and section introductions |
| `type-body` | `16px / 26px` | `16px / 26px` | 400 | Standard copy |
| `type-label` | `13px / 18px` | `13px / 18px` | 700 | Buttons, chips, metadata |
| `type-eyebrow` | `12px / 16px` | `12px / 16px` | 700 | Uppercase section label |

### Typography rules

- Use one family only.
- Use weight 700 for headings and key controls.
- Use color and spacing, not extra font families, to create hierarchy.
- Keep display letter spacing between `-0.03em` and `-0.04em`.
- Keep body tracking at `0`.
- Headings should use `app-ink`; teal headings are not characteristic of the screenshots.
- Metadata should remain secondary and never compete with card titles.

## Spacing and Density

The app is dense but orderly. The website should adopt the rhythm, not the mobile density.

### Proposed spacing scale

```css
--space-1: 8px;
--space-2: 16px;
--space-3: 24px;
--space-4: 32px;
--space-6: 48px;
--space-8: 64px;
--space-12: 96px;
```

### Application

- `8px`: icon-to-label and chip internals
- `16px`: related text and compact controls
- `24px`: card padding and component groups
- `32px`: larger card padding and heading-to-body spacing
- `48px`: separation within a section
- `64px`: mobile section boundaries
- `96px`: desktop section boundaries

The screenshots consistently show generous outer gutters with compact internal group spacing.

## Landing-Page Component Mapping

### Header

- White or warm-white surface
- `app-ink` navigation text
- Teal primary CTA
- `16px` control radius
- Thin bottom border; no heavy shadow

### Hero

- Warm page background
- `app-ink` headline
- One white product-preview card with `32px` radius
- Teal CTA
- At most one `shadow-floating` surface
- Orange limited to one small status cue

### Core User Flow

- Replace hard grayscale dividers with white cards on warm background
- Cards use `20px` radius, subtle border, and `shadow-card`
- Step numbers sit in soft-teal pills or icon containers
- Preserve the current three-step content hierarchy

### Proof / Requirements

- Use `app-ink` as the dark section background
- White primary text and muted warm-gray secondary text
- Teal check or status icons
- Avoid orange unless a warning or pending concept is present

### Final CTA

- White card or warm surface rather than a decorative full-bleed gradient
- `32px` panel radius
- Teal primary button
- Large `app-ink` headline
- One clear action

## Proposed CSS Token Set

```css
:root {
  --color-ink: #1a1a2e;
  --color-teal: #4a9d91;
  --color-teal-action: #397c72;
  --color-orange: #e95d24;

  --color-page: #f8f5f0;
  --color-surface: #fffffe;
  --color-teal-soft: #e4f2ef;
  --color-orange-soft: #feebe6;
  --color-text-secondary: #666762;
  --color-text-muted: #8b8d88;
  --color-border: #e5e2dc;

  --radius-control: 16px;
  --radius-card: 20px;
  --radius-field: 24px;
  --radius-panel: 32px;
  --radius-pill: 999px;

  --shadow-card: 0 2px 8px rgba(26, 26, 46, 0.04);
  --shadow-control: 0 4px 14px rgba(26, 26, 46, 0.06);
  --shadow-floating: 0 12px 32px rgba(26, 26, 46, 0.10);

  --font-family: Inter, ui-sans-serif, -apple-system, BlinkMacSystemFont,
    "Segoe UI", sans-serif;

  --type-display: 700 64px/68px var(--font-family);
  --type-h2: 700 44px/48px var(--font-family);
  --type-h3: 700 24px/30px var(--font-family);
  --type-body-lg: 400 18px/29px var(--font-family);
  --type-body: 400 16px/26px var(--font-family);
  --type-label: 700 13px/18px var(--font-family);
}
```

## Key Differences From the Current Wireframe

| Current wireframe | App-derived direction |
| --- | --- |
| Pure white and cool grayscale | Warm off-white and white layered surfaces |
| `6–8px` control radii | `16–24px` control radii |
| Flat divided sections | Contained cards with subtle borders |
| Black CTA | Muted teal CTA |
| System-gray headings | Near-black navy headings |
| No shadows | Very shallow functional shadows |
| Abstract map wireframe only | One controlled real-product preview when imagery is approved |

## Recommendation

Apply the style guide in this order:

1. Color and typography tokens
2. Radius and border system
3. Card surfaces
4. Button and interaction states
5. One optimized product screenshot
6. Shadows last

This sequence preserves the approved hierarchy and user flow while making the landing page feel like the same product as the app.
