# NovaCast Studio — Landing Page PRD

**Version:** 0.3

**Reference:** Current `index.html`; this document does not authorize changes to it.
**Status:** Requirements for the current WhatsApp-first, paid-pilot funnel.

## 1. Product goal

Convert qualified B2B buyers into paid Starter Test Packs and suitable monthly retainers. Reduce low-intent inquiries through clear package scope, qualification, and direct WhatsApp conversation.

## 2. Audience and positioning

- **Primary:** US DTC/Shopify brands and GCC advertisers, especially growth marketers and paid media buyers.
- **Secondary:** B2C apps with an ongoing need for short-form paid-social creative.
- **Positioning:** Premium, minimalist, performance-driven AI UGC-style creative for hook and angle testing.
- **Site language:** English only. Arabic is not a website language toggle; Khaleeji/Gulf Arabic is a production option confirmed per project and market.

## 3. Core promise and claim boundaries

Create hook-first short-form creative for paid-media testing with rapid turnaround. State the first delivery as **48–72 hours depending on brief approval and required asset readiness**. Confirm the schedule for each project; it is not an unconditional guarantee.

- Do not guarantee ROAS, CPA, CTR, sales, conversion lift, platform approval, or elimination of creative fatigue.
- Do not present synthetic testimonials as personal use or real customer endorsements unless compliant, substantiated, and approved for the relevant market and placement.
- Usage rights, permissions for supplied assets, and platform acceptance are subject to project terms and platform rules; acceptance is not guaranteed.
- No website lead-capture forms or email contact routes. WhatsApp is the sole landing-page conversion route.

## 4. Page sections (mapped to `wireframe.md`)

1. Sticky navigation with brand, section links, and one **Chat on WhatsApp** CTA.
2. Hero with hook-first AI UGC value proposition, paid-media context, a single WhatsApp CTA, and optional non-conversion “View Samples” scroll link.
3. Traditional vs NovaCast workflow comparison.
4. Creative Showcase: 9:16 horizontal scroll-snap video carousel.
5. Four-step process: brief → hooks/angles approval → production → delivery.
6. Three package cards: Starter, Growth, Retainer; each CTA opens WhatsApp.
7. FAQ accordion.
8. Final WhatsApp CTA banner.
9. Minimal footer with legal/commercial terms note.

## 5. Conversion and measurement

- **Only conversion event:** click on a WhatsApp link (`whatsapp_click`). Apply this event consistently to all WhatsApp CTAs; optionally attach a non-conversion `cta_location` property such as `nav`, `hero`, `package`, `final`, or `floating`.
- Use a WhatsApp deep link with a prefilled message. Production URL pattern: `https://wa.me/PHONE_NUMBER?text=...&utm_source=website&utm_medium=whatsapp&utm_campaign=paid_pilot`.
- Keep the phone number configurable; replace the project’s `YOUR_PHONE_NUMBER` placeholder before launch.
- Track the click using Plausible or GA4, subject to the site’s privacy configuration. Validate that click tracking works before deployment.
- Attribute the entry page’s UTM values in analytics; preserve campaign/source context in the WhatsApp link where supported. Do not treat page views, carousel interaction, or video playback as additional conversion events.
- Primary KPI: WhatsApp CTA click-through rate from landing page sessions. Business outcome review may separately inspect qualified conversations and paid-pilot sales without defining them as additional site conversion events.

## 6. Intake requirements

Collect through the WhatsApp conversation before production:

- Product/store URL and product/SKU to feature.
- Target geography, audience, placement, and campaign objective.
- Offer, price, product benefits, approved CTA, and relevant product facts.
- Brand assets and guidance: logo, product imagery, colors, voice, examples, and approved likeness/voice permissions.
- Do-not-say list, claim substantiation, regulated categories, and other angle constraints.
- Required language and market dialect; confirm Khaleeji/Gulf Arabic availability and suitability per project.
- Desired launch date, review owner, asset readiness, and budget fit for a paid pilot.

## 7. Package requirements

Public pricing may remain quote-based. Confirm the exact scope, schedule, rights, and review windows before production.

| Package | Deliverables | Schedule and revisions |
|---|---|---|
| Starter Test Pack | 3 short-form videos, typically 15–35 seconds, with distinct hooks; burn-in captions and clean-caption exports as scoped | First delivery in 48–72 hours depending on approved brief and asset readiness; one text/hook revision pre-production and one style revision post-delivery unless otherwise agreed |
| Growth Creative Pack | 8–12 videos per month, agreed hook/angle matrix, captioned and clean-caption exports as scoped | Weekly batches; language, volume, and revision scope agreed before kickoff |
| Ad Machine Retainer | 20–30 videos per month, ongoing planning with media buyer and creative backlog | SLA, approvals, and revision scope agreed before kickoff |

## 8. Creative Showcase requirements

- Horizontal carousel with CSS scroll snap, swipe/touch support, and accessible previous/next controls.
- Six vertical cards based on the current page’s examples; each card uses 9:16 media, poster image, niche/hook labels, and a replaceable MP4 source.
- Videos use `muted`, `loop`, `playsinline`, and `preload="none"`.
- IntersectionObserver starts playback only when a card is at least 60% visible and pauses it when it falls below the threshold or leaves view. Only one video may play at a time.
- Concept media must be identified as concept work, not client results or proof.

## 9. Functional, accessibility, and responsive requirements

- English copy throughout the site; dialect options appear only as production capabilities.
- Mobile-first layout with usable sticky navigation and no horizontal page overflow.
- Maintain keyboard focus visibility, descriptive control names, semantic headings, and readable contrast.
- FAQ answers remain available in the document structure when collapsed; buttons expose accurate expanded state and control relationships.
- Provide explicit image dimensions and descriptive alt text. Video controls must remain operable on touch and keyboard.

## 10. Acceptance criteria

- [ ] Every landing-page conversion button opens WhatsApp with a prefilled message; no other conversion CTA is present.
- [ ] No web lead-capture forms or email contact routes exist.
- [ ] Site content is English-only; Khaleeji/Gulf Arabic is clearly an optional production language/dialect.
- [ ] Hero communicates hook-first AI UGC for paid-media testing and rapid 48–72-hour turnaround with dependencies stated.
- [ ] Comparison, showcase, four-step process, packages, FAQ, final CTA, and minimal footer match `wireframe.md`.
- [ ] Carousel meets video attributes, 60% visibility, one-at-a-time playback, and responsive swipe behavior.
- [ ] Package counts, caption deliverables, revision boundaries, and schedule match the approved scope.
- [ ] `whatsapp_click` is verified in the selected analytics tool; WhatsApp link contains the agreed source/campaign attribution pattern.
- [ ] Mobile/desktop layout, accessibility basics, and performance are reviewed before release.
- [ ] Actual WhatsApp Business number, final video assets, and production metadata replace temporary values before launch.

## 11. Commercial and legal boundaries

The client confirms rights to supplied product assets, logos, music, likenesses, and voice references. NovaCast confirms dialect, pronunciation, and deliverability before quoting. Commercial usage scope and restrictions are stated in project terms. Client approval is required for claims and final creative. Neither performance nor platform acceptance is guaranteed.
