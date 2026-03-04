# Real Estate

A property-focused website for real estate agents, agencies, and property managers.

## Build Method

This blueprint supports two build paths:

| Path | Tool | How |
|------|------|-----|
| **IDE** | Claude Code, Cursor, Codex | Clone the template, follow the build prompt, deploy via `waymaker push` or Host |
| **Conversational** | Claude Desktop, Host Direct | Describe your business, AI builds + deploys via MCP `host_app_upload` |

Both paths produce the same output. The build prompt detects your environment and guides you accordingly.

## Documentation

| Folder | Contents |
|--------|----------|
| `docs/01-planning/product-requirements/` | PRD — sections, design spec, content requirements |
| `docs/02-working/prompts/active/` | Build prompt with YAML front matter |
| `docs/02-working/sessions/` | Session briefs as you build |
| `docs/03-knowledge/` | Patterns discovered during the build |

## Build Phases

| Phase | Prompt | Status |
|-------|--------|--------|
| 1 — Build Website | `docs/02-working/prompts/active/phase-1-build-website.md` | todo |

## Sections Quick Reference

| ID | Name | Purpose |
|----|------|---------|
| hero | Hero + Search | Agency brand with property search or featured listing |
| listings | Featured Listings | Current properties with photos, prices, and bed/bath/car |
| agent | Agent Profile | Experience, stats, headshot, and licence number |
| areas | Areas of Expertise | Suburbs and regions with local knowledge |
| testimonials | Testimonials | Vendor and buyer reviews and ratings |
| valuation | Free Appraisal/Valuation Form | Lead generation form for property appraisals |

## Design Tokens

| Token | Value |
|-------|-------|
| Primary | Charcoal or navy |
| Background | White |
| Accent | Gold or emerald |
| Headings | DM Sans / Outfit |
| Body | DM Sans / Outfit |
| Mood | Aspirational, trustworthy, local expertise |

## Critical Rules

- Mobile-first responsive design
- Semantic HTML (`nav`, `main`, `section`, `footer`)
- Performance: compress images, lazy load, minimal JS
- Accessibility: proper heading hierarchy, alt text, colour contrast
- SEO: meta tags, structured data, semantic markup
- Single-page layout with smooth scroll navigation
- Property cards with bed/bath/car icons are standard
- Agent headshot must be prominent and professional
- Appraisal form is the primary lead generation tool

## How to Build

1. Read the PRD: `docs/01-planning/product-requirements/website-real-estate-prd.md`
2. Open the build prompt: `docs/02-working/prompts/active/phase-1-build-website.md`
3. Follow the instructions for your build path (IDE or Conversational)
4. Update the YAML `status` field as you go: `todo` -> `in-progress` -> `review` -> `done`

## Quick Reference

| What | How |
|------|-----|
| Dev server | Open `index.html` in browser (IDE path) |
| Deploy | `waymaker push` or MCP `host_app_upload` |
| Design spec | See PRD — Design Specification section |
| Content needed | See PRD — Content Requirements section |
