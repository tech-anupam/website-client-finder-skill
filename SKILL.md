---
name: website-client-finder
description: Find and qualify businesses with a weak, outdated, missing, or slow-performing website, verify public business contact details, score leads by opportunity, and draft genuinely personalized outreach pitching a standalone website build/redesign — matched to the relevant live project from a supplied portfolio. Produces a structured Excel lead list. Use for cold-outreach lead generation involving website audits (performance, mobile-friendliness, design, presence), Claude web research, and spreadsheet creation. Trigger for requests like "find me web dev clients," "find businesses with bad websites," "website leads outreach," "find leads for my portfolio," even if the user doesn't say "skill."
---

# Website Client Finder

Find businesses that need a new standalone website or a rebuild of their current one, then produce verified, scored leads with personalized outreach drafts pitching website development services — anchored on a real, matching project from the user's own portfolio.

Do not send messages. Prepare outreach drafts for user review unless the user explicitly asks to send them through an available communication tool.

## Required input

Accept a short request containing:

- Portfolio: either a portfolio URL, or a list of the user's own live projects (name + one-line description + link, if any) to draw case studies from
- Target industry/niche(s) (e.g. local services, D2C ecommerce, tutoring, clinics, restaurants) or explicit business examples
- Optional target market/city (default: Delhi NCR if the user gives no market and the business type is local/hyperlocal; otherwise worldwide English-speaking)
- Optional lead count; default to 50
- Optional qualifying issue focus: no website at all, outdated/template site, slow performance, not mobile-friendly, poor SEO/no local presence — default to all of these

If the portfolio or target industry is missing, ask before starting.

## Interpret the target direction

Derive search categories from the user's stated industry/niche or example businesses. Expand into closely related business types with similar site needs, without drifting into unrelated categories.

Prioritize businesses that:

- Are real, operating businesses with a public presence (site, social, or directory listing)
- Have a clear, demonstrable site problem (see qualifying issues below)
- Plausibly have budget/willingness to pay for a website (registered business, paid ads, physical location, active social commerce)
- Fit a case study already in the portfolio (a redesign pitch lands harder when the sample shown is in the same domain)

## Phase 1: Discover candidates

Use web search and public directories to find businesses in the target category and market. Useful sources: Google Maps/local business listings, Google/Bing search for the niche + city, Instagram/Facebook business pages that link out (or fail to link out) to a site, industry directories, Justdial/IndiaMART for Indian local businesses, marketplace seller pages for ecommerce.

For every candidate, collect when available:

- Business name
- Industry/category
- City/market
- Current site URL (or "No website found")
- Social presence (Instagram/Facebook/LinkedIn handle)
- Source URL where the business was found

Never invent a URL, business name, or detail. Mark unavailable fields `Not found`.

## Phase 2: Audit the site (or its absence)

For each candidate with an existing site, inspect it directly with `web_fetch` and note concrete, observable issues. For candidates with no site, the absence itself is the qualifying issue — note where their presence currently lives instead (Instagram bio, Linktree, WhatsApp Business, marketplace-only listing).

Qualifying issues to check for and record, with specific evidence (not a generic label):

- **No standalone site** — business only exists on social/marketplace/directory listings
- **Performance** — slow load, unoptimized images, render-blocking assets, no caching; note what you observed (large hero image, no lazy loading, bloated third-party scripts) rather than an invented score
- **Mobile-friendliness** — broken layout, unreadable text, tap targets too small, non-responsive on a narrow viewport
- **Outdated design/stack** — visibly old template, Flash-era patterns, expired SSL, broken links, stale copyright year
- **No conversion path** — no clear CTA, no contact form, no booking/ordering flow, no way to reach the business from the site
- **No local/SEO presence** — no Google Business Profile, no local schema, site doesn't rank for the business's own name

Do not run automated Lighthouse/PageSpeed scoring unless a tool for it is actually available — if none is available, assess performance and mobile-friendliness by direct inspection of the fetched page (asset sizes, structure, viewport meta tag, responsive CSS) and say so plainly in the notes rather than presenting an invented numeric score.

Do not insult the business or its existing site. Describe the opportunity constructively and specifically — this is what goes into the outreach message later.

For every lead, produce:

- Current site summary (or "no site" summary)
- Specific, evidence-based opportunity (1–2 concrete issues, not a generic list)
- Recommended fix/deliverable (new standalone site, performance pass, mobile rebuild, landing page + booking flow, etc.)
- Matching portfolio project — the one existing project from the user's portfolio closest to this business's domain or need, and why it's the right reference

## Phase 3: Qualify and score leads

Remove candidates that:

- Have no verifiable public presence at all
- Are large chains, franchises, agencies, or corporations with an in-house dev team (unless the user explicitly wants these)
- Have a genuinely solid, fast, modern site with no real opportunity
- Sell prohibited, unsafe, or deceptive products/services
- Duplicate a business already included

Score each remaining lead from 0 to 100:

| Factor | Points | Standard |
| --- | ---: | --- |
| Site opportunity severity | 30 | No site at all scores highest; specific, evidenced performance/design issues score next |
| Business/portfolio fit | 20 | Close match to an existing portfolio project's domain |
| Ability to pay | 20 | Evidence of active operations — physical location, paid ads, active social commerce, existing (if weak) site investment |
| Contactability | 20 | Verified official contact channel |
| Market fit | 10 | Matches user's stated target market/city |

Prioritize high-scoring leads. Do not use invented revenue, traffic, or budget estimates.

## Phase 4: Find verified public business contacts

Research each qualified lead's official channels for contact details.

Search in this order:

1. Site contact page (if a site exists)
2. Google Business Profile / directory listing contact info
3. Social bio / "contact us" link (Instagram, Facebook, LinkedIn)
4. WhatsApp Business number if publicly listed

Prefer:

- Owner/manager email or general business email
- Contact form URL when no email is published
- Public business phone/WhatsApp number
- A publicly named owner/decision-maker only when verified on an official or reliable public source

Never guess email patterns, invent names/roles/numbers, or use leaked/paywalled data. Save the source URL used to verify every contact. When nothing is verifiable, write `Not found` and keep any public contact-form or DM channel as a fallback.

## Phase 5: Write personalized outreach

One original message per lead. Personalize using the specific site issue found and the matching portfolio project — not just the business name.

Structure:

**Subject:** A short, specific idea for [Business Name]'s website

**Message:**

1. Address the business/contact naturally.
2. Mention the specific thing observed (their current site, or the fact they don't have one yet, named concretely).
3. One genuine positive observation about the business itself (not the site).
4. Name the specific opportunity without insulting current work.
5. Reference the matching portfolio project by name as proof of relevant, shipped work — one line on why it's relevant to their case.
6. Introduce the offer: a fast, standalone site/rebuild focused on performance and conversion, built and shipped quickly.
7. Include the portfolio link.
8. End with a low-pressure question inviting a reply.

Keep each message 70–120 words. Natural human tone. No guaranteed-results claims, no spam language, no identical copy across leads.

Default CTA:

> Want to see a quick mockup of what this could look like?

## Phase 6: Create the Excel workbook

Create an `.xlsx` workbook named `website_client_leads.xlsx` with three sheets.

### Sheet 1: Qualified Leads

Columns in this order:

1. Lead ID
2. Opportunity Score
3. Business Name
4. Industry
5. City/Market
6. Current Site URL (or "No website found")
7. Social Presence
8. Source URL
9. Site Issue Summary
10. Specific Opportunity
11. Recommended Deliverable
12. Matching Portfolio Project
13. Contact Person
14. Contact Role
15. Public Business Email
16. Public Business Phone
17. Contact Form URL
18. Contact Verification Source
19. Email Subject
20. Personalized Message
21. Verification Status
22. Notes

### Sheet 2: Top Prospects

The 15 highest-scoring leads with the same contact/outreach fields, plus a `Why Prioritize` column with one concise reason.

### Sheet 3: Research Summary

Include: search date, date window, target industries, target market, candidates reviewed, qualified leads, leads with verified emails, leads with contact forms only, leads rejected, rejection reasons, scoring methodology, important limitations (note explicitly that performance/mobile assessments are manual inspections, not automated audit-tool scores, unless such a tool was actually used).

## Workbook quality requirements

- Sort by Opportunity Score, highest to lowest.
- Freeze header row, enable filters.
- Wrap long text, set useful column widths.
- Format URLs as clickable links.
- Consistent date formatting.
- Highlight missing contacts and unverified fields.
- Deduplicate by domain/business name.
- Every personalized message must reference the correct row's business and issue.
- No formulas with calculation errors.

## Final validation

Before delivery:

1. Open and inspect the workbook.
2. Confirm every lead has a real, verifiable public presence.
3. Confirm every listed email/phone has a verification source.
4. Open a sample of site, source, and contact links.
5. Check no message contains another lead's name/details.
6. Check all portfolio links/project references are correct.
7. Confirm no invented information appears anywhere.
8. Report the exact number of qualified leads and verified contacts.

## Final response

Provide:

- A link to the completed Excel workbook
- Total candidates reviewed
- Total qualified leads
- Total verified emails
- Total contact forms
- Short summary of the top three prospects
- Any research limitations

Do not send outreach automatically. Ask the user to review and approve the spreadsheet and messages first.

## Short invocation example

> Find [NUMBER] businesses in [INDUSTRY/NICHE] in [CITY/MARKET] with a weak or missing website and create the verified lead workbook with personalized outreach, using [my portfolio: PROJECT LIST OR URL].
