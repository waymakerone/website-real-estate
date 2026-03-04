# Real Estate Agent Website — Product Requirements

**Status:** Approved
**Author:** Waymaker
**Date:** 2026-03-03

## Problem Statement

Real estate is a relationship business. Buyers and sellers don't choose an agency — they choose an agent. The agent they trust to understand their street, their market, and their goals. But on the major portal sites — realestate.com.au, Domain, Zillow, Realtor.com — every agent looks the same. Same layout, same profile format, same tiny headshot in a sidebar. The portals are designed to showcase properties, not agents.

A personal website changes the dynamic. It positions the agent as a local expert with a track record, not just a name attached to a listing. It showcases sold properties (social proof), highlights specialist areas (local knowledge), and captures seller leads through free appraisal forms — the single highest-value conversion in real estate marketing. A homeowner requesting a free appraisal is signalling they're considering selling. That form submission is worth more than any other lead source.

Without a personal website, agents are commoditised. They compete on the portal's terms, where the property is the hero and the agent is interchangeable. A dedicated site flips this — the agent is the hero, the properties are the proof, and the appraisal form is the conversion engine. In a market where the top 20% of agents do 80% of the business, a professional web presence is what separates the 20% from the rest.

## Goals

1. Establish the agent as a local expert — not just another name on a portal listing
2. Showcase current and sold properties — the track record is the proof
3. Capture seller leads — free appraisal form as the primary conversion mechanism
4. Build trust before the first meeting — testimonials, experience, and area knowledge
5. Rank locally — appear in search results for "[suburb] real estate agent"

## Non-Goals

- This is NOT a property search engine — no advanced filters, saved searches, or map-based search
- This is NOT a listing management system — listings are manually curated, not synced from a CRM
- This is NOT a portal replacement — properties still live on realestate.com.au/Domain/Zillow, the site links to them
- This is NOT a transaction platform — no offers, contracts, or document signing

## Sections

### Hero + Search

**Purpose:** Establish the agent's brand immediately. The visitor should know who this agent is, what market they serve, and see a stunning property image that demonstrates the calibre of listings they handle. A clear CTA drives the visitor deeper — either to view listings or to request an appraisal.

**Content Questions:**
- What is your name and agency name?
- What is your market or specialty? (e.g. "Residential sales in Sydney's Eastern Suburbs" or "Luxury homes in Scottsdale")
- What areas or suburbs do you cover?
- Do you have a hero-quality property image? (wide, high-resolution, aspirational)

**Design Notes:** Full-width property hero image — the best listing photo available. Agent name and tagline overlaid with good contrast (dark gradient overlay on the image). A primary CTA: "View Current Listings" or "Get a Free Appraisal." The search bar is optional — if included, it should be simple (suburb or address search that filters the listings section). Navigation should be clean: Listings, About, Areas, Testimonials, Contact.

---

### Featured Listings

**Purpose:** Current properties on the market. This is the agent's shop window — the listings they're actively marketing. Each property card should look polished and link to the full listing on the relevant portal.

**Content Questions:**
- What properties are currently listed? (3-6 is ideal for a personal site)
- For each: address, price or price guide, number of bedrooms, bathrooms, and car spaces, and a hero photo
- Where is the full listing? (link to realestate.com.au, Domain, Zillow, etc.)

**Design Notes:** Property cards in a grid — 2-3 columns on desktop, 1 on mobile. Each card shows: hero image, price (or price guide), address, and bed/bath/car icons with counts. Consistent card sizing for a clean grid. Each card links to the external listing page. If the agent has sold properties they want to highlight, a "Recently Sold" sub-section with the same card format (with "SOLD" badge) adds social proof.

---

### Agent Profile

**Purpose:** Build personal trust. In real estate, people hire people. The agent profile section humanises the brand — it's the "Why me?" section. Experience, specialisations, sales volume, and a professional headshot combine to say "I know this market and I'll look after you."

**Content Questions:**
- What is your professional background and experience? (years in real estate, career highlights)
- What are your specialisations? (residential, commercial, luxury, first home buyers, downsizers)
- How many properties have you sold or managed?
- What suburbs or areas are you an expert in?
- Do you have a professional headshot?
- What is your real estate licence number? (required in most jurisdictions)

**Design Notes:** Large professional headshot alongside a bio. Keep the text concise — 2-3 short paragraphs max. Key stats displayed prominently: "15+ years experience", "200+ properties sold", "$150M+ in sales." Licence number displayed for compliance. Awards or industry recognition as badges or a simple list. The headshot should be professional — suit or smart casual, well-lit, approachable.

---

### Areas of Expertise

**Purpose:** Demonstrate local knowledge. Buyers and sellers want an agent who knows their specific suburb — the streets, the schools, the market trends. This section positions the agent as the go-to expert for specific areas, and also serves local SEO by creating content around suburb names.

**Content Questions:**
- What suburbs or areas do you specialise in? (3-6 areas)
- Can you provide a brief description of each area? (what makes it desirable, market trends, lifestyle)
- Do you have area-specific photography? (streetscapes, landmarks, lifestyle shots)

**Design Notes:** Area cards in a grid — each card features an area photo, the suburb name, and a 2-3 sentence description. Cards can link to a filtered view of listings in that area, or to external portal search results. The photography should be aspirational — tree-lined streets, harbour views, buzzing cafe strips — whatever makes the area desirable.

---

### Testimonials

**Purpose:** Social proof from real clients. In real estate, vendor and buyer reviews carry enormous weight — a glowing testimonial from a local seller is more persuasive than any marketing copy. This section lets happy clients sell on the agent's behalf.

**Content Questions:**
- Do you have client testimonials? (3-5 is ideal)
- For each: the quote, the client's name, and their suburb (e.g. "Sarah M., Paddington")
- Do you have a Google Reviews or RateMyAgent profile? (link to it for credibility)

**Design Notes:** Quote cards with the testimonial text, client name, and suburb. Star ratings if available. A link to the agent's Google Reviews or RateMyAgent profile for visitors who want to read more. Display 3-5 testimonials — enough for credibility without overwhelming. Rotate or carousel on mobile if space is tight.

---

### Free Appraisal / Valuation Form

**Purpose:** Lead generation. This is the most valuable conversion on the entire site. A homeowner who fills out a free appraisal form is signalling intent to sell — they want to know what their property is worth. This form captures their details and starts the relationship.

**Content Questions:**
- Do you offer free property appraisals or market valuations?
- What information do you need from the homeowner? (property address, property type, number of bedrooms, name, phone number, email — minimum)
- What CTA phrase do you prefer? (e.g. "Get Your Free Appraisal", "What's My Home Worth?", "Request a Market Update")

**Design Notes:** Prominent CTA section — full-width with an accent background colour (gold, emerald, or the agent's brand colour) to visually separate it from the rest of the page. Strong headline: "What's Your Property Worth?" or "Get a Free Market Appraisal." A simple form: property address, property type (dropdown: House, Unit, Townhouse, Land), bedrooms (dropdown: 1-5+), name, phone, email. The submit button should be large and action-oriented: "Request My Free Appraisal." This section should also appear as a CTA banner earlier on the page (e.g. between Listings and Agent Profile) to capture visitors who don't scroll to the bottom.

## Design Specification

| Token | Value |
|-------|-------|
| Colour Palette | Sophisticated — charcoal or navy primary, white background, gold or emerald accent for CTAs. Property photos provide the visual richness. |
| Typography | Elegant sans-serif (e.g. DM Sans, Outfit). Property addresses in a slightly condensed style. Large price displays. |
| Mood | Aspirational, trustworthy, local expertise. The site should feel premium regardless of the market segment. |
| Layout | Property cards in a grid. Full-width hero. Agent profile as a featured section. Clean, uncluttered — let the properties shine. |

## Content Requirements

What the user must provide:

- Agent name and agency name
- Market specialty or tagline
- Areas/suburbs covered
- Hero property image (wide, high-resolution)
- 3-6 current listings, each with: address, price/price guide, bedrooms, bathrooms, car spaces, hero photo, and link to external listing
- Professional headshot
- Bio text (2-3 paragraphs covering experience, specialisations, achievements)
- Key stats: years of experience, properties sold, total sales volume
- Real estate licence number
- 3-6 specialist suburbs/areas with descriptions and area photography
- 3-5 client testimonials with name and suburb
- Google Reviews or RateMyAgent profile URL (if available)
- Appraisal form CTA phrase
- Contact details: phone, email, office address

## Technical Requirements

- Single-page layout with smooth scroll navigation
- Semantic HTML: `nav`, `main`, `section`, `footer`
- Mobile-first responsive design (375px → 768px → 1024px+)
- Performance: compressed images, lazy loading, minimal JS
- Accessibility: proper heading hierarchy, alt text, colour contrast (WCAG AA)
- SEO: meta title + description, Open Graph tags, semantic markup
- Property cards with bed/bath/car icons — consistent iconography across all listings
- Links to external listing platforms (realestate.com.au, Domain, Zillow) — open in new tab
- Appraisal form with fields: property address (text), property type (dropdown), bedrooms (dropdown), name (text), phone (tel), email (email) — form submits via `mailto:` link or Formspree/Netlify Forms
- `RealEstateAgent` structured data (schema.org) for agent SEO — includes name, area served, description, image
- `RealEstateListing` structured data for featured properties (if applicable)
- `tel:` links for phone numbers, `mailto:` for email
- Map embed or link to office location
- Area pages with suburb names in headings for local SEO ("Real Estate Agent in [Suburb]")

## Success Criteria

| Metric | Target |
|--------|--------|
| Mobile responsive | Works on 375px+ screens |
| Page load | < 3 seconds on 3G |
| Accessibility | WCAG AA compliant |
| SEO ready | Meta tags, semantic HTML, RealEstateAgent structured data |
| Build time (with AI) | < 30 minutes |
| Appraisal form | Functional, submits all fields, confirmation shown |
| Property cards | Bed/bath/car icons render correctly, links work |
| Local SEO | Suburb names appear in headings and meta description |
