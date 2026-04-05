# Internal LFS Report — Fat Head's Brewery

**Prospect:** Fat Head's Brewery
**Date:** April 5, 2026
**Status:** Sample site + client report ready

---

## 1. Prospect Overview

- **Owner/contact:** TBD (Nate has the contact — needs to fill in)
- **Business type:** Craft brewery, beer hall, restaurant, distribution, merchandise
- **Service area:** Northeast Ohio (primary), distribution 30+ states
- **Flagship location:** Middleburg Heights — Brewery, Beer Hall & Restaurant (250 seats)
- **Other locations:** North Olmsted, Canton, Pittsburgh
- **Pain points:** The current site was built by Origo Branding on WordPress multisite — it looks good but has real SEO and conversion gaps they likely don't know about. The age gate is actively hurting their search presence. Their biggest awards are buried in carousels.
- **Main goal:** Beer catalog showcase, brand experience, drive visits to Beer Hall
- **Likely buying trigger:** When they see that Google may be indexing their homepage as "Age Verification" instead of their actual business — that's the wakeup call. Pair it with the missing structured data and the fact that their Brewery of the Year win isn't being leveraged properly online.

---

## 2. Real Findings

### Technical:
- WordPress multisite with Yoast SEO v27.2 (built by Origo Branding Company)
- Core Web Vitals PASS in real-user data (CrUX) — site works OK for most visitors
- Lab tests are brutal: mobile LCP = 40.5s, FCP = 12.8s on simulated Slow 4G
- Desktop lab: LCP 6.1s, TBT 230ms — not great but passable
- Best Practices score: 100 (good)
- jQuery Migrate still loaded (legacy dependency)
- Heavy carousel JavaScript across multiple homepage sections
- 99 page resources — too many
- Viewport meta disables pinch-to-zoom (accessibility violation)

### SEO:
- **Critical issue: Page title renders as "Age Verification - Fat Heads Brewery" to crawlers** — confirmed via Rich Results test
- The `age-gate__restricted` class on the HTML element suggests the age gate wraps or blocks the real content during initial render
- Only Breadcrumbs schema detected — no LocalBusiness, Restaurant, Organization, Menu, Event, or Product structured data
- Homepage H1 is just "Fat Head's Brewery" — no location or service keywords
- No city name (Cleveland, Middleburg Heights) in title or H1
- Canonical set correctly to https://fatheads.com/
- Robots meta allows full indexing
- Good URL structure with location-specific paths

### Local SEO:
- No LocalBusiness structured data
- No embedded map on homepage
- GBP not directly linked or referenced from the site
- No service area page or city-targeting landing pages
- NAP present but not structured for search engines
- Multi-location setup could cause entity confusion without proper schema hierarchy

### Conversion:
- No single dominant CTA on homepage
- Beer Finder is the strongest CTA but drives off-site retail (not visits)
- No reservation or online ordering integration visible
- No phone number on homepage without drilling into location pages
- Age gate creates friction on every uncached visit
- Multiple carousels compete for attention
- No sticky mobile CTA

### Trust / brand:
- Awards are carousel slides, not persistent elements
- No third-party review ratings visible (Google, Yelp, Untappd)
- No press logos or "As Seen In"
- Community partnerships are on a subpage, not featured on homepage
- Ohio Craft Brewers Association badge in footer (good, but small)

### Competitor edge:
- Great Lakes Brewing owns the "Ohio's original" positioning and prime Ohio City location
- Market Garden has a stronger food story (chef-driven, seasonal, local)
- Southern Tier has national scale and multi-state taproom presence
- **Fatheads wins on:** awards (untouchable — GABF Brewery of the Year), beer variety, brand personality, community depth

---

## 3. What the Sample Fixed

1. **SEO-safe page title** — "Fat Head's Brewery | Award-Winning Craft Beer & Beer Hall | Middleburg Heights, OH" (not "Age Verification")
2. **Full structured data** — LocalBusiness + Organization JSON-LD with address, hours, cuisine, social profiles
3. **Age gate over content, not replacing content** — the real page content exists underneath for crawlers
4. **GABF Brewery of the Year is prominent and persistent** — badge in hero + dedicated awards section, visible to every visitor
5. **Clear CTA hierarchy** — explore beers → visit Beer Hall → find our beer near you
6. **Beer showcase upgraded** — floating cans in hero + full 6-beer grid with color-coded cards
7. **Flagship location front and center** — address, hours, what to expect, Get Directions + View Menu CTAs
8. **Mobile-first responsive** — clean stacked layout, no carousel overload
9. **Accessibility fix** — no zoom restriction, proper contrast, semantic HTML
10. **Performance foundation** — single HTML file, CSS-only animations, no jQuery/heavy JS

---

## 4. Talking Points

### Visual wins:
- "Look at how the beer lineup hits you immediately — your flagship beers displayed with their own color identity, all visible at once instead of buried in a carousel"
- "The floating beer cans are still there — we kept what makes your site yours. But now it's paired with a stronger layout underneath"
- "GABF Brewery of the Year is the first credibility signal any visitor sees. On your current site, there's roughly a 1 in 5 chance they'll see that slide"

### SEO wins:
- "When we ran the Rich Results test, Google sees your homepage title as 'Age Verification.' That means when someone searches for craft breweries in Middleburg Heights, Google may not know what your page is actually about."
- "Your current site has basic breadcrumb markup. The new version tells Google exactly what you are — a brewery and restaurant, where you're located, your hours, what you serve. That's the difference between a basic listing and a rich one."
- "None of your competitors are doing structured data perfectly either — this is an opportunity to jump ahead."

### Conversion wins:
- "On the new version, a visitor knows within 5 seconds: what you are, where you are, and why you're credible. Then there's a clear path to visit or find your beer."
- "We added explicit CTAs for the Beer Hall — Get Directions and View Menu. Currently those require 2-3 clicks to find."
- "The mobile experience is cleaner — no carousel fatigue, just scroll through the story"

### Likely objections:
- **"Our current site was just built by Origo."** The site looks good and Origo did solid design work. This isn't about replacing what they did — it's about the layer underneath: how Google reads the site, how structured data works, how the age gate affects indexing, and how visitors convert. Those are optimization issues, not design issues.
- **"We're happy with our traffic/business."** The question isn't whether business is good — it's whether the website is working as hard as the brand. When your biggest award is hidden in a carousel and Google might be indexing "Age Verification" as your page title, the site is leaving value on the table.
- **"We don't want to change the brand feel."** We preserved it. Dark palette, floating cans, fun tone, same nav structure. The changes are structural and technical, not aesthetic.
- **"What about the other locations?"** The sample focuses on the flagship because that's the anchor. A full build would bring the same improvements to every location through the multisite structure.

### Responses:
- Lean into the age gate issue — it's specific, provable, and concerning. Show the Rich Results test screenshot.
- Use the structured data gap as a "your competitors could do this first" angle
- The awards story is emotional — "you earned Brewery of the Year and your website hides it"

---

## 5. Close Strategy

- **Default package to pitch:** Full site rebuild + launch (all locations), with technical SEO foundation built in
- **Whether to mention care now:** Yes — position monthly care as protecting the investment (uptime, updates, SSL, backups)
- **Whether to mention growth now:** Mention it lightly — "after launch, we can turn search data into real improvements month over month." Don't lead with it; let the site sell first
- **Whether to keep 90-day test off the table or use as rescue close:** Keep it off the table initially. The evidence here (age gate issue, missing structured data, buried awards) is strong enough that a 90-day test shouldn't be needed. If they're hesitant, use the age gate fix as an urgent standalone offer to build the relationship, then upsell the full build.
- **Strongest angle:** "Google might be reading your homepage as an age verification page. We can fix that and a lot more."
