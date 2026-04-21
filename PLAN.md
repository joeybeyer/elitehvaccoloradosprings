# PLAN.md — Colorado Springs Elite HVAC Rebuild

## Pre-Build Gate (§1 — SITE-BUILD-2026.md)

| Decision | Value |
|----------|-------|
| **Brand name** | Colorado Springs Elite HVAC |
| **GBP match** | TBD — no GBP yet (create after site launch) |
| **Launch cities** | Colorado Springs, Monument, Fountain, Security-Widefield, Manitou Springs |
| **Stack** | Static HTML on AWS S3 (per Joey's decision) |
| **Repo** | joeybeyer/elitehvaccoloradosprings |
| **URL pattern** | /[emq]-[city]/ with trailing slash |
| **S3 bucket** | elitehvaccoloradosprings.com |
| **Domain** | elitehvaccoloradosprings.com |

## Money Keywords (15)

1. 24/7 hvac colorado springs co
2. emergency hvac colorado springs
3. hvac quotes colorado springs
4. affordable furnace repair colorado springs
5. licensed hvac contractor colorado springs
6. ac installation cost colorado springs
7. commercial hvac service colorado springs
8. furnace replacement cost colorado springs
9. best hvac company colorado springs
10. air conditioning service colorado springs
11. hvac installation colorado springs
12. hvac maintenance colorado springs
13. ac repair colorado springs co
14. furnace repair colorado springs
15. hvac colorado springs co

## City Pages to Build

| City | URL Slug | Pop. | Rationale |
|------|----------|------|-----------|
| Colorado Springs | /hvac-colorado-springs/ | 499K | Primary market |
| Monument | /hvac-monument/ | 15K | Fastest-growing suburb (+5.26%/yr) |
| Fountain | /hvac-fountain/ | 29K | 2nd largest suburb |
| Security-Widefield | /hvac-security-widefield/ | ~33K CDP | Large unincorporated area |
| Manitou Springs | /hvac-manitou-springs/ | 4.5K | Tourist town, unique HVAC needs |

## SOP Adaptations (S3 Static)

Since Joey chose S3 over Next.js + Turso + Cloudflare Pages:
- Each city page = `/[slug]/index.html` folder structure on S3
- Homepage = `/index.html` with Organization schema
- Schema is inline JSON-LD in each HTML file
- Tables are static HTML `<table>` elements
- FAQ is static `<h3>` + `<p>` pairs (no JS accordion)
- Sitemap.xml generated statically
- No dynamic routing — each page is a separate HTML file

## Page Structure Per City (§8 Template)

```
<h1>[EMQ exactly]</h1>
<p class="sidekick">Colorado Springs Elite HVAC — Official Service</p>

[Hero CTA with phone number]

<h2>[Service] in [City], Colorado</h2>
[2-3 paragraphs: neighborhoods, venues, local context]

<h2>[Service] Recommendations for [City] Homes</h2>
[RECOMMENDATION TABLE — unit size/town by home size]

<h2>[City] HVAC Pricing</h2>
[PRICING TABLE]

<h2>Neighborhoods We Serve in [City]</h2>
[Named neighborhoods with descriptions]

<h2>[City] HVAC Permit & Regulation Notes</h2>
[PPRBD requirements, local codes]

<h2>Frequently Asked Questions</h2>
[6+ H3+p Q&A pairs]

<h2>Schedule [Service] in [City]</h2>
[Closing CTA]

[LocalBusiness + FAQPage JSON-LD]
```

## Build Order

1. ✅ PLAN.md (this file)
2. 🔨 Homepage (Organization schema, title: "HVAC Colorado Springs CO | Official 24/7 Service 2026")
3. 🔨 Colorado Springs city page (/hvac-colorado-springs/)
4. 🔨 Monument city page (/hvac-monument/)
5. 🔨 Fountain city page (/hvac-fountain/)
6. 🔨 Security-Widefield city page (/hvac-security-widefield/)
7. 🔨 Manitou Springs city page (/hvac-manitou-springs/)
8. 🔨 Sitemap.xml + robots.txt
9. 🔨 Deploy all to S3
10. 🔨 Visual verification
11. 🔨 Create GBP for brand entity

## Key Local Data

### Pikes Peak Regional Building Department (PPRBD)
- Permit required for furnace install/replacement
- AFUE 90% minimum efficiency
- Mechanical permit: $50-150 residential
- Processing: 3-5 business days
- Permits expire after 6 months
- Fines up to $1,000 for non-compliance
- Online portal: pprbd.org

### Colorado Springs Neighborhoods
Briargate, Old Colorado City, Downtown, Broadmoor, Powers Corridor, Northgate, Cimarron Hills, Falcon, Northeast, Southeast, Westside, Cheyenne Mountain, Stetson Hills

### Venues/Landmarks
Garden of the Gods, Pikes Peak, US Olympic Training Center, The Broadmoor, Air Force Academy, Memorial Park, Acacia Park, Cheyenne Mountain Zoo, Red Rocks Open Space

### Monument Neighborhoods
Forest Lakes, Promontory Pointe, Jackson Creek, Bent Grass, Sanctuary Pointe

### Fountain Neighborhoods
Countryside, Heritage, Fountain Valley, Jedediah Smith, Clearview Estates

---
*Created: 2026-04-20 | Following SITE-BUILD-2026.md SOP*
