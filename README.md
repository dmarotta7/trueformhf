# TrueForm Health & Fitness — trueformhf.com

Premium health & wellness brand website. Built for GitHub Pages deployment with GoDaddy domain.

## Stack
- Pure HTML / CSS / JS — zero dependencies, zero build step
- Google Fonts (DM Serif Display + DM Sans) via CDN
- Schema.org structured data for SEO
- Full Open Graph + Twitter Card meta tags

## File Structure
```
/
├── index.html          ← Homepage (deploy this)
├── CNAME               ← GitHub Pages custom domain file
├── README.md
├── css/                ← (future: extracted stylesheets)
├── js/                 ← (future: extracted scripts)
└── images/             ← Add og-image.jpg, logo.png here
```

## Deploy to GitHub Pages

### Step 1 — Push to GitHub
```bash
cd trueformhf
git init
git add .
git commit -m "Initial site build"
git remote add origin https://github.com/dmarotta7/trueformhf.git
git push -u origin main
```

### Step 2 — Enable GitHub Pages
1. Go to your repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `root`
4. Save

### Step 3 — Connect GoDaddy Domain
In GoDaddy DNS, add these records:

| Type  | Name | Value                  | TTL  |
|-------|------|------------------------|------|
| A     | @    | 185.199.108.153        | 600  |
| A     | @    | 185.199.109.153        | 600  |
| A     | @    | 185.199.110.153        | 600  |
| A     | @    | 185.199.111.153        | 600  |
| CNAME | www  | dmarotta7.github.io    | 3600 |

The `CNAME` file in this repo handles the GitHub side. DNS propagation: 15 min to 48 hours.

### Step 4 — Enable HTTPS
In GitHub Pages settings, check **"Enforce HTTPS"** once the domain is verified.

---

## SEO Checklist
- [x] Title + meta description
- [x] Canonical URL
- [x] Open Graph tags
- [x] Twitter Card
- [x] Schema.org Organization markup
- [x] Semantic HTML (main, section, nav, footer, aria-labels)
- [x] Heading hierarchy (h1 → h2 → h3)
- [ ] Add sitemap.xml (create after launch)
- [ ] Submit to Google Search Console
- [ ] Add Google Analytics or Plausible
- [ ] Add og-image.jpg (1200×630) to /images/

## Email Capture Integration
The form `handleSubmit()` in index.html is ready to wire to:
- **GoHighLevel** (recommended — already in your stack)
- Mailchimp
- ConvertKit
- Klaviyo (best when supplements launch)

Replace the form handler with a fetch POST to your GHL webhook URL.

## Supplements E-Commerce Path
When ready to sell:
1. Add Shopify Buy Button (embedded JS widget) — no new domain needed
2. Or full Shopify storefront at shop.trueformhf.com
3. Product pages will link from the Supplements section

## Social Links
Update footer links in index.html once handles are confirmed:
- Instagram: https://instagram.com/trueformhf
- Facebook: https://facebook.com/trueformhf
- YouTube / TikTok: update when created
