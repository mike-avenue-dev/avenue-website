# Avenue Landing Page Communication Audit

Status: Approved direction for the MVP landing page
Scope: Purpose, information hierarchy, visual support, and CTA logic

## Strategic Decision

The website does not need to look or behave like an extension of the Avenue app.

Its MVP job is narrower:

1. Explain what Avenue is.
2. Explain why it is useful in Limassol.
3. Show what a visitor will be able to do with it.
4. Give interested visitors one obvious next action.

Visual similarity to the product is secondary. App screenshots, map treatments, interface cards, and product-specific interaction patterns should only appear when they make the purpose easier to understand.

## Primary Audience

The first landing page is written primarily for people in Limassol looking for something to do.

The page should answer these questions in order:

- What is Avenue?
- Is it relevant to me and my city?
- What problem does it solve?
- What will I be able to do with it?
- Is it available yet?
- What should I do next?

Venue owners, event organisers, and potential partners are valid future audiences, but they should not compete with the consumer message or primary CTA in the MVP.

## Core Message

### One-sentence proposition

**Avenue helps people discover events and venues across Limassol in one place.**

### Supporting promise

Visitors should understand that Avenue reduces the need to search across social media, venue pages, messages, and unrelated listings.

### Desired visitor takeaway

> When I want to make a plan in Limassol, Avenue will give me one clear place to start.

Every section should strengthen this takeaway. Content that does not improve understanding, trust, or conversion should be removed.

## CTA Strategy

### Primary conversion

The only primary conversion is:

**Join the launch list**

This exact label should be used in:

1. The header
2. The hero
3. The final CTA section

All three instances must lead to the same destination and set the same expectation.

### CTA expectation

The supporting copy should explain:

- Avenue is coming soon to iPhone.
- Joining means receiving a launch notification or a very small number of relevant launch updates.
- The visitor will not receive ongoing promotional spam.

Recommended microcopy:

**Coming soon to iPhone. Join for one launch update.**

### CTA hierarchy

- Use one filled primary button style throughout the page.
- Do not introduce another filled action such as “Learn more,” “View demo,” or “Explore events.”
- In-page navigation may use text links, but it must remain visually subordinate.
- Legal, support, and contact links belong in the footer and are not conversion actions.
- A future organiser or venue CTA should live on a separate page or clearly secondary route.

### CTA destination

A short email field and submit button is the preferred final implementation because it keeps the visitor on the page and makes the action explicit.

The current `mailto:` link is acceptable only as a temporary wireframe mechanism. Before launch, replace it with a real launch-list form or a clearly explained external signup destination. Do not imply that a visitor has joined until a submission has succeeded.

### CTA success state

After submission, show a concise confirmation:

**You’re on the list. We’ll let you know when Avenue launches.**

Do not redirect the visitor to an unrelated page.

## Information Architecture

### 1. Header

Purpose:

- Identify Avenue.
- Keep the primary action available.

Content:

- Avenue logo and wordmark
- “Join the launch list” button

Avoid a full navigation menu for the MVP. The page is short and has one conversion goal.

### 2. Hero

Purpose:

- Establish what Avenue does, where it works, and why it matters.

Recommended hierarchy:

- Eyebrow: `Event and venue discovery for Limassol`
- Headline: `Find a plan without searching everywhere.`
- Supporting copy: Avenue brings local events and venues into one clear place so people can decide where to go.
- Primary CTA
- Availability and privacy microcopy

The hero should be content-led. A visual may support the message, but it must not require visitors to interpret a product interface before understanding the proposition.

Suitable hero support:

- A simple editorial illustration of scattered sources becoming one clear destination
- A restrained Limassol/location motif
- A compact information panel summarising `Events`, `Venues`, and `One place to start`
- No visual at all if the copy is stronger without one

Avoid:

- A large app screenshot as the main message
- A fake interactive map
- Feature-heavy interface chrome
- Decorative visuals that compete with the CTA

### 3. Problem

Purpose:

- Confirm that Avenue addresses a familiar local frustration.

Message:

**Local plans are scattered across too many places.**

Keep this section short. It should create recognition, not over-explain the market.

### 4. What Avenue Helps You Do

Purpose:

- Turn the proposition into three concrete benefits.

Recommended benefits:

1. Discover local events and venues
2. Narrow the options using useful details
3. Save promising plans for later

Use benefit-led language. Interface terminology such as annotations, segmented controls, sheets, or tabs does not belong in the marketing copy.

### 5. How It Works

Purpose:

- Make the future experience easy to picture.

Sequence:

1. Open Avenue
2. Find options that fit
3. Choose where to go

This can be a compact numbered sequence. It does not need to reproduce app screens.

### 6. MVP Promise

Purpose:

- Establish trust by being specific about the first release.

The first version should promise:

- Useful events and venues in Limassol
- Clear location and timing information
- Understandable filters
- The ability to save plans

Do not advertise incomplete features such as Near Me, advanced date filtering, or organiser tools as available.

### 7. Final CTA

Purpose:

- Convert visitors who now understand the product.

Content:

- `Avenue is coming soon`
- `Be first to know when Avenue launches in Limassol.`
- One sentence setting the email expectation
- The same launch-list action used in the hero

The section should feel conclusive, not introduce new product information.

### 8. Footer

Include:

- Copyright
- Privacy
- Terms
- Support
- Contact where appropriate

Keep footer links visually separate from the primary CTA.

## Visual Direction

The visual system should support reading and decision-making rather than imitate the app.

### Principles

- High contrast
- Generous whitespace
- Clear section boundaries
- Strong typographic hierarchy
- Limited decoration
- One dominant action color
- Consistent button treatment

### Color

Use a restrained website palette:

- Near-black or deep navy for headings
- White and one subtle neutral for section backgrounds
- Dark teal for the primary CTA and important highlights
- Orange only as a small brand accent when it has a clear purpose

No section requires app category colors, map-marker colors, or status colors.

### Typography

Use a system UI font stack for speed and clarity. The display scale should be confident but not so large that it pushes the proposition or CTA below the fold.

| Role | Desktop | Mobile | Use |
| --- | --- | --- | --- |
| Display | `64px / 68px` | `44px / 48px` | Hero headline |
| H2 | `44px / 48px` | `34px / 39px` | Main section headings |
| H3 | `24px / 30px` | `22px / 28px` | Benefits and steps |
| Lead | `18px / 29px` | `17px / 27px` | Hero and section introductions |
| Body | `16px / 26px` | `16px / 26px` | Standard copy |
| Label | `13px / 18px` | `13px / 18px` | Buttons and compact metadata |

### Surfaces and depth

- Prefer flat sections and thin borders.
- Use cards only when they improve scanning or group related information.
- Use a maximum of one subtle shadow treatment.
- Do not make every section a rounded panel.
- Product-style floating controls are unnecessary.

### Imagery

Imagery is optional for the MVP.

If included, it must pass this test:

> Does this image help a first-time visitor understand Avenue faster?

One lightweight visual is preferable to a gallery of app screenshots. Product screenshots may appear below the core explanation later, but they are not required for launch.

## Content Rules

- Lead with visitor outcomes, not implementation details.
- Use “events and venues” consistently.
- Mention Limassol above the fold.
- Keep paragraphs to two or three sentences.
- Avoid unsupported claims such as “all events,” “the best events,” or “everything happening.”
- Do not describe features that are not part of the MVP.
- Use the same CTA wording everywhere.
- Place reassurance immediately beside the CTA, not in a distant FAQ.

## MVP Release Test

The landing page is ready when a first-time visitor can answer the following after ten seconds:

1. Avenue helps me find events and venues.
2. It is focused on Limassol.
3. It is not available yet.
4. I can join the launch list.
5. Joining has a clear and limited email expectation.

If the visual design is memorable but any of these points are unclear, the page has failed its primary purpose.
