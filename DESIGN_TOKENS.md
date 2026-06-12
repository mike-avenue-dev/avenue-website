# Avenue Design Tokens

Status: Proposed v1  
Scope: Avenue marketing website  
Principle: Tokens support hierarchy and usability. They should not be used only for decoration.

## Color

The brand palette is limited to three colors. Neutral colors are supporting UI values and do not count as additional brand colors.

### Brand palette

| Token | Value | Role | Usage |
| --- | --- | --- | --- |
| `color-brand-primary` | `#105257` | Dark teal | Primary buttons, headings, navigation, dark sections |
| `color-brand-secondary` | `#1AB3AD` | Teal | Active states, icons, highlights, focus indicators |
| `color-brand-accent` | `#E95D24` | Orange | Small attention cues and selected accents |

### Brand color rules

- Dark teal is the default brand color and may carry white text.
- Teal is an accent. Do not use it for body text on white.
- Orange is reserved for small moments of emphasis. It must not compete with the primary CTA.
- Use no more than two brand colors within one component.
- The primary CTA always uses dark teal, not orange.
- Do not introduce gradients in the first visual design pass.

### Neutral palette

| Token | Value | Role |
| --- | --- | --- |
| `color-text-primary` | `#17172B` | Headings and high-emphasis text |
| `color-text-secondary` | `#62645F` | Body copy |
| `color-text-muted` | `#8B8D88` | Metadata and helper text |
| `color-border` | `#E5E5DF` | Dividers, borders, input outlines |
| `color-surface-subtle` | `#F7F5F1` | Alternate section background |
| `color-surface` | `#FFFFFE` | Main page and card background |

### Accessibility

- Dark teal on white: `8.87:1`, suitable for text.
- Primary text on white: `17.58:1`, suitable for text.
- Secondary text on white: `5.98:1`, suitable for normal body text.
- Teal on white: `2.59:1`; use for large icons, fills, and decoration only.
- Orange on white: `3.47:1`; use for large or non-text accents only.
- Never place normal white text on teal or orange without a separate contrast check.

## Typography

Use one type family throughout the website.

**Font family:** `DM Sans, Arial, sans-serif`

| Style | Desktop | Mobile | Weight | Letter spacing | Use |
| --- | --- | --- | --- | --- | --- |
| H1 | `64px / 64px` | `48px / 48px` | 700 | `-0.04em` | One page title only |
| H2 | `48px / 52px` | `40px / 44px` | 700 | `-0.035em` | Major section headings |
| H3 | `24px / 30px` | `22px / 28px` | 600 | `-0.015em` | Cards and step titles |
| Body | `16px / 26px` | `16px / 26px` | 400 | `0` | Paragraphs and descriptions |

### Typography rules

- Each page has one H1.
- Use H2 for top-level page sections and H3 within those sections.
- Do not skip heading levels for visual effect.
- Keep body text between 45 and 70 characters per line.
- Body text must remain at least `16px`.
- Use bold body text sparingly; hierarchy should come from heading level and spacing.
- Uppercase labels may use `12px / 16px`, weight 700, with `0.12em` letter spacing.
- Buttons use `14px / 20px`, weight 700.

## Spacing

All layout spacing uses an 8px base unit.

| Token | Value | Typical usage |
| --- | --- | --- |
| `space-1` | `8px` | Icon gaps, compact inline spacing |
| `space-2` | `16px` | Related text, control padding |
| `space-3` | `24px` | Card padding, mobile page gutter |
| `space-4` | `32px` | Component groups |
| `space-6` | `48px` | Large component separation |
| `space-8` | `64px` | Section content separation |
| `space-12` | `96px` | Standard desktop section padding |
| `space-16` | `128px` | Large editorial section padding |

### Spacing rules

- Start with `16px` between tightly related elements.
- Use `24px` or `32px` between groups inside a component.
- Use at least `64px` between distinct page sections.
- Standard desktop section padding is `96px`; mobile section padding is `64px`.
- Desktop page gutters are `24px`; mobile gutters are `16px`.
- Avoid arbitrary values such as `18px`, `27px`, or `70px`.
- A `4px` half-step is allowed only for optical alignment, borders, or very small icon adjustments.
- Spacing communicates hierarchy: larger conceptual changes require larger spacing.

## Grid

| Property | Desktop | Tablet | Mobile |
| --- | --- | --- | --- |
| Max content width | `1120px` | Fluid | Fluid |
| Columns | 12 | 8 | 4 |
| Page gutter | `24px` | `24px` | `16px` |
| Column gap | `24px` | `24px` | `16px` |

### Grid rules

- Align section headings, body copy, cards, and CTAs to the same column lines.
- Prefer balanced `6/6` or content-led `5/7` desktop splits.
- Collapse multi-column content to one column on mobile.
- Do not position screenshots or cards outside the grid.
- Overlap is not part of the base system and requires explicit design approval.

## Component Foundations

| Token | Value | Usage |
| --- | --- | --- |
| `radius-control` | `8px` | Buttons, inputs, compact controls |
| `radius-card` | `16px` | Cards and content panels |
| `border-default` | `1px solid #E5E5DF` | Cards, dividers, form controls |
| `control-height` | `48px` | Standard buttons and inputs |
| `control-height-large` | `56px` | Primary hero CTA |

Shadows are excluded from the first visual pass. Hierarchy should work through spacing, border, scale, and contrast before elevation is added.

## Interaction States

Interactive states must remain clear in grayscale. Never communicate interaction using color alone.

### Primary button

| State | Background | Border | Position | Purpose |
| --- | --- | --- | --- | --- |
| Default | `#171717` | `#171717` | Resting | Available action |
| Hover | `#2D2D2D` | `#2D2D2D` | Move up `2px` | Pointer is over the action |
| Active | `#000000` | `#000000` | Move down `1px`, scale to `98%` | Action is being pressed |
| Focus visible | Default state | `3px #171717` outer outline, `4px` offset | Resting | Keyboard focus |

Button transitions use `160ms ease` for color and `80ms ease` for press movement. Motion is removed when the user enables reduced motion.

### Text links

| State | Text | Underline | Weight | Purpose |
| --- | --- | --- | --- | --- |
| Default | Secondary text | Hidden | Existing weight | Available navigation |
| Hover | Primary text | `1px`, offset `4px` | Existing weight | Pointer is over the link |
| Active | Primary text | `2px`, offset `4px` | 700 | Link is being pressed |
| Focus visible | Existing state | Existing underline | Existing weight | `3px` outer outline, `4px` offset |

### Interaction rules

- Hover is an enhancement, not the only interaction signal.
- Every interactive element must have a visible `:focus-visible` state.
- Active states should feel pressed and last only while the pointer or key is held.
- Do not change layout dimensions between states.
- Do not use hover effects on non-interactive content.
- Touch devices rely on active and focus feedback because hover may not occur.
- Controls must retain at least a `44px` touch target.
- Disabled states are not defined until the product has a real disabled action.

## CSS Reference

```css
:root {
  --color-brand-primary: #105257;
  --color-brand-secondary: #1ab3ad;
  --color-brand-accent: #e95d24;

  --color-text-primary: #17172b;
  --color-text-secondary: #62645f;
  --color-text-muted: #8b8d88;
  --color-border: #e5e5df;
  --color-surface-subtle: #f7f5f1;
  --color-surface: #fffffe;

  --font-family: "DM Sans", Arial, sans-serif;

  --font-h1: 700 64px/64px var(--font-family);
  --font-h2: 700 48px/52px var(--font-family);
  --font-h3: 600 24px/30px var(--font-family);
  --font-body: 400 16px/26px var(--font-family);

  --space-1: 8px;
  --space-2: 16px;
  --space-3: 24px;
  --space-4: 32px;
  --space-6: 48px;
  --space-8: 64px;
  --space-12: 96px;
  --space-16: 128px;

  --radius-control: 8px;
  --radius-card: 16px;
  --control-height: 48px;
  --control-height-large: 56px;

  --duration-interaction: 160ms;
  --duration-press: 80ms;
  --focus-width: 3px;
  --focus-offset: 4px;
}
```

These tokens should be approved before they are applied to the wireframe.
