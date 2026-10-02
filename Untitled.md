# Webflow Migration Requirements and Timeline

Oct 2, 2026 · @Pamela

**Estimate: about 20 weeks (roughly 5 months) from go-ahead to switching off WP Engine, with the team working part-time on it.** With dedicated time it could compress to about 12 weeks. The main site is a rebuild, not a copy: Webflow can't import our WordPress theme. Most of the work is design-system setup, rebuilding custom page types, and moving content. These are planning estimates, to be firmed up in the first two weeks.

## Scope

Only the WordPress sites on WP Engine are in scope. The apps on Vercel stay where they are. Fewer sites means lower recurring cost, so a few older sites are better archived than migrated.

| Site | Today | Recommendation |
| --- | --- | --- |
| codewordagency.com (main site, plus stage and dev) | WordPress on WP Engine | **Migrate.** This is most of the work. |
| speechwriting.codewordagency.com | WordPress on WP Engine | Migrate. Check whether it's a separate install or a page of the main site. |
| learningdesign.codewordagency.com | WordPress on WP Engine | Migrate. Same check. |
| volumezine.codewordagency.com | WordPress on WP Engine | Decide: migrate, or archive as a static snapshot |
| prom.codewordagency.com (2023) | WordPress on WP Engine | Archive or retire |
| Cannes 2025 page (on the main site) | WordPress page and form | Retire before the move |
| aintelligentstudios.com | Early app-like mini-site | Probably not a Webflow fit. Move to Vercel or archive. |
| 666fm.live, Font of the day, AI SEO tool | Vercel | No change |

On the main site, these content types need rebuilding as Webflow collections and templates: blog posts (The Feed), case studies, reports, jobs, press, events, recent projects and leadership.

## Requirements

**People.** Time is the biggest requirement. Effort figures are rough estimates for the whole project.

| Role | Who | Responsibilities | Rough effort |
| --- | --- | --- | --- |
| Transition lead | Marketing | Owns the plan, decisions, content inventory and sign-off | 1–2 days a week throughout |
| Webflow designer(s) | Design team | Design system, components, collection templates, page builds | 8–12 weeks of part-time work |
| Developer | Creative development | CMS structure, forms and Mailchimp, redirects, SEO, DNS, interactive pages, QA | 6–8 weeks of part-time work |
| Content editors | Marketing and others | Move and check content, then publish going forward | 1–3 weeks during migration |
| Approver | Leadership | Go/no-go at each gate | A few hours per gate |

**Accounts and access**

- [ ] Webflow workspace plan, plus one site plan for each site we keep
- [ ] Login for the domain registrar and DNS for codewordagency.com and its subdomains. **This isn't documented today, so finding out who has it comes first.**
- [ ] Admin access to Mailchimp and any connected Google Sheets
- [ ] WP Engine contract end date, so the cutover lands before renewal

**Content**

- [ ] An inventory of every page and post: keep, merge or drop
- [ ] Media library export (images, PDFs, video)
- [ ] SEO titles, descriptions and social images for pages we keep
- [ ] **An export of the current redirect list.** Missing redirects are the most common cause of lost search traffic after a migration.

**Features to rebuild**

| Today | On Webflow |
| --- | --- |
| Contact form with submissions emailed and saved | Webflow Forms (built in) |
| Newsletter opt-in checkbox on the contact form | Small integration (e.g. Zapier or Make) to add subscribers to Mailchimp |
| Newsletter signup embeds | Same Mailchimp embed, placed in Webflow |
| Custom report pages (long-scroll, colour wheel, scales, floating cards) | Rebuild each pattern as a Webflow component. This is design-heavy. |
| Sentiment heatmap page | Custom code. Keep it as an embed, or host it on Vercel. |
| SEO plugin, redirects plugin, media folders | Built into Webflow |
| Login security and update routine | Mostly no longer needed: there's no WordPress login or plugins to patch |

## Timeline

&#91;embedded content: migration timeline · 7 phases, 3 gates\]

Phases overlap so the design system and the pilot inform the main build. If the pilot shows editors can't publish without help, we stop at week 7 with little sunk cost. WP Engine stays live until four weeks after launch as a fallback.

## Cost estimate

With our likely setup, Webflow would cost **roughly $260 a month (about $3,100 a year)**, before comparing it with our WP Engine bill. **The prices are approximate and unverified.** I couldn't open Webflow's pricing pages while researching this, so confirm on [Webflow pricing](https://webflow.com/pricing) before budgeting.

| Item | Assumption | Approx. monthly cost |
| --- | --- | --- |
| Site plans with CMS (\~$25 each, billed yearly) | 4 sites: main, speechwriting, learning design, Volume | \~$100 |
| Full seats (\~$39 each) | 2 designers | \~$78 |
| Content editor seats (\~$15 each) | 4 writers and editors | \~$60 |
| Reviewer seats | Approvers | Free |
| Mailchimp opt-in integration (Zapier or Make) | One small automation | \~$20 |
| **Total** |  | **\~$260** |

The one-off cost is team time (see Requirements), plus a Webflow agency partner if we want to go faster. Still needed for a fair comparison: the current WP Engine cost and its renewal date.

## Risks and decisions needed

| Risk | What could happen | How we reduce it |
| --- | --- | --- |
| Missing redirects | Old links break and search traffic drops | Export redirects early and test every old URL before cutover |
| No one has DNS access | Launch is blocked on the last day | Find the registrar login in week 1 |
| Rebuilding report pages takes longer than expected | The timeline slips | Rebuild the most-used report patterns first and simplify the rest |
| Writers publish without review | Off-brand or incorrect posts go live | Agree publishing rules and roles before launch |
| Lock-in | Leaving Webflow later is another rebuild | Accept it knowingly. Content can be exported as CSV; layouts can't. |

**Decisions before starting**

- [ ] Go-ahead and budget
- [ ] Which sites migrate, and which are archived or retired
- [ ] Who is on the core team, and how much time each person has
- [ ] Publishing rules: who can publish, and whether posts need sign-off
- [ ] Target launch date, set against the WP Engine renewal date
