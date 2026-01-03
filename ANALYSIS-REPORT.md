# Caymanian Times (caymaniantimes.ky) - Tech Stack Analysis

**Analysis Date:** 2026-01-03
**Note:** Direct website inspection was blocked (403). Analysis based on secondary sources, DNS lookups, and publicly available technology profiles.

---

## 1. Tech Stack Detection

### CMS/Platform
| Component | Value | Confidence | Evidence |
|-----------|-------|------------|----------|
| **Backend Language** | PHP | High | ZoomInfo profile, `index.php` in URLs |
| **CMS** | Custom PHP CMS (likely) | Medium | No WordPress indicators found |
| **Framework** | Unknown (possibly CodeIgniter/Laravel) | Low | URL patterns suggest PHP framework |

**Notable:** No `/wp-content/`, `/wp-admin/`, or WordPress meta generator tags were found in any indexed content, suggesting this is NOT WordPress.

### Frontend
| Component | Status | Notes |
|-----------|--------|-------|
| JavaScript Libraries | Unknown | Likely jQuery (typical for PHP sites) |
| CSS Framework | Unknown | Likely Bootstrap or similar |
| Responsive Design | Yes | Modern news site layout |

### Hosting/CDN
| Component | Value | Source |
|-----------|-------|--------|
| **Hosting Provider** | OVH SAS | DNS lookup |
| **Web Server** | Apache | Technology profile |
| **CDN** | Cloudflare | Nameservers confirm |
| **IP Address** | 149.56.185.76 | DNS lookup |
| **Nameservers** | grace.ns.cloudflare.com, wesley.ns.cloudflare.com | WHOIS |
| **DNSSEC** | Not enabled | DNS check |

### Analytics/Tracking Tools
| Tool | Purpose | Confirmed |
|------|---------|-----------|
| **Google AdSense** | Display advertising | Yes (ZoomInfo) |
| **Google reCAPTCHA** | Spam protection | Yes (ZoomInfo) |
| **Bullhorn** | Recruitment/ATS integration | Yes (ZoomInfo) |
| **Google Analytics** | Traffic analytics | Likely (typical with AdSense) |

---

## 2. Site Structure

### URL Patterns
```
/                                    # Homepage
/news                                # News listing
/news/{article-slug}                 # Individual articles
/news-category/{category-slug}       # Category pages
/index.php/news-category/{category}  # Alternative PHP URLs
/archives                            # PDF archive downloads
```

### Main Navigation Hierarchy
```
Home
├── News
│   ├── Local News
│   ├── International
│   ├── Regional
│   ├── Politics
│   ├── Business
│   ├── Editorial
│   ├── Sports
│   ├── Health Care
│   ├── Entertainment
│   ├── Environment
│   ├── Tourism
│   ├── Education
│   ├── Employment
│   ├── Development
│   ├── Cost of Living
│   ├── Hurricane Watch
│   ├── Community Voice
│   ├── Law Enforcement
│   ├── Government
│   └── Front Pages
├── Archives (PDF downloads by month)
├── Video News Release
├── Classifieds
│   ├── Personal Classifieds (free)
│   └── Featured Classifieds (paid)
├── Gas Prices
├── Community Calendar
├── Advertising
├── About Us
└── Contact Us
```

### Subdomains
| Subdomain | Purpose |
|-----------|---------|
| `jobmarket.caymaniantimes.ky` | Separate employment listings portal |
| `ctimes.ky` | URL shortener/redirect |

---

## 3. Key Features & Libraries

### Content Features
| Feature | Implementation | Notes |
|---------|---------------|-------|
| **Article Publishing** | Custom CMS | Standard news articles with categories |
| **PDF Archives** | Monthly downloads | Print replica PDFs |
| **Video Content** | VNR Section | Video News Releases |
| **Image Galleries** | Embedded | In-article images |

### Interactive Features
| Feature | Implementation | Details |
|---------|---------------|---------|
| **Comments** | Native/custom | No login required, moderated pre-publication |
| **Search** | Unknown | Standard site search |
| **Newsletter** | Email-based | Contact: ctimesonline@caymaniantimes.ky |
| **Forms** | Multiple | Contact, ad upload, classifieds submission |

### Third-Party Integrations
| Integration | Purpose | Migration Impact |
|-------------|---------|-----------------|
| **Google AdSense** | Monetization | Low - script swap |
| **Google reCAPTCHA** | Bot protection | Low - API key change |
| **Bullhorn ATS** | Job market/recruitment | High - API integration |
| **Cloudflare** | CDN/Security | Low - DNS config only |

### Classifieds System
- **Categories:** Property Rentals, Vehicles, Services, Real Estate, Furniture, Office
- **Types:** Free personal ads, Featured/paid listings
- **Submission:** Email and form-based

### Job Market Portal
- **URL:** jobmarket.caymaniantimes.ky
- **Features:** Job listings, employer ad uploads, category browsing
- **Contact:** jobmarket@caymaniantimes.ky
- **Integration:** Bullhorn ATS

---

## 4. Migration Considerations

### Complexity Assessment: **MEDIUM-HIGH**

### Content Migration Scope
| Content Type | Volume/Scope | Complexity |
|--------------|--------------|------------|
| **Articles** | 10+ years (2013-present) | Medium - standard content |
| **Categories** | 20+ news categories | Low - taxonomy mapping |
| **PDF Archives** | Monthly since 2016 | Low - file migration |
| **Classifieds** | User submissions | Medium - custom module |
| **Jobs** | Separate subdomain | High - may need separate migration |
| **Comments** | All articles | Medium - data export needed |
| **Media/Images** | All articles | Low - file migration |

### Dependencies Requiring Replacement

| Dependency | Current | Replacement Options | Effort |
|------------|---------|---------------------|--------|
| **PHP Backend** | Custom | Laravel, WordPress, Node.js, Headless CMS | HIGH |
| **CMS** | Custom | WordPress, Ghost, Strapi, Sanity | HIGH |
| **AdSense** | Google | Keep or alternative ad network | LOW |
| **reCAPTCHA** | Google | Keep, hCaptcha, or Turnstile | LOW |
| **Bullhorn** | ATS integration | Keep or custom job board | MEDIUM-HIGH |
| **Cloudflare** | CDN | Keep (recommended) | LOW |
| **Comments** | Custom | Disqus, native CMS, custom | MEDIUM |

### Feature Equivalents Needed

| Current Feature | Standard Solution |
|-----------------|-------------------|
| Category-based browsing | Any CMS with taxonomy |
| PDF archive downloads | Media library + custom page |
| Video News Releases | YouTube/Vimeo embeds or hosted video |
| Classifieds system | WP Classified Ads plugin or custom |
| Job board | Bullhorn plugin or custom integration |
| Ad upload forms | File upload forms with notifications |
| Community calendar | Events plugin/module |
| Gas prices page | Custom data page |
| Moderated comments | Native CMS comments or Disqus |

### Critical Migration Risks

1. **Stingray Media Group Acquisition** (Effective Jan 1, 2026)
   - New ownership may have specific platform requirements
   - Potential integration with Stingray ecosystem (eCay, Stingray Rewards, radio)
   - Strategy emphasizes "technology media platform"

2. **URL Preservation**
   - Must maintain SEO rankings
   - Redirect rules needed for `/news-category/`, `/news/`, `/index.php/` patterns
   - Shortlink domain (ctimes.ky) must continue working

3. **Job Market Subdomain**
   - Separate system may have different tech stack
   - Bullhorn integration is critical for functionality
   - May require independent migration assessment

### Recommended Migration Phases

| Phase | Focus | Key Tasks |
|-------|-------|-----------|
| **1** | Content Export | Full audit, database export, media inventory, URL mapping |
| **2** | Platform Setup | CMS selection, content model design, staging environment |
| **3** | Data Migration | Articles, categories, PDFs, media, static pages |
| **4** | Features | Classifieds, comments, ads, custom features |
| **5** | Integration | Bullhorn, AdSense, reCAPTCHA, SEO verification |
| **6** | Launch | DNS cutover, redirects, monitoring |

---

## Company Context

| Attribute | Value |
|-----------|-------|
| **Founded** | 2013 (as Employment Weekly) |
| **Rebranded** | 2016 (to Caymanian Times) |
| **Original Owner** | Lewis (Cayman Islands) Ltd |
| **Founder** | Ralph Lewis (continuing as publisher) |
| **New Owner** | Stingray Media Group (from Jan 1, 2026) |
| **Readership** | 250,000+ |
| **Weekly Visits** | 30,000+ |
| **Location** | 19 Walkers Rd, George Town, Cayman Islands |
| **Contact** | info@caymaniantimes.ky, +1 (345) 916-2000 |

---

## Data Sources
- ZoomInfo technology profile
- DNS/WHOIS lookups
- Web search analysis
- URL pattern analysis from indexed pages

## Limitations
Direct website inspection was blocked (403 errors from network restrictions). For complete analysis:
- Use browser DevTools on the live site
- Run Wappalyzer browser extension
- Check BuiltWith.com/caymaniantimes.ky
- Inspect page source for exact library versions
