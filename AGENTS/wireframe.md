# NovaCast Studio — Single-Page Wireframe

**Reference implementation:** `index.html`  
**Page language:** English  
**Primary audience:** US DTC/Shopify brands, GCC advertisers, and paid media buyers  
**Conversion:** WhatsApp only; no forms or alternate contact route.

## Global behavior and design

- Premium, minimalist, performance-driven visual system; retain the current page’s brand, typography, spacing, and responsive styling when implementing this spec.
- Mobile-first layout. Keep content within the viewport; use horizontal scrolling only inside the Creative Showcase carousel.
- All conversion buttons use the same WhatsApp Business destination pattern and a prefilled paid-pilot message:

  ```text
  https://wa.me/YOUR_PHONE_NUMBER?text=Hi%20NovaCast,%20I'm%20interested%20in%20a%20paid%20UGC%20test%20pack%20for%20my%20brand.&utm_source=website&utm_medium=whatsapp&utm_campaign=paid_pilot
  ```

- Replace `YOUR_PHONE_NUMBER` before launch. Track WhatsApp link clicks as `whatsapp_click`; optional CTA location labels can identify placement.
- Non-conversion section links may be used for navigation or “View Samples”; do not add input forms or another destination CTA.

## 1. Sticky top navigation

**Desktop:** logo and “NovaCast Studio” at left; section links `Workflow`, `Samples`, `Packages`, `FAQ`; one prominent **Chat on WhatsApp** button at right.

**Mobile:** keep the 1:1 logo fully inside its frame with the brand name beside it. Use a compact menu for section anchors and a visible **Chat on WhatsApp** button. If the page also uses a fixed mobile CTA, avoid obscuring content or duplicating the nav label in a crowded header.

**Behavior:** sticky at top with a solid/blurred background and visible keyboard focus. The WhatsApp button opens the prefilled link in a new tab with safe `rel` attributes.

## 2. Hero

**Eyebrow:** `PERFORMANCE-DRIVEN CREATIVE`

**Headline:** `AI UGC for DTC Brands`

**Subhead:** `Hook-first AI UGC video ads built for paid media testing. Create new angles for TikTok, Reels, and paid social with a clear, reviewable workflow.`

**Timing note:** `First delivery in 48–72 hours, depending on brief approval and asset readiness.`

**Primary action:** one **Chat on WhatsApp** button.

**Optional secondary action:** `View Samples` scroll link to `#showcase`. It must not collect user information or open a contact channel.

**Visual:** current NovaCast brand mark and a vertical creator/product preview. Do not imply that concept imagery is a real customer result or testimonial.

## 3. Traditional vs NovaCast workflow

**Section ID:** `#workflow`  
**Heading:** `A faster way to test new creative.`

Two-column comparison on desktop; stacked cards on mobile.

| Traditional creator production | NovaCast Studio workflow |
|---|---|
| Scheduling and shipping can extend production timelines. | Start with a product URL, approved assets, and a clear brief. |
| Coordination spans creators, product samples, and edits. | Approve hooks and angles before production. |
| New concepts may require another production cycle. | Scope variations for paid-media testing in a repeatable workflow. |

Avoid absolute comparisons, guaranteed savings, or claims of guaranteed performance.

## 4. Creative Showcase

**Section ID:** `#showcase`  
**Heading:** `Formats made for the feed.`  
**Intro:** `Concept examples for common product and app categories. Replace these media files with approved work before presenting them as portfolio pieces.`

### Layout and card specification

- Horizontal container: `overflow-x: auto; scroll-snap-type: x mandatory; -webkit-overflow-scrolling: touch; scrollbar-width: none;` with equivalent scrollbar hiding for WebKit browsers.
- Each card: `scroll-snap-align: start`, width 260–300px (responsive), vertical 9:16 media, rounded corners, concise title and niche/hook badges.
- Place accessible previous/next buttons above the carousel. Each click scrolls by approximately one card width plus gap. Touch swipe and trackpad/mouse horizontal scroll must work.
- Start with six replaceable cards: Beauty · Pain Point; Tech · Unboxing; App · Habit Hook; GCC Market · Khaleeji Arabic; Beauty · Routine Demo; Tech · Problem/Solution.
- Each card uses a poster image and this video behavior:

  ```html
  <video muted loop playsinline preload="none" poster="assets/poster.jpg" aria-label="Descriptive concept video title">
    <source src="assets/videos/example.mp4" type="video/mp4">
  </video>
  ```

- Show a clear play/pause control and descriptive accessible name. Keep category and hook badges readable over the media.

### Playback logic

- Observe each card relative to the carousel viewport with `IntersectionObserver`.
- Play a card video only while at least 60% of that card is visible; pause it when visibility falls below 60% or it exits the carousel.
- Enforce a single active video globally within the carousel: starting another video pauses the previous one.
- Handle rejected `play()` promises without leaving a false “playing” state. Provide a visibility calculation fallback where `IntersectionObserver` is unavailable.

## 5. How it works

**Section ID:** `#how-it-works`  
**Heading:** `From brief to creative test.`

1. **Brief** — Share product URL, market, audience, offer, brand assets, and claim restrictions through WhatsApp.
2. **Hooks & angles approval** — Review and approve scripts, messaging angles, and language before production.
3. **Production** — Create and edit the approved short-form video concepts; perform human QA for brand fit, claims, voice, and captions.
4. **Delivery** — Receive the agreed exports and provide feedback within the project’s revision scope.

## 6. Packages

**Section ID:** `#packages`  
**Heading:** `Choose the right creative cadence.`

Use three clean package cards. Growth may be visually emphasized. Every card’s only action is a WhatsApp link; customize its prefilled message with that package name while retaining the same `wa.me` destination.

### Starter Test Pack

- 3 short-form videos, typically 15–35 seconds
- Distinct hooks for a paid creative pilot
- Burn-in captions and clean-caption exports as scoped
- One text/hook revision before production; one style revision after delivery unless otherwise agreed
- First delivery in 48–72 hours depending on approved brief and required assets
- CTA: **Chat on WhatsApp**

### Growth Creative Pack

- 8–12 videos per month
- Agreed hook/angle matrix
- Weekly delivery batches
- Caption versions and review scope confirmed before kickoff
- CTA: **Chat on WhatsApp**

### Ad Machine Retainer

- 20–30 videos per month
- Ongoing planning with the media buyer and a creative backlog
- SLA, approvals, and revision scope agreed before kickoff
- CTA: **Chat on WhatsApp**

Keep pricing quote-based unless approved prices are supplied. State that commercial usage terms are agreed per project.

## 7. FAQ accordion

Use semantic buttons with `aria-expanded` and `aria-controls`. Keep answer text in the DOM while collapsed. Suggested questions:

1. **Will the videos look AI-generated?** Explain that realism varies and that examples, limitations, and human QA can be reviewed before production.
2. **What do you need from me?** Product URL, market, audience, brand assets/guidance, offer, and claims to avoid.
3. **Who can use the finished videos?** Usage rights and restrictions are defined in project terms; the client must have rights to supplied assets.
4. **How long does delivery take?** First delivery is 48–72 hours depending on approved brief and asset readiness; confirm the project schedule.
5. **Can I request revisions?** State the standard one pre-production text/hook revision and one post-delivery style revision unless otherwise agreed.

## 8. Final CTA banner

**Heading:** `Ready to build your next test?`  
**Copy:** `Share your product, audience, and target market directly with NovaCast Studio. We’ll scope a paid Starter Test Pack or a monthly creative program.`  
**Single button:** **Chat on WhatsApp**

No fields, form submission, email address, or alternate contact option.

## 9. Footer

- Show the NovaCast Studio logo/wordmark and a concise service description.
- Include a minimal legal/commercial note: `Usage rights, asset permissions, platform requirements, and delivery scope are confirmed per project. Platform acceptance and ad performance are not guaranteed.`
- Keep footer navigation limited to in-page anchors and approved legal pages. Do not add contact methods beyond WhatsApp.

## Responsive and accessibility checks

- At narrow widths, stack sections and package cards; preserve readable spacing and button hit areas.
- Prevent horizontal overflow outside the carousel. Carousel must remain swipeable and its controls keyboard operable.
- Use semantic landmarks, ordered heading levels, visible focus, descriptive image/video names, and sufficient text contrast.
- Ensure the sticky nav, floating WhatsApp control (if present), and mobile CTA do not cover FAQ controls, carousel arrows, or page content.
