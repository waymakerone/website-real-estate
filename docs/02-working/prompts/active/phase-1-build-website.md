---
sync:
  type: doc
  layer: Website — Real Estate
build:
  status: todo
  phase: 1
  priority: P0
  depends_on: []
  started_at: null
  completed_at: null
---

# Phase 1: Build Real Estate Website

**Goal:** A complete, deployed real estate agent website with all sections — hero + search, featured listings, agent profile, areas of expertise, testimonials, free appraisal/valuation form. Mobile-first, semantic HTML, performance-optimised.

**PRD Reference:** `docs/01-planning/product-requirements/website-real-estate-prd.md`

---

## Build Path Detection

Detect your environment:

- **IDE Path** (Claude Code, Cursor, Codex) — you have filesystem access, can create files, run dev servers
- **Conversational Path** (Claude Desktop, Host Direct) — you have MCP tools, build in conversation, deploy via `host_app_upload`

Both paths produce the same output — a deployed website. Follow the instructions for your environment below.

---

## IDE Path

### 1. Project Setup

Create a single-page website project:

```
website-real-estate/
├── index.html
├── styles.css
├── script.js
└── assets/
    ├── listings/          # Property photos (optimised WebP/JPG)
    ├── areas/             # Suburb/area lifestyle photos
    ├── headshot.jpg       # Agent portrait (professional)
    └── favicon.svg
```

### 2. HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="[Agent Name] — [Market Focus] real estate agent in [Areas]. Browse listings, get a free appraisal, and find your next property.">
  <title>[Agent Name] — [Market Focus] Real Estate | [Primary Area]</title>
  <link rel="icon" href="assets/favicon.svg" type="image/svg+xml">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="styles.css">

  <!-- Structured Data: RealEstateAgent -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "RealEstateAgent",
    "name": "[Agent Name or Agency Name]",
    "description": "[Brief description of the agent/agency and services]",
    "url": "[Website URL]",
    "telephone": "[Phone Number]",
    "email": "[Email Address]",
    "image": "[Headshot URL]",
    "address": {
      "@type": "PostalAddress",
      "addressLocality": "[City]",
      "addressRegion": "[State]",
      "addressCountry": "[Country]"
    },
    "areaServed": [
      {
        "@type": "City",
        "name": "[Suburb/Area 1]"
      },
      {
        "@type": "City",
        "name": "[Suburb/Area 2]"
      }
    ],
    "sameAs": [
      "https://realestate.com.au/agent/[profile]",
      "https://domain.com.au/agent/[profile]",
      "https://linkedin.com/in/[handle]"
    ]
  }
  </script>
</head>
<body>
  <nav id="navbar"><!-- Sticky nav with agent name + CTA --></nav>
  <main>
    <section id="hero"><!-- Hero image, headline, CTA --></section>
    <section id="listings"><!-- Featured property cards --></section>
    <section id="about"><!-- Agent profile, stats, credentials --></section>
    <section id="areas"><!-- Areas of expertise --></section>
    <section id="testimonials"><!-- Client testimonials --></section>
    <section id="appraisal"><!-- Free appraisal form --></section>
  </main>
  <footer><!-- Contact, licence, disclaimers --></footer>
  <script src="script.js"></script>
</body>
</html>
```

### 3. Build Sections

#### 3.1 Navigation

Clean, professional sticky nav. Agent name or agency brand on left, links + appraisal CTA on right.

```html
<nav id="navbar" class="navbar">
  <div class="nav-inner container">
    <a href="#hero" class="nav-logo">[Agent Name]</a>
    <button class="nav-toggle" aria-label="Toggle menu" aria-expanded="false">
      <span class="hamburger"></span>
    </button>
    <ul class="nav-links">
      <li><a href="#listings">Listings</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#areas">Areas</a></li>
      <li><a href="#testimonials">Testimonials</a></li>
      <li><a href="#appraisal" class="nav-cta btn btn-accent">Free Appraisal</a></li>
    </ul>
  </div>
</nav>
```

#### 3.2 Hero

Large hero image of a premium property or lifestyle shot. Confident headline.

```html
<section id="hero" class="hero">
  <div class="hero-bg" style="background-image: url('assets/listings/hero-property.jpg');">
    <div class="hero-overlay"></div>
  </div>
  <div class="container hero-content">
    <p class="hero-eyebrow">[Market Focus] Real Estate — [Primary Area]</p>
    <h1 class="hero-title">Your Property, Our Priority</h1>
    <p class="hero-subtitle">[One-line value proposition — e.g., "Helping families find their perfect home in [Area] for over [X] years."]</p>
    <div class="hero-ctas">
      <a href="#listings" class="btn btn-accent">View Listings</a>
      <a href="#appraisal" class="btn btn-outline-light">Get a Free Appraisal</a>
    </div>
  </div>
</section>
```

- Full viewport height with a background image and dark overlay for text readability.
- Two CTAs: primary (view listings) and secondary (free appraisal).

#### 3.3 Featured Listings

A grid of 3-6 property cards with key details.

```html
<section id="listings" class="listings">
  <div class="container">
    <h2 class="section-title">Featured Listings</h2>
    <p class="section-subtitle">Hand-picked properties currently on the market.</p>

    <div class="listing-grid">
      <article class="listing-card">
        <div class="listing-image">
          <img src="assets/listings/property-1.jpg" alt="[Address] — [Suburb]" loading="lazy">
          <span class="listing-status">For Sale</span>
        </div>
        <div class="listing-details">
          <h3 class="listing-price">$[Price or Price Guide]</h3>
          <p class="listing-address">[Street Address], [Suburb]</p>
          <div class="listing-features">
            <span class="feature">
              <svg class="feature-icon" viewBox="0 0 24 24" width="16" height="16" aria-hidden="true">
                <!-- Bed icon SVG path -->
              </svg>
              [X] Bed
            </span>
            <span class="feature">
              <svg class="feature-icon" viewBox="0 0 24 24" width="16" height="16" aria-hidden="true">
                <!-- Bath icon SVG path -->
              </svg>
              [X] Bath
            </span>
            <span class="feature">
              <svg class="feature-icon" viewBox="0 0 24 24" width="16" height="16" aria-hidden="true">
                <!-- Car icon SVG path -->
              </svg>
              [X] Car
            </span>
          </div>
          <a href="[Listing URL on realestate.com.au or Domain]" target="_blank" rel="noopener" class="listing-link">
            View Listing &rarr;
          </a>
        </div>
      </article>
      <!-- Repeat for each listing -->
    </div>

    <div class="listings-cta">
      <a href="[realestate.com.au agent profile or search URL]" target="_blank" rel="noopener" class="btn btn-outline">
        View All Listings
      </a>
    </div>
  </div>
</section>
```

- **Property cards**: Image at top, details below. Status badge ("For Sale", "Under Offer", "Sold") overlaid on the image.
- **Bed/Bath/Car icons**: Use simple inline SVGs. Display horizontally.
- **Price display**: Large, bold. Use guide format if applicable ("$1,200,000 - $1,300,000" or "Contact Agent").
- **Link**: Opens listing on realestate.com.au, Domain, or the agent's portal.
- Grid: 1 column mobile, 2 tablet, 3 desktop.

#### 3.4 Agent Profile

Two-column layout: professional headshot + credentials.

```html
<section id="about" class="about">
  <div class="container about-grid">
    <div class="about-image">
      <img src="assets/headshot.jpg" alt="[Agent Name]" loading="lazy">
    </div>
    <div class="about-content">
      <h2 class="section-title">About [First Name]</h2>
      <p class="about-bio">[2-3 paragraphs covering experience, approach, values, and track record.]</p>

      <!-- Agent Stats -->
      <div class="agent-stats">
        <div class="stat">
          <span class="stat-value">[X]+</span>
          <span class="stat-label">Years Experience</span>
        </div>
        <div class="stat">
          <span class="stat-value">[X]+</span>
          <span class="stat-label">Properties Sold</span>
        </div>
        <div class="stat">
          <span class="stat-value">$[X]M+</span>
          <span class="stat-label">Total Sales Value</span>
        </div>
      </div>

      <p class="about-licence">Licence No: [Licence Number]</p>

      <div class="about-platforms">
        <a href="[realestate.com.au profile URL]" target="_blank" rel="noopener" class="platform-link">
          View on realestate.com.au
        </a>
        <a href="[Domain profile URL]" target="_blank" rel="noopener" class="platform-link">
          View on Domain
        </a>
      </div>
    </div>
  </div>
</section>
```

- Stats displayed as large numbers with labels. Use accent colour for the numbers.
- Licence number shown for trust and compliance.
- Links to listing platforms for credibility.

#### 3.5 Areas of Expertise

Cards for each suburb or area the agent specialises in.

```html
<section id="areas" class="areas">
  <div class="container">
    <h2 class="section-title">Areas of Expertise</h2>
    <p class="section-subtitle">Deep local knowledge in [Region]'s most sought-after suburbs.</p>

    <div class="area-grid">
      <article class="area-card">
        <div class="area-image">
          <img src="assets/areas/suburb-1.jpg" alt="[Suburb Name] streetscape" loading="lazy">
        </div>
        <div class="area-content">
          <h3 class="area-name">[Suburb Name]</h3>
          <p class="area-desc">[2-3 sentences about the suburb — lifestyle, property types, median price, what makes it special.]</p>
        </div>
      </article>
      <!-- Repeat for each area -->
    </div>
  </div>
</section>
```

- Cards with a local photo (streetscape, park, cafe strip) and suburb description.
- Grid: 1 column mobile, 2 tablet, 3 desktop.
- Optional: overlay the suburb name on the image with a gradient.

#### 3.6 Testimonials

Client testimonials from both vendors (sellers) and buyers.

```html
<section id="testimonials" class="testimonials">
  <div class="container">
    <h2 class="section-title">What Clients Say</h2>

    <div class="testimonial-grid">
      <blockquote class="testimonial-card">
        <p class="testimonial-text">"[Testimonial text — 2-4 sentences about the experience.]"</p>
        <footer class="testimonial-author">
          <cite class="author-name">[Client Name]</cite>
          <span class="author-role">[Vendor / Buyer] — [Suburb]</span>
        </footer>
      </blockquote>
      <!-- Repeat for each testimonial -->
    </div>
  </div>
</section>
```

- Large quotation marks as a visual element (CSS `::before` pseudo-element with a decorative quote character in the accent colour).
- Label each testimonial as "Vendor" or "Buyer" so prospects can find relevant ones.
- Grid: 1 column mobile, 2 tablet, 3 desktop.

#### 3.7 Free Appraisal / Valuation Form

Lead capture form for property appraisals.

```html
<section id="appraisal" class="appraisal">
  <div class="container">
    <div class="appraisal-content">
      <h2 class="section-title">Get a Free Property Appraisal</h2>
      <p class="section-subtitle">Thinking of selling? Find out what your property is worth with a no-obligation market appraisal.</p>

      <form class="appraisal-form" id="appraisal-form" novalidate>
        <div class="form-group">
          <label for="appraisal-name">Full Name *</label>
          <input type="text" id="appraisal-name" name="name" required autocomplete="name">
          <span class="form-error" id="name-error" hidden>Please enter your name</span>
        </div>

        <div class="form-group">
          <label for="appraisal-email">Email *</label>
          <input type="email" id="appraisal-email" name="email" required autocomplete="email">
          <span class="form-error" id="email-error" hidden>Please enter a valid email</span>
        </div>

        <div class="form-group">
          <label for="appraisal-phone">Phone *</label>
          <input type="tel" id="appraisal-phone" name="phone" required autocomplete="tel">
          <span class="form-error" id="phone-error" hidden>Please enter your phone number</span>
        </div>

        <div class="form-group">
          <label for="appraisal-address">Property Address *</label>
          <input type="text" id="appraisal-address" name="address" required placeholder="e.g., 42 Smith Street, Richmond VIC 3121">
          <span class="form-error" id="address-error" hidden>Please enter the property address</span>
        </div>

        <div class="form-group">
          <label for="appraisal-type">Property Type</label>
          <select id="appraisal-type" name="property_type">
            <option value="">Select...</option>
            <option value="house">House</option>
            <option value="apartment">Apartment / Unit</option>
            <option value="townhouse">Townhouse</option>
            <option value="land">Land</option>
            <option value="commercial">Commercial</option>
          </select>
        </div>

        <div class="form-group">
          <label for="appraisal-bedrooms">Bedrooms</label>
          <select id="appraisal-bedrooms" name="bedrooms">
            <option value="">Select...</option>
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5+">5+</option>
          </select>
        </div>

        <div class="form-group">
          <label for="appraisal-message">Additional Notes</label>
          <textarea id="appraisal-message" name="message" rows="4" placeholder="Any details about your property or timeline..."></textarea>
        </div>

        <button type="submit" class="btn btn-accent btn-full btn-lg">Request Free Appraisal</button>

        <p class="form-disclaimer">Your details are kept confidential. No spam, ever.</p>
      </form>

      <!-- Success message (hidden by default) -->
      <div class="form-success" id="form-success" hidden>
        <h3>Thank You!</h3>
        <p>Your appraisal request has been received. [Agent Name] will be in touch within 24 hours.</p>
      </div>
    </div>
  </div>
</section>
```

- Client-side validation with clear error messages.
- On submit, show the success message and hide the form (in a real deployment, this would POST to an endpoint — for now, handle client-side only).
- Fields: Name, Email, Phone, Property Address, Property Type (dropdown), Bedrooms (dropdown), Message (optional).
- Privacy disclaimer below the button.

#### 3.8 Footer

```html
<footer class="footer">
  <div class="container footer-inner">
    <div class="footer-brand">
      <p class="footer-name">[Agent Name]</p>
      <p class="footer-agency">[Agency Name]</p>
      <p class="footer-licence">Licence No: [Number]</p>
    </div>
    <div class="footer-contact">
      <a href="tel:[phone]">[Phone Number]</a>
      <a href="mailto:[email]">[Email Address]</a>
    </div>
    <div class="footer-links">
      <a href="[realestate.com.au]" target="_blank" rel="noopener">realestate.com.au</a>
      <a href="[Domain]" target="_blank" rel="noopener">Domain</a>
      <a href="[LinkedIn]" target="_blank" rel="noopener">LinkedIn</a>
    </div>
    <p class="footer-disclaimer">Information provided is believed to be accurate but is not guaranteed. Prospective buyers should make their own enquiries.</p>
    <p class="footer-copy">&copy; [Year] [Agent Name]. All rights reserved.</p>
  </div>
</footer>
```

### 4. CSS Architecture

Mobile-first with breakpoints at 768px and 1024px.

```css
/* ============================================
   Design Tokens
   ============================================ */
:root {
  /* Colours */
  --color-primary: #1e293b;       /* Charcoal / Navy */
  --color-background: #ffffff;
  --color-surface: #f8fafc;
  --color-text: #1e293b;
  --color-text-muted: #64748b;
  --color-accent: #b8860b;        /* Gold (default) — or user's choice */
  --color-accent-hover: #996f09;
  --color-accent-light: rgba(184, 134, 11, 0.1);
  --color-border: #e2e8f0;
  --color-error: #ef4444;
  --color-success: #22c55e;

  /* Typography */
  --font-heading: 'DM Sans', sans-serif;
  --font-body: 'DM Sans', sans-serif;

  /* Spacing */
  --space-xs: 0.5rem;
  --space-sm: 1rem;
  --space-md: 2rem;
  --space-lg: 4rem;
  --space-xl: 6rem;
  --space-section: 8rem;

  /* Sizing */
  --container-max: 1200px;
  --nav-height: 64px;
  --border-radius: 8px;
  --border-radius-lg: 12px;

  /* Transitions */
  --transition-fast: 150ms ease;
  --transition-base: 300ms ease;
}

/* ============================================
   Reset & Base
   ============================================ */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; scroll-padding-top: var(--nav-height); }
body {
  font-family: var(--font-body);
  color: var(--color-text);
  background: var(--color-background);
  line-height: 1.7;
  -webkit-font-smoothing: antialiased;
}
img { max-width: 100%; height: auto; display: block; }
a { color: inherit; text-decoration: none; }
ul { list-style: none; }

.container {
  max-width: var(--container-max);
  margin: 0 auto;
  padding: 0 var(--space-sm);
}
@media (min-width: 768px) { .container { padding: 0 var(--space-md); } }

/* ============================================
   Key Patterns
   ============================================ */

section { padding: var(--space-xl) 0; }
@media (min-width: 768px) { section { padding: var(--space-section) 0; } }

.section-title {
  font-family: var(--font-heading);
  font-size: clamp(1.75rem, 3.5vw, 2.5rem);
  font-weight: 700;
  text-align: center;
  margin-bottom: var(--space-xs);
}
.section-subtitle {
  text-align: center;
  color: var(--color-text-muted);
  margin-bottom: var(--space-lg);
  max-width: 600px;
  margin-left: auto; margin-right: auto;
}

/* Hero */
.hero {
  min-height: 100vh; position: relative;
  display: flex; align-items: center;
  color: #fff;
}
.hero-bg {
  position: absolute; inset: 0;
  background-size: cover; background-position: center;
}
.hero-overlay {
  position: absolute; inset: 0;
  background: linear-gradient(to bottom, rgba(0,0,0,0.5), rgba(0,0,0,0.7));
}
.hero-content { position: relative; z-index: 1; }
.hero-title {
  font-size: clamp(2rem, 5vw, 4rem);
  font-weight: 700; line-height: 1.1;
  margin-bottom: var(--space-sm);
}

/* Listing cards */
.listing-grid {
  display: grid; grid-template-columns: 1fr; gap: var(--space-md);
}
@media (min-width: 768px) { .listing-grid { grid-template-columns: repeat(2, 1fr); } }
@media (min-width: 1024px) { .listing-grid { grid-template-columns: repeat(3, 1fr); } }

.listing-card {
  background: var(--color-background);
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius-lg);
  overflow: hidden;
  transition: box-shadow var(--transition-base);
}
.listing-card:hover {
  box-shadow: 0 8px 30px rgba(0,0,0,0.08);
}
.listing-image { position: relative; aspect-ratio: 4/3; overflow: hidden; }
.listing-image img { width: 100%; height: 100%; object-fit: cover; }
.listing-status {
  position: absolute; top: 12px; left: 12px;
  background: var(--color-accent); color: #fff;
  padding: 4px 12px; border-radius: 4px;
  font-size: 0.75rem; font-weight: 700; text-transform: uppercase;
}
.listing-details { padding: var(--space-sm); }
.listing-price {
  font-size: 1.5rem; font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 4px;
}
.listing-address {
  color: var(--color-text-muted);
  margin-bottom: var(--space-xs);
}
.listing-features {
  display: flex; gap: var(--space-sm);
  margin-bottom: var(--space-xs);
  font-size: 0.9rem;
  color: var(--color-text-muted);
}
.feature { display: flex; align-items: center; gap: 4px; }
.feature-icon { fill: currentColor; }
.listing-link {
  color: var(--color-accent); font-weight: 500;
  display: inline-block; margin-top: var(--space-xs);
}
.listing-link:hover { text-decoration: underline; }

/* Agent stats */
.agent-stats {
  display: flex; gap: var(--space-md);
  margin: var(--space-md) 0;
  flex-wrap: wrap;
}
.stat { text-align: center; }
.stat-value {
  display: block;
  font-size: 2rem; font-weight: 700;
  color: var(--color-accent);
}
.stat-label {
  font-size: 0.85rem;
  color: var(--color-text-muted);
}

/* About grid */
.about-grid {
  display: grid; grid-template-columns: 1fr; gap: var(--space-lg);
}
@media (min-width: 768px) {
  .about-grid { grid-template-columns: 1fr 1.5fr; align-items: start; }
}
.about-image img {
  border-radius: var(--border-radius-lg);
  width: 100%;
}

/* Area cards */
.area-grid {
  display: grid; grid-template-columns: 1fr; gap: var(--space-md);
}
@media (min-width: 768px) { .area-grid { grid-template-columns: repeat(2, 1fr); } }
@media (min-width: 1024px) { .area-grid { grid-template-columns: repeat(3, 1fr); } }

.area-card {
  border-radius: var(--border-radius-lg);
  overflow: hidden;
  border: 1px solid var(--color-border);
}
.area-image { aspect-ratio: 16/9; overflow: hidden; }
.area-image img { width: 100%; height: 100%; object-fit: cover; }
.area-content { padding: var(--space-sm); }
.area-name { font-size: 1.25rem; font-weight: 700; margin-bottom: 0.5rem; }

/* Testimonials */
.testimonial-grid {
  display: grid; grid-template-columns: 1fr; gap: var(--space-md);
}
@media (min-width: 768px) { .testimonial-grid { grid-template-columns: repeat(2, 1fr); } }
@media (min-width: 1024px) { .testimonial-grid { grid-template-columns: repeat(3, 1fr); } }

.testimonial-card {
  background: var(--color-surface);
  border-radius: var(--border-radius-lg);
  padding: var(--space-md);
  position: relative;
}
.testimonial-card::before {
  content: "\201C";
  font-size: 4rem; line-height: 1;
  color: var(--color-accent);
  opacity: 0.3;
  position: absolute; top: 12px; left: 16px;
}
.testimonial-text {
  font-style: italic;
  margin-bottom: var(--space-sm);
  position: relative; z-index: 1;
}
.author-name { display: block; font-weight: 700; font-style: normal; }
.author-role { font-size: 0.85rem; color: var(--color-text-muted); }

/* Appraisal form */
.appraisal {
  background: var(--color-surface);
}
.appraisal-content {
  max-width: 640px;
  margin: 0 auto;
}
.form-group {
  margin-bottom: var(--space-sm);
}
.form-group label {
  display: block;
  font-weight: 500;
  margin-bottom: 4px;
  font-size: 0.9rem;
}
.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius);
  font-family: var(--font-body);
  font-size: 1rem;
  background: var(--color-background);
  transition: border-color var(--transition-fast);
}
.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--color-accent);
  box-shadow: 0 0 0 3px var(--color-accent-light);
}
.form-group.error input,
.form-group.error select {
  border-color: var(--color-error);
}
.form-error {
  color: var(--color-error);
  font-size: 0.8rem;
  margin-top: 4px;
}
.form-disclaimer {
  text-align: center;
  font-size: 0.8rem;
  color: var(--color-text-muted);
  margin-top: var(--space-sm);
}

/* Buttons */
.btn {
  display: inline-block;
  padding: 12px 28px;
  border-radius: var(--border-radius);
  font-family: var(--font-body);
  font-weight: 600;
  text-align: center;
  cursor: pointer;
  transition: all var(--transition-fast);
  border: none;
}
.btn-accent { background: var(--color-accent); color: #fff; }
.btn-accent:hover { background: var(--color-accent-hover); }
.btn-outline {
  background: transparent;
  border: 1px solid var(--color-border);
  color: var(--color-text);
}
.btn-outline:hover { border-color: var(--color-accent); color: var(--color-accent); }
.btn-outline-light {
  background: transparent;
  border: 1px solid rgba(255,255,255,0.5);
  color: #fff;
}
.btn-outline-light:hover { background: rgba(255,255,255,0.1); border-color: #fff; }
.btn-full { width: 100%; }
.btn-lg { padding: 16px 36px; font-size: 1.05rem; }
```

### 5. JavaScript (script.js)

Implement the following in vanilla JS (no frameworks):

1. **Smooth scroll** — CSS handles `scroll-behavior: smooth`. Add JS to offset anchor clicks by the sticky nav height.

2. **Mobile menu toggle** — Toggle `nav-open` class on body. Update `aria-expanded`. Close on link click.

3. **Navbar scroll effect** — Add `scrolled` class to `#navbar` when `scrollY > 50`. Transparent on hero, solid background after scrolling.

4. **Form validation** — On `#appraisal-form` submit:
   - Prevent default.
   - Validate required fields (name, email, phone, address). Check email format with a simple regex.
   - If invalid, show error messages (`.form-error`) and add `.error` class to the form group. Focus the first invalid field.
   - If valid, hide the form and show `#form-success`. In a production deployment, this would POST to an API endpoint.

5. **Scroll reveal** — Use `IntersectionObserver` to add `.revealed` class to sections and cards as they enter the viewport.

### 6. Deploy

```bash
# Via Waymaker CLI
cd website-real-estate
waymaker push

# Or via MCP tool
# Use host_app_upload with all files
```

---

## Conversational Path

### Step 1: Gather Business Details

Ask these questions in order. Move to the next question after each answer. Do not skip any.

**Essential (must have before building):**

1. What is your name or agency name?
2. What is your market focus? (Residential, commercial, luxury, rural, etc.)
3. What areas (suburbs/regions) do you cover?

**Content (ask after essentials):**

4. Please share your current featured listings (3-6). For each, I need: property address, price or price guide, number of bedrooms/bathrooms/car spaces, a photo, and the listing URL (realestate.com.au or Domain link).
5. Tell me about your experience — years in the industry, number of properties sold, total sales value, and any achievements.
6. What is your real estate licence number?
7. For each area you specialise in, give me a 2-3 sentence description of the area — lifestyle, property types, what makes it special. Include a photo if you have one.
8. Please share 3-6 client testimonials. For each: the quote, the client's name (or initials), and whether they were a vendor (seller) or buyer.
9. What is your headshot photo? (Professional portrait.)
10. What are your contact details? (Phone, email.)
11. Do you have profiles on realestate.com.au and/or Domain? Please share the URLs.
12. Do you prefer gold or emerald as your accent colour? Or suggest another.

### Step 2: Build the Website

Once you have the answers:

1. **Populate listings**: Build property cards with real data — prices, addresses, bed/bath/car counts, photos, and listing URLs.
2. **Build index.html**: Create the full HTML with all sections. Fill in agent bio, stats, areas, testimonials, and the appraisal form.
3. **Build styles.css**: Use the complete CSS architecture from the IDE path above. Set the accent colour token.
4. **Build script.js**: Include mobile menu, scroll effects, and form validation.
5. **Populate structured data**: Fill in the RealEstateAgent schema with real details.
6. **Handle images**: Reference property and headshot images by URL or include files.

### Step 3: Deploy

Deploy using the `host_app_upload` MCP tool:

```
Use host_app_upload with:
- files: [index.html, styles.css, script.js, plus any asset files]
- app_name: "[agent-name]-realestate" or custom slug
```

Confirm the live URL with the user. Walk through each section — verify all listings display correctly with accurate prices and details, testimonials are attributed correctly, and the appraisal form validates properly.

---

## Design Tokens

| Token | Value |
|-------|-------|
| Primary | `#1e293b` (charcoal / navy) |
| Background | `#ffffff` |
| Surface | `#f8fafc` |
| Text | `#1e293b` |
| Text Muted | `#64748b` |
| Accent | User's choice (default: `#b8860b` gold, alt: `#059669` emerald) |
| Border | `#e2e8f0` |
| Error | `#ef4444` |
| Success | `#22c55e` |
| Headings Font | DM Sans (alt: Outfit) — elegant, professional |
| Body Font | DM Sans |
| Prices | DM Sans, large display weight (`font-size: 1.5rem; font-weight: 700`) |

## Technical Requirements

- **Performance**: All property and area images lazy-loaded. Font loaded with `display=swap`. No render-blocking JS. Target < 2s LCP.
- **Accessibility**: Form fields have labels. Error messages linked to fields. Focus management on form errors. Colour contrast >= 4.5:1. Bed/bath/car icons have `aria-hidden="true"` with text labels.
- **SEO**: Semantic HTML5. RealEstateAgent structured data. Meta description includes agent name, market focus, and area. Property addresses in text (not just images) for search indexing.
- **Responsive**: Mobile-first. Three breakpoints: base, 768px, 1024px. Property cards stack single-column on mobile. Form is full-width.
- **Lead capture**: Form validates client-side. In production, would POST to an API. Success message displays on valid submission. No spam — honeypot field can be added optionally.
- **No dependencies**: Vanilla HTML, CSS, JS only.

## Acceptance Criteria

- [ ] Hero displays agent name, market focus, value proposition, and two CTAs (View Listings + Free Appraisal).
- [ ] Featured listings display 3-6 property cards with photo, price, address, bed/bath/car icons, and status badge.
- [ ] Each listing links to the property on realestate.com.au or Domain.
- [ ] Agent profile shows headshot, bio, experience stats (years, properties sold, sales value), and licence number.
- [ ] Areas of expertise displays suburb cards with photos and descriptions.
- [ ] Testimonials section shows client quotes attributed with name and role (Vendor/Buyer).
- [ ] Appraisal form validates all required fields. Shows inline error messages for invalid inputs. Shows success message on valid submission.
- [ ] Navigation is sticky, links highlight on scroll, mobile menu toggles correctly.
- [ ] Structured data (RealEstateAgent schema) is valid — test at https://validator.schema.org/.
- [ ] Page scores 90+ on Lighthouse for Performance, Accessibility, Best Practices, and SEO.
- [ ] No console errors. No broken images. No layout shifts.

## Complexity Advisory

Both build paths work well for website blueprints. Websites are single-phase builds with straightforward HTML/CSS — conversational and IDE paths produce equivalent results.
