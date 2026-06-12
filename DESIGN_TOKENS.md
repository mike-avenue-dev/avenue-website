# Avenue Website Design Tokens

Status: Proposed MVP direction
Scope: Information-first marketing website
Principle: Every token must improve comprehension, hierarchy, accessibility, or CTA clarity.

## Color

The website uses one primary action color and a quiet neutral foundation. It does not need to reproduce the app’s full interface palette.

### Brand and action palette

| Token | Value | Role |
| --- | --- | --- |
| `color-action` | `#105257` | Primary CTA, high-emphasis links, focus treatment |
| `color-action-hover` | `#0C4347` | Primary CTA hover |
| `color-accent` | `#E95D24` | Small brand accent only |
| `color-heading` | `#17172B` | Headings and high-emphasis text |

### Neutral palette

| Token | Value | Role |
| --- | --- | --- |
| `color-text` | `#62645F` | Body copy |
| `color-muted` | `#7D807A` | Helper text and metadata |
| `color-border` | `#E5E5DF` | Dividers, borders, and form outlines |
| `color-surface-subtle` | `#F7F5F1` | Alternate informational sections |
| `color-surface` | `#FFFFFE` | Main page and card background |
| `color-inverse` | `#FFFFFF` | Text on dark surfaces |

### Color rules

- The primary CTA always uses `color-action`.
- Do not create multiple filled button colors.
- Headings use `color-heading`; body text uses `color-text`.
- Orange must not be used for the primary action.
- Use alternate section backgrounds to aid scanning, not as decoration.
- Do not import category, status, or map-marker colors from the app.
- Do not use gradients in the MVP.
- Interaction and meaning must remain understandable without color.

### Accessibility

- Dark teal on white has sufficient contrast for normal text.
- Heading and body colors must meet WCAG AA against their surfaces.
- White text may only appear on a background that passes a contrast check.
- Focus indicators must remain visible against both white and subtle neutral surfaces.

## Typography

Use the operating system UI stack to avoid a font request and keep the page fast.

```css
--font-family: ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI",
  sans-serif;
```

| Style | Desktop | Mobile | Weight | Letter spacing | Use |
| --- | --- | --- | --- | --- | --- |
| H1 | `64px / 68px` | `44px / 48px` | 700 | `-0.035em` | One clear proposition |
| H2 | `44px / 48px` | `34px / 39px` | 700 | `-0.03em` | Major sections |
| H3 | `24px / 30px` | `22px / 28px` | 700 | `-0.015em` | Benefits and steps |
| Lead | `18px / 29px` | `17px / 27px` | 400 | `0` | Introductory copy |
| Body | `16px / 26px` | `16px / 26px` | 400 | `0` | Paragraphs |
| Label | `13px / 18px` | `13px / 18px` | 700 | `0.08em` | Eyebrows and buttons |

### Typography rules

- Each page has one H1.
- Keep the complete hero proposition and CTA visible without excessive scrolling.
- Body text remains at least `16px`.
- Keep body copy between 45 and 70 characters per line.
- Use sentence case for headings and buttons.
- Use uppercase only for short eyebrow labels.
- Avoid oversized display text that turns a short message into many lines.
- Use weight and spacing before introducing additional colors.

## Spacing

All layout spacing uses an 8px base unit.

| Token | Value | Typical usage |
| --- | --- | --- |
| `space-1` | `8px` | Icon and inline gaps |
| `space-2` | `16px` | Related text and control padding |
| `space-3` | `24px` | Card padding and content groups |
| `space-4` | `32px` | Heading-to-copy and component groups |
| `space-6` | `48px` | Section internals |
| `space-8` | `64px` | Mobile section boundaries |
| `space-12` | `96px` | Standard desktop sections |
| `space-16` | `128px` | Reserved for a deliberate final CTA pause |

### Spacing rules

- Conceptually related information stays close together.
- CTA reassurance sits within `8px` to `16px` of the action.
- Use at least `64px` between distinct sections.
- Desktop page gutters are `24px`; mobile gutters are `16px`.
- Avoid arbitrary spacing values.
- Do not use whitespace to compensate for weak content hierarchy.

## Grid

| Property | Desktop | Tablet | Mobile |
| --- | --- | --- | --- |
| Max content width | `1120px` | Fluid | Fluid |
| Columns | 12 | 8 | 4 |
| Page gutter | `24px` | `24px` | `16px` |
| Column gap | `24px` | `24px` | `16px` |

### Grid rules

- Align headings, body copy, and CTAs to shared column lines.
- Use a content-led `7/5` hero split when a supporting panel is present.
- A single-column hero is valid when it makes the message clearer.
- Collapse multi-column content to one column on mobile.
- Keep supporting visuals inside the grid.
- Do not overlap content or place decoration outside the grid.

## Component Foundations

| Token | Value | Usage |
| --- | --- | --- |
| `radius-control` | `10px` | Buttons and form fields |
| `radius-card` | `16px` | Informational cards |
| `border-default` | `1px solid #E5E5DF` | Cards, dividers, and form controls |
| `control-height` | `48px` | Header CTA and standard controls |
| `control-height-large` | `56px` | Hero and final CTA |
| `shadow-subtle` | `0 4px 16px rgba(23, 23, 43, 0.06)` | Optional emphasis for one key surface |

### Component rules

- Cards are informational containers, not default wrappers for every section.
- Use one radius for all primary buttons.
- Header, hero, and final CTA buttons must look and read the same.
- Shadows are optional and limited to one level.
- Controls must have at least a `44px` touch target.

## CTA Components

### Primary button

| State | Background | Text | Movement |
| --- | --- | --- | --- |
| Default | `#105257` | White | None |
| Hover | `#0C4347` | White | Up `1px` |
| Active | `#08373A` | White | Down `1px` |
| Focus visible | Default | White | `3px` outline with `3px` offset |

Button transitions use `160ms ease`. Movement is removed when reduced motion is enabled.

### Launch-list form

- Email field and submit button use the same `56px` height in hero and final CTA contexts.
- The field must have a persistent visible label, even if placeholder text is also used.
- Validation appears next to the field and does not rely on color alone.
- The success state replaces the form with a clear confirmation.
- Do not add unrelated fields to the MVP form.

### Secondary links

- Text links remain visually subordinate to the filled CTA.
- In-page links may use an underline on hover and focus.
- Footer links never adopt primary button styling.

## Interaction Rules

- Hover is an enhancement, not the only interaction signal.
- Every interactive element has a visible `:focus-visible` state.
- Active states must not alter layout dimensions.
- Do not animate non-interactive content.
- Respect `prefers-reduced-motion`.
- Do not add carousels, auto-rotating content, or scroll-dependent CTA behavior.

## CSS Reference

```css
:root {
  --color-action: #105257;
  --color-action-hover: #0c4347;
  --color-accent: #e95d24;
  --color-heading: #17172b;
  --color-text: #62645f;
  --color-muted: #7d807a;
  --color-border: #e5e5df;
  --color-surface-subtle: #f7f5f1;
  --color-surface: #fffffe;
  --color-inverse: #ffffff;

  --font-family: ui-sans-serif, -apple-system, BlinkMacSystemFont, "Segoe UI",
    sans-serif;

  --font-h1: 700 64px/68px var(--font-family);
  --font-h2: 700 44px/48px var(--font-family);
  --font-h3: 700 24px/30px var(--font-family);
  --font-lead: 400 18px/29px var(--font-family);
  --font-body: 400 16px/26px var(--font-family);
  --font-label: 700 13px/18px var(--font-family);

  --space-1: 8px;
  --space-2: 16px;
  --space-3: 24px;
  --space-4: 32px;
  --space-6: 48px;
  --space-8: 64px;
  --space-12: 96px;
  --space-16: 128px;

  --radius-control: 10px;
  --radius-card: 16px;
  --control-height: 48px;
  --control-height-large: 56px;
  --shadow-subtle: 0 4px 16px rgba(23, 23, 43, 0.06);

  --duration-interaction: 160ms;
  --focus-width: 3px;
  --focus-offset: 3px;
}
```

These tokens intentionally describe a clear marketing website rather than a web reproduction of the Avenue app.
