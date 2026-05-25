# Build Log — fairpoint

## 2026-05-25 — Re-skin to "Playful Arcade" design system

**Prompt:** "Looks great, push" — after rendering the new Fairpoint design system across all sites.

**Problem:** The hub's flat white-on-gray cards were generic and didn't match the more engaging direction.

**Solution:** Restyled `index.html` to the `fairpoint-kit` "Playful Arcade" system — Space Grotesk display type, neobrutalist 2px-ink-border + offset-shadow cards with hover lift, vivid purple/lime/coral palette, paper background with faint radial glows, and a "Play ▸" badge on each lesson card. The data-driven `LESSONS`/`COMING_SOON` script is unchanged — content and links are identical.

**Changed files:** `index.html`

## 2026-05-21 — Initial scaffold

**Prompt:** "Create the fairpoint.website landing page that links to our two sites. more to come."

**What landed:**
- New folder `/Users/pfrazier/Documents/claude/fairpoint/`
- Single-file static landing page at the fairpoint.website apex
- Data-driven `LESSONS` and `COMING_SOON` arrays so adding a new site is a one-line edit
- Hero + tagline + "what is this" callout + lesson cards + coming-soon list + footer
- Identical CSS palette to the quiz sites (Slack purple, yellow accent) for brand cohesion

**Lessons listed (live):**
- Don't use @here → dontuseathere.fairpoint.website
- Send to channel… less → sendtochannelless.fairpoint.website

**Coming soon (placeholders):**
- Use threads. (thread-evangelism site, name TBD)
- More. (CTA for issue-submission)

**Brand voice notes:**
- Tagline "A fair point at a time." plays on the name — each lesson is making one small but important point.
- Each lesson card uses the lesson's directive as the title (not a generic name).
- "What is this" section explicitly contrasts with vague Slack-etiquette advice ("use threads more") — Fairpoint is concrete.

**Pending:**
- GitHub repo creation + initial push
- Vercel project + apex domain wiring (A record, not CNAME — apex domains)
- Add "More from Fairpoint →" footer link to dontuseathere site (sendtochannelless already has it)
