# Avenue Responsive Breakdown

Status: Information-first MVP specification
Reference widths: `1400px` desktop and `375px` mobile

## Responsive Objective

The responsive layout must preserve the same decision sequence at every width:

1. Understand Avenue
2. Understand its relevance to Limassol
3. Understand the benefits
4. Join the launch list

Mobile is not a reduced product presentation. It is the clearest, most linear version of the marketing story.

## Breakpoints

| Range | Layout behavior |
| --- | --- |
| `801px` and wider | Desktop grid with a maximum content width of `1120px` |
| `521px` to `800px` | Single-column story with tablet gutters and desktop body sizing |
| `520px` and narrower | Mobile type scale, `16px` gutters, reduced section spacing, full-width conversion controls |

Breakpoints are driven by content pressure rather than device names.

## 1. Header

### At 1400px

- The logo sits on the left.
- The primary CTA sits on the right.
- The header does not need a full navigation menu.
- The CTA uses the same label and styling as the hero action.

### At 375px

- Logo and CTA remain on one row where the label fits.
- The header CTA may use the standard `48px` control height.
- Do not replace the CTA with a menu icon.
- Legal and support links remain in the footer.

## 2. Hero

### At 1400px

- Content sits within a centered `1120px` container.
- The preferred layout is a content-led `7/5` split.
- The proposition, explanation, CTA, and reassurance occupy the larger column.
- The smaller column may contain a simple purpose-supporting panel.
- A single-column layout is acceptable if no useful supporting visual is approved.
- The visitor should understand Avenue and see the CTA without scrolling on a typical laptop viewport.

### At 375px

- The layout becomes one column.
- The available content width is approximately `343px` with `16px` gutters.
- The eyebrow, headline, explanation, CTA, and reassurance appear first.
- The headline uses `44px / 48px` and should remain approximately four lines or fewer.
- The primary CTA or launch-list form spans the full content width.
- Any supporting visual follows the complete CTA group and may be removed if it adds more scrolling than understanding.

### Experience change

Desktop may use a supporting panel to aid scanning. Mobile presents the proposition and action as one uninterrupted decision block.

## 3. Problem And Purpose

### At 1400px

- Use a two-column layout with the problem statement on the left and concise explanation on the right.
- Keep the section compact enough to read in one viewport band.

### At 375px

- Stack the heading before the explanation.
- Preserve at least `24px` between the two text groups.
- Avoid decorative elements between the problem and its explanation.

## 4. Benefits

### At 1400px

- Present three equal-width benefits in one row.
- Each benefit uses a short title and no more than two or three lines of supporting copy.
- Cards are optional; columns with dividers are acceptable if they scan more clearly.

### At 375px

- Stack the benefits vertically.
- Remove fixed heights.
- Keep titles, descriptions, and optional icons aligned consistently.
- Use dividers or spacing so each benefit remains a distinct reading unit.

### Experience change

Desktop supports comparison. Mobile turns the benefits into a short explanatory sequence.

## 5. How It Works

### At 1400px

- The three steps may appear horizontally.
- Step numbers and titles align to a consistent baseline.
- Keep the section visually quieter than the benefits; it confirms simplicity rather than introducing another major sales argument.

### At 375px

- Steps stack vertically in their natural order.
- Each step should fit comfortably within a short scroll segment.
- Do not use screenshots between steps.

## 6. MVP Promise

### At 1400px

- Use a strong section heading and a compact list of first-release commitments.
- A two-column layout is appropriate when it shortens scanning distance.

### At 375px

- Place the promise heading above the list.
- List items use clear text and optional simple check icons.
- Do not hide or collapse commitments behind accordions.

## 7. Final CTA

### At 1400px

- Center the content within the `1120px` container.
- Keep the heading below `720px` wide.
- Repeat the exact hero CTA label and expectation.
- The form or button remains compact and centered.

### At 375px

- Use reduced vertical padding.
- The heading uses the mobile H2 scale rather than a second H1-sized display treatment.
- The email field and submit button stack vertically and span the content width.
- The reassurance remains immediately below the action.

### Experience change

Desktop creates a focused pause before conversion. Mobile maximizes clarity and touchability without changing the offer.

## Responsive CTA Rules

- Use `Join the launch list` everywhere.
- Every CTA instance leads to the same signup destination.
- The reassurance copy stays attached to each major CTA group.
- Do not introduce a floating, sticky, or bottom-sheet CTA in the MVP.
- Do not show a different CTA based on viewport size.
- Validation and success messages must not cause horizontal overflow or major layout shift.

## General Responsive Rules

- Content order never changes between widths.
- Mobile layouts do not hide essential information.
- No horizontal scrolling is allowed.
- Touch targets remain at least `44px` high.
- Body text remains at least `16px`.
- Supporting visuals stay inside the grid and never overlap copy.
- Optional imagery may be removed on mobile when it does not carry essential meaning.
- Hover is a desktop enhancement; active and focus states provide feedback everywhere.
