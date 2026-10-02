# Blogging on Webflow

Oct 2, 2026 · @Pamela

**Yes, if the design team builds the blog template and fields once, up front.** After that, writers fill in a form-like editor, preview and publish a post. They never touch the layout. In WordPress a post's layout can change post to post; on Webflow every post uses the same template. The trade-off is a little less flexibility per post in exchange for consistency.

## Publishing flow

&#91;embedded content: blog publishing flow · 4 steps, 1 decision\]

Writers handle every step themselves. The design team only steps in when the post template itself needs to change, which should be rare.

## Who can do what

Non-design editors get a **Content editor** seat. They can write and publish blog posts but can't change page design, styles or components. Seat prices are approximate and need checking (see Limits and costs).

| Person | Webflow role | Seat type | Can do | Can't do |
| --- | --- | --- | --- | --- |
| Writers / non-design editors | Content editor | Limited (\~$15/mo) | Create, edit, preview, schedule and publish blog posts | Change layouts, styles or other pages; publish the whole site |
| Designers | Designer | Full (\~$39/mo) | Build and change the blog template, components and pages | Publish the whole site unless allowed |
| Site owner (one or two people) | Site manager or Admin | Full | Publish the whole site, manage roles, redirects, settings |  |
| Approvers (leadership, legal) | Reviewer | Free | View drafts and leave comments | Edit anything |

One caveat: a content editor can publish their own post directly. If a post needs approval first, that's a team rule, not something Webflow enforces. See Open questions.

## Setup that keeps it easy

The design team builds a few CMS collections and one post template. Writers then just fill in fields. This maps today's Feed post fields to Webflow:

| Today on The Feed | On Webflow | Note |
| --- | --- | --- |
| Title, date, sub head | Post fields: name, publish date, plain-text sub head | Same as today |
| Body (WordPress blocks) | Rich text field: headings, lists, quotes, images, video embeds | Custom WordPress blocks don't carry over. Anything special becomes a template option or a field. |
| Author name, title, photo (typed on every post) | **Authors** collection, picked from a dropdown on each post | Better than today: set each author up once |
| Categories, "show in filter", recommended post | **Categories** collection plus reference fields | Same behavior, done once in the template |
| Feed type (standard, carousel, slides, video) | An option field that shows or hides parts of the template | Designers build each variant once |
| Image carousel with a caption per image | Multi-image field | **No per-image captions.** Put captions in the body, or use a separate Gallery collection. Designers should decide this. |
| Google Slides embed, video embed | Video or link field, or an embed block in rich text | Works; designers style the embed once |

What keeps this sustainable:

- **A writer's guide of one page:** which fields are required, image sizes, how long the sub head should be, how to choose a category.
- **A draft post kept as a template** that writers duplicate.
- **Required fields and character limits** set in the collection, so incomplete posts can't be saved.
- **The design team owns the template.** Writers never need Designer access.

## Limits and costs to know

A blog at our volume is well inside Webflow's limits. The ongoing cost is mostly seats for each writer. **All figures below are approximate and unverified.** Confirm them on [Webflow pricing](https://webflow.com/pricing) before budgeting.

| Item | Approximate figure | What it means for us |
| --- | --- | --- |
| Site plan with CMS | \~$25/mo billed yearly | Needed for any blog. Webflow reportedly merged its CMS and Business plans in May 2026; older articles show different tiers. |
| CMS item limit | Reportedly 20,000 items (older plans: 2,000 or 10,000) | Years of posts, even at several a week |
| Content editor seat | \~$15/mo per writer | The main ongoing cost as the writer pool grows |
| Reviewer seat | Free | Approvers can comment on drafts at no cost |
| Scheduled publishing | Included on CMS plans | Writers can queue posts ahead |

## Open questions for the design team

- [ ] How often do we want to post, and how many people will write? This sets the seat count.
- [ ] Does every post need approval before it goes live? If yes, who approves, and do writers save drafts while the approver publishes?
- [ ] Carousel captions: put them in the body, or build a Gallery collection?
- [ ] Should existing Feed posts all move to Webflow, or only recent ones?
- [ ] Who on the design team owns the template and the writer's guide?
