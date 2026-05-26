# Build Log — fairpoint

## 2026-05-26 — Beyond-Slack repositioning + landing-page glow-up

**Prompt:** "The fairpoint landing page needs some love. make it exciting and change the copy to reflect this is beyond slack. its quick tips that are fair points, and good to know."

**Problem:** The hub still framed Fairpoint as Slack-only ("Tiny, opinionated quizzes on how to use Slack like you mean it"), but only 3 of the 8 live lessons are actually Slack — the rest span meetings, shipping, statistics, and money. The page also read as a flat list, lacking the arcade energy of the sites it links to.

**Solution:**
- **Copy, fully beyond Slack:** new subheadline ("Quick, opinionated tips worth knowing — on Slack, meetings, money, stats, and shipping. Each one's a fair point."), rewrote the "what is this" box around concrete-not-vague + "good to know," renamed the section heading "The lessons" → "The fair points," and broadened the meta description + "Coming soon" invite. Kept the tagline "A fair point at a time."
- **Visual glow-up (within the Playful Arcade tokens):** added a three-chip stats strip (`8 lessons · 280+ scenarios · ~5 min each`) with rotating accent borders; gave each lesson card a category tag pill + matching colored left accent border, mapped to existing tokens — Slack→purple-electric, Meetings→coral, Shipping→lime, Stats→gold, Money→deep purple.
- Added a `category` field to each `LESSONS` entry and a `CATEGORIES` color map; render JS sets per-card `--accent`/`--accent-ink` CSS vars. Existing `textContent` escaping unchanged (DESIGN.md trust boundary).

**Key decisions:** Stayed strictly within `fairpoint-kit/DESIGN.md` (named tokens only, 2px ink borders + offset shadows, Space Grotesk display). Used the 5 existing palette tokens for the 5 categories so cards rotate color without introducing new hex. Rounded scenario count down to a safe "280+" (actual ~283 across the 7 quizzes).

**Verification:** Served locally and screenshotted in the gstack headless browser at 720px (desktop) and 390px (mobile) — stats strip, tags, and accent borders render correctly, links intact, no console errors.

**Changed files:** `index.html`, `BUILD_LOG.md`

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
