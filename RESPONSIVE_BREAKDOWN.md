# Avenue Responsive Breakdown

Status: Wireframe specification  
Reference widths: `1400px` desktop and `375px` mobile

## Breakpoints

| Range | Layout behavior |
| --- | --- |
| `801px` and wider | Desktop grid with a maximum content width of `1120px` |
| `521px` to `800px` | Single-column content; desktop type and gutters are retained where they still fit |
| `520px` and narrower | Mobile type scale, `16px` page gutters, reduced section spacing, full-width primary CTA where needed |

Breakpoints are driven by content pressure, not device names.

## 1. Hero

### At 1400px

- The content sits within a centered `1120px` container.
- Copy and product wireframe use two `515px` columns with a `90px` gap.
- The headline and CTA appear on the left.
- The product explanation remains visible beside the value proposition.
- The user can understand the offer and inspect the product model without scrolling.
- The primary CTA uses its intrinsic width.

### At 375px

- The layout becomes one column at `800px`.
- The available content column is `328px`.
- Copy appears before the product wireframe to preserve the decision sequence.
- The headline drops to `48px / 48px`.
- Page gutters reduce from `24px` to `16px`.
- The primary CTA remains prominent but does not automatically fill the screen.
- The product wireframe follows as supporting evidence, not competing content.

### Experience change

Desktop supports simultaneous scanning. Mobile enforces a linear story: proposition, explanation, CTA, then product evidence.

## 2. Core User Flow

### At 1400px

- The three steps appear in one horizontal row.
- Each step occupies approximately `373px`.
- Equal-width columns make the sequence easy to compare.
- Vertical dividers separate steps without introducing card styling.
- Step numbers, titles, and descriptions align consistently.

### At 375px

- Steps stack vertically at `800px`.
- Each step occupies the full `328px` content width.
- Vertical dividers become horizontal dividers.
- Fixed minimum heights are removed.
- Internal spacing reduces to `28px 20px`.
- Each step becomes a short reading block that fits naturally into vertical scrolling.

### Experience change

Desktop communicates the complete process at a glance. Mobile turns the process into a clear numbered sequence with one decision per viewport area.

## 3. Final CTA

### At 1400px

- Content is centered within the `1120px` container.
- The heading has a maximum width of `820px`.
- Generous vertical spacing isolates the final decision from the preceding content.
- The button remains content-width so the section does not feel like a form.
- The measured button width is approximately `175px`.

### At 375px

- Section padding reduces from `130px` to `95px`.
- The heading uses the `48px` mobile H1 scale.
- Supporting copy remains centered and readable.
- The primary button becomes full width for a larger, clearer touch target.
- The measured button width is `328px`, matching the content column.

### Experience change

Desktop creates a focused pause before conversion. Mobile prioritizes reachability and removes ambiguity by making the sole action span the available content width.

## Responsive Rules

- Content order never changes between widths.
- The primary CTA label stays identical across the page.
- Mobile layouts do not hide essential information.
- No horizontal scrolling is allowed.
- Touch targets remain at least `44px` high.
- Text remains at least `16px` for body content.
- Screenshots and future imagery must stay inside the grid rather than overlap adjacent sections.
- Hover remains a desktop enhancement; active and focus states provide feedback on mobile and keyboard navigation.
