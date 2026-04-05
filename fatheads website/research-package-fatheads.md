# Step 2A Research Package — Fat Head's Brewery

**Prospect:** Fat Head's Brewery
**Website:** https://fatheads.com/
**Date:** April 5, 2026
**Focus:** Flagship location — Middleburg Heights, OH

---

## 1. Business Summary

- **Business name:** Fat Head's Brewery
- **Business type:** Craft brewery, beer hall, restaurant, retail (merch/gift shop)
- **Main services:** Award-winning craft beer (20-tap beer hall), full food menu (smokehouse wings, headwiches, burgers, stone oven pizza), self-guided brewery tours, catering, beer finder/distribution (30+ states), online store (apparel, glassware, gift cards)
- **Flagship location:** 17450 Engle Lake Dr, Middleburg Heights, OH — 250-seat Beer Hall, opened 2018
- **Hours:** Mon–Thu 12–9pm, Fri 12–10pm, Sat–Sun 11am–9pm
- **Other locations:** North Olmsted (Brewery & Saloon), Canton (Brewpub), Pittsburgh (South Shore Saloon)
- **Service area:** Cleveland metro / Northeast Ohio (primary), distribution across 30+ states
- **Main contact methods:** Phone, contact form (fatheads.com/contact/), individual location pages
- **Key trust elements:** 2025 GABF Brewery of the Year (15,001–100,000 barrels), 35+ GABF medals since 2009, WBC Gold for Head Hunter IPA, community partnerships (Cleveland Guardians, Monsters, Metroparks, Workshop of Wishes), Ohio Craft Brewers Association member
- **Social links:** Instagram @fatheadsbeer (30K followers), Facebook /fatheadsbeer, Twitter/X @fatheadsbeer, TikTok @fatheadsbeer, LinkedIn /fat-head-s-brewery/
- **Founded:** 1992 (Pittsburgh saloon), Ohio expansion 2009, production brewery 2012, current Middleburg Heights facility 2018
- **Signature beers:** Head Hunter IPA, Bumble Berry Honey Blueberry Ale, Hazy Head Hunter IPA, Crumble Berry, Lime Feelin' Good
- **Website platform:** WordPress multisite (Yoast SEO v27.2), built by Origo Branding Company
- **Store:** store.fatheads.com (separate e-commerce platform)

---

## 2. SEO / Local SEO Findings

### Search relevance strengths:
- Strong brand name recognition in Ohio craft beer space
- Yoast SEO installed with canonical tags properly set
- Robots meta allows indexing: `index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1`
- Clean URL structure with location-specific paths (/middleburg-heights/, /north-olmsted/, etc.)
- Good internal linking between beer pages and Beer Finder
- Strong topical authority content (How We Brew, Awards, Our Story, individual beer pages, release calendar)

### Search relevance weaknesses:
- **CRITICAL: Page title renders as "Age Verification - Fat Heads Brewery" to crawlers.** The age gate intercepts the page load, meaning Google may see the age verification screen rather than the real homepage content. This is a significant SEO vulnerability.
- Homepage H1 is just "Fat Head's Brewery" — no service/location context for search engines
- No city or service-type keywords in the homepage title or H1 (e.g., "craft brewery in Cleveland" or "Middleburg Heights brewery")
- Heavy reliance on carousels for key content (Featured Beer, Promos, Events) — carousel content may not be fully crawled or indexed
- Beer Finder relies on external tool/JS — unclear crawlability

### Local clarity strengths:
- Location pages exist for each location with addresses and hours
- Visit page acts as a location hub
- Hours displayed on homepage for each location

### Local clarity weaknesses:
- No LocalBusiness or Restaurant structured data detected (only Breadcrumbs schema found in Rich Results test)
- No explicit city targeting on the main homepage — the word "Cleveland" or "Middleburg Heights" doesn't appear prominently
- GBP links not directly referenced or connected from the site
- No embedded map on the homepage
- Missing explicit service area page or neighborhood/city content

### Internal linking notes:
- Good internal link structure through main nav and footer
- Beer pages link to Beer Finder
- Location pages link to their own food/drink menus
- Missing: cross-linking between blog/content and service pages, no location-specific landing pages targeting search queries

### Structured data notes:
- **Only Breadcrumbs schema detected** (1 valid item per Rich Results test)
- Missing: LocalBusiness, Restaurant, Organization, Menu, Event, Product schemas
- This is a significant gap — competitors with proper schema will have richer search appearances

### Business details / entity notes:
- NAP (Name, Address, Phone) is present but not prominently structured for search
- Multiple locations could cause entity confusion without proper Organization + LocalBusiness schema hierarchy
- Ohio Craft Brewers Association badge in footer provides trust signal but isn't schema-connected

---

## 3. Speed / Technical Findings

### PageSpeed — Real User Data (CrUX, 28-day):

**Mobile (Passed CWV):**
| Metric | Value | Status |
|--------|-------|--------|
| LCP | 1.6s | Good (91% good) |
| INP | 79ms | Good (98% good) |
| CLS | — | Good (92% good) |
| FCP | 1.2s | Good (90% good) |
| TTFB | 0.7s | Good (83% good, 14% needs improvement) |

**Desktop (Passed CWV):**
| Metric | Value | Status |
|--------|-------|--------|
| LCP | 2.0s | Good (84% good, 12% needs improvement) |
| INP | 45ms | Good (98% good) |
| CLS | — | Good (98% good) |
| FCP | 1.0s | Good (93% good) |
| TTFB | 0.5s | Good (87% good) |

### Lighthouse Lab Test Scores:

**Mobile (simulated Slow 4G):**
| Metric | Value | Rating |
|--------|-------|--------|
| FCP | 12.8s | Poor |
| LCP | 40.5s | Poor |
| TBT | 700ms | Poor |
| Speed Index | 12.8s | Poor |
| Best Practices | 100 | Good |

**Desktop:**
| Metric | Value | Rating |
|--------|-------|--------|
| FCP | 0.9s | Good |
| LCP | 6.1s | Poor |
| TBT | 230ms | Moderate |
| CLS | 0.004 | Good |
| Speed Index | 1.4s | Good |
| Best Practices | 100 | Good |

### Analysis:
- Real user experience passes Core Web Vitals — the site is functional for most visitors
- Lab tests show severe performance under constrained conditions (40.5s LCP on simulated mobile is extreme)
- This gap suggests heavy JavaScript/asset loading that real-world caching and fast connections mask, but slower devices or first visits could be painful
- The age gate adds a render-blocking interaction before any content loads
- 99 page resources loaded, 1 blocked (reCAPTCHA image by robots.txt — minor)

### Core UX / mobile notes:
- Viewport meta has `maximum-scale=1` — **disables pinch-to-zoom, which is an accessibility violation**
- Homepage is very long with multiple carousels (Featured Beer, Promos, Events, Instagram feed)
- Age gate creates friction for every new visitor
- Multiple carousel implementations may cause JS bloat

### Rendering or asset issues:
- jQuery Migrate 3.4.1 still loaded (legacy dependency)
- Heavy carousel/slider JS for multiple homepage sections
- reCAPTCHA loaded on page (newsletter form)

### Indexing or eligibility concerns:
- **Age gate class `age-gate__restricted age-gate__restricted--js` on HTML element may interfere with crawler rendering**
- Page title showing "Age Verification" to crawlers is a confirmed issue from the Rich Results test
- 1/99 resources blocked (minor — reCAPTCHA logo)
- Canonical set correctly to https://fatheads.com/

---

## 4. Competitor Notes

### Competitor 1: Great Lakes Brewing Company (greatlakesbrewing.com)
- Ohio's original craft brewery (est. 1988), strong heritage brand
- Located in Ohio City — prime Cleveland location near West Side Market
- Full brewpub restaurant experience
- Strong brand storytelling and seasonal beer marketing
- Well-established local SEO presence in Cleveland
- **Advantage over Fatheads:** Longer history, prime Cleveland location, stronger "original craft brewery" positioning
- **Where Fatheads wins:** More awards (GABF Brewery of the Year), stronger beer portfolio breadth, better multi-location infrastructure

### Competitor 2: Southern Tier Brewing Company (stbcbeer.com)
- Large-scale craft producer (est. 2002, Lakewood NY), distribution in 30+ states
- Multiple taprooms including Cleveland location
- Location-specific subdomains (cleveland.stbcbeer.com)
- 110 BBL Steinecker brewhouse — serious production scale
- **Advantage over Fatheads:** National scale, multi-state taproom presence, strong production story
- **Where Fatheads wins:** Stronger local roots, more personal brand feel, better award pedigree, more fun/irreverent brand personality

### Competitor 3: Market Garden Brewery (marketgardenbrewery.com)
- Ohio City location next to West Side Market — strong neighborhood identity
- Chef-driven gastropub menu with seasonal, local, organic ingredients
- Beer garden setting, multiple spaces (brewpub + production taproom)
- Website on Squarespace — clean but limited
- **Advantage over Fatheads:** Better food story (chef-driven, seasonal), stronger neighborhood/walkability appeal
- **Where Fatheads wins:** Bigger beer operation, more awards, better online beer catalog/finder, stronger production and distribution story

### What competitors appear to do better:
- Better location/neighborhood identity (Great Lakes and Market Garden own "Ohio City")
- Potentially better local schema/search presence
- Simpler, faster-loading sites (especially Market Garden on Squarespace)
- Stronger food-forward positioning (Market Garden)

### What we can beat:
- Award story is unmatched (GABF Brewery of the Year, 35+ medals)
- Beer variety and beer finder tool
- Multi-location reach and catering capability
- Brand personality (fun, irreverent, memorable)
- Community involvement depth (Guardians, Monsters, Metroparks)

---

## 5. Conversion Notes

### Main CTA strength:
- Beer Finder is well-placed (nav, hero area, dedicated section)
- Location pages have clear visit information with hours
- Online store accessible from main nav
- Events section promotes engagement

### Main CTA weakness:
- **No single dominant CTA on the homepage** — it's a showcase with multiple competing actions
- Age gate creates immediate friction before any conversion path
- No "Order Online" or "Make a Reservation" CTA for the beer hall
- No phone number visible on the homepage without clicking to a location page
- Beer Finder is the strongest CTA but it drives off-site retail, not visits to the beer hall

### Trust-flow issues:
- Awards are buried in a carousel slide rather than prominently featured
- "GABF Brewery of the Year" should be a persistent badge/element, not a rotating promo
- No visible review count or rating from Google/Yelp
- No press logos or "As Seen In" section

### Mobile conversion issues:
- Long homepage requires extensive scrolling
- Multiple carousels compete for attention
- Age gate on mobile is an extra tap before anything
- No sticky CTA or quick-action bar on mobile

### Friction points:
- Age gate on every visit (unless cached)
- No clear "what should I do next" hierarchy
- Location hours change (e.g., "Closed Hoppy Easter" shown) but no clear indication of regular hours vs. exceptions
- Careers link goes to Indeed.com — takes users off-site

---

## 6. Weakness List

1. **Age gate page title ("Age Verification - Fat Heads Brewery") is what Google sees** — major SEO issue
2. **No LocalBusiness, Restaurant, or Organization structured data** — only Breadcrumbs
3. **No city/service keywords in homepage title or H1** — weak local search targeting
4. **Lab mobile performance is extremely poor** (40.5s LCP) even though CrUX passes
5. **Homepage lacks a clear primary CTA** — multiple competing actions with no hierarchy
6. **Awards and trust signals are hidden in carousels** instead of being persistent
7. **Viewport disables pinch-to-zoom** — accessibility violation
8. **No reservation, online ordering, or direct phone CTA** on the homepage
9. **No structured data for menu, events, or beer products**
10. **Heavy JavaScript and carousel bloat** on homepage
11. **No embedded map or explicit location prominence** for the flagship

---

## 7. Opportunity List

1. **Fix the age gate SEO issue** — ensure the real page title/content is what Google indexes, not the age verification overlay
2. **Add comprehensive structured data** — LocalBusiness, Restaurant, Menu, Event, Organization, Product (for beers)
3. **Add city and service keywords** to homepage title, H1, and meta description
4. **Make "GABF Brewery of the Year" a persistent trust badge** — not a carousel slide
5. **Add a clear primary CTA** for the flagship location (Visit Us / Get Directions / View Menu)
6. **Improve mobile performance** — reduce carousel count, lazy-load images, reduce JS payload
7. **Add reservation/online ordering integration** if available
8. **Build city-specific landing pages** (e.g., "best brewery near Cleveland," "Middleburg Heights brewery")
9. **Add review/rating trust signals** from Google, Yelp, Untappd
10. **Fix viewport zoom restriction** for accessibility compliance
11. **Strengthen the beer catalog as the hero experience** — since the user says this is the core value proposition

---

## 8. Strategy for Sample Site

### What the sample must fix first:
- Clean, SEO-safe page title that reflects the business (not age verification)
- Prominent location details and local signals for flagship
- Clear CTA hierarchy: explore beers → visit the beer hall → find our beer near you
- Persistent award/trust badges (GABF Brewery of the Year front and center)
- Proper structured data foundation

### What should remain familiar:
- Brand personality and tone ("Chill out man, have a beer!")
- Dark/bold visual identity
- Beer-forward content hierarchy
- Floating beer can visual treatment (user specifically requested this)
- Fun, irreverent copy style
- Navigation structure (Beer, Visit, About, Outreach, Shop)

### What should look stronger immediately:
- Beer showcase as the hero experience (catalog feel, floating cans)
- Award credentials prominently displayed
- Clear "Visit the Beer Hall" CTA for Middleburg Heights
- Faster, cleaner loading experience
- Mobile experience without excessive carousels
- Location prominence with map/directions

### Local SEO improvements to show:
- City name in title and H1
- LocalBusiness structured data
- Embedded location context
- Service area signals

### Conversion improvements to show:
- Clear CTA hierarchy
- Persistent trust badges
- Phone/directions accessible without extra clicks
- Streamlined mobile flow

---

## 9. Strategy for Sales Report

### Which issues are easiest to show visually:
- Age gate title tag issue (screenshot the Rich Results test showing "Age Verification" as the page title)
- Missing structured data (show the 1 valid item vs. what should be there)
- Carousel-buried awards vs. prominent placement
- Side-by-side mobile experience comparison

### Which issues matter most to the owner:
- Google may not be properly seeing/indexing their homepage content
- Their biggest achievement (GABF Brewery of the Year) is hidden in a rotating banner
- Missing structured data means missed opportunities in search results
- No clear path for visitors to take action (visit, order, call)

### Which findings should stay internal:
- Exact Lighthouse lab scores (the CrUX pass is more relevant for the client conversation)
- Detailed competitor analysis specifics
- jQuery Migrate / technical dependency details
- Exact structured data implementation strategy
