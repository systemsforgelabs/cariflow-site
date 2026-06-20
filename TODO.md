# cariflow-site — Claude Code Task List

> Running TODO for site dev. Work top-to-bottom. Commit after each task or batch.
> Branch strategy: feature branches → Cloudflare preview → merge to `main`.
> Last updated: 2026-06-09

---

## 🔴 High Priority — Pre-Launch Blockers

### [ ] 1. Favicon
Add a simple SVG favicon using brand navy `#1A2F45` with the letter C.
```
- Create favicon.svg in repo root
- Add to <head>: <link rel="icon" href="/favicon.svg">
- Commit: "feat: add SVG favicon"
```

### [ ] 2. Mobile Nav (Hamburger Menu)
Nav has no mobile menu. Add hamburger toggle for viewports under 768px.
```
- Pure JS, no library
- Hide .nav-links on mobile
- Show toggle button, slide-down menu on tap
- Match existing nav styles (#1A2F45, blur backdrop)
- Commit: "feat: mobile hamburger nav"
```

### [ ] 3. Verify Calendly Link
Confirm https://calendly.com/daveops-cloudai/30min is live.
```
- Check both CTA instances: hero button + CTA section near footer
- Update URL in both places if changed
- Commit: "fix: verify and update Calendly URL" (only if changed)
```

### [ ] 4. Open Graph / Social Meta Tags
Clean LinkedIn previews when the site is shared.
```
Add to <head>:
  <meta property="og:title" content="Cariflow — AI & Workflow Automation for Healthcare & Small Business">
  <meta property="og:description" content="AI automation and workflow consulting for healthcare practices and small businesses.">
  <meta property="og:url" content="https://gocariflow.com">
  <meta property="og:type" content="website">
  <!-- <meta property="og:image" content="https://gocariflow.com/og-image.png"> -->

- Leave og:image commented out until a real OG image exists
- Commit: "feat: add Open Graph meta tags"
```

---

## 🟡 Medium Priority — Quality & Accessibility

### [ ] 5. Reduced Motion Accessibility
Hero has CSS fadeUp animations. Wrap in prefers-reduced-motion.
```
- Wrap all animation/transition declarations in:
  @media (prefers-reduced-motion: no-preference) { ... }
- Commit: "fix: respect prefers-reduced-motion"
```

### [ ] 6. Safari Smooth Scroll Polyfill
`scroll-behavior: smooth` not supported in all Safari versions.
```
- Add smoothscroll-polyfill via CDN as fallback:
  <script src="https://cdn.jsdelivr.net/npm/smoothscroll-polyfill@0.4.4/dist/smoothscroll.min.js"></script>
  <script>smoothscroll.polyfill();</script>
- Commit: "fix: smooth scroll Safari polyfill"
```

### [ ] 7. Footer Year Auto-Update
Replace hardcoded "© 2026" so it never goes stale.
```
- Replace static year text with: <span id="footer-year"></span>
- Add before </body>:
  <script>document.getElementById('footer-year').textContent = new Date().getFullYear();</script>
- Commit: "fix: auto-update footer copyright year"
```

### [ ] 8. Hero Logo Image Audit
Confirm logo image src is correct and the file is committed.
```
- Check: does logo.png or logo.svg exist in repo root?
- Add onerror fallback on the <img> if needed:
  onerror="this.style.display='none'"
- Commit: "fix: hero logo path and fallback" (only if changed)
```

---

## 🟢 Nice to Have — Post-Launch

### [ ] 9. robots.txt
Create in repo root. Cloudflare Pages serves static files from root automatically.
```
File: robots.txt
---
User-agent: *
Allow: /
Sitemap: https://gocariflow.com/sitemap.xml
---
- Commit: "feat: add robots.txt"
```

### [ ] 10. sitemap.xml
Single-page sitemap for SEO.
```
File: sitemap.xml
---
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://gocariflow.com/</loc>
    <lastmod>2026-06-09</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
---
- Commit: "feat: add sitemap.xml"
```

### [ ] 11. Contact Form (No Backend)
Replace or supplement the mailto CTA with an embedded form.
```
- Options: Tally.so (free) or Jotform HIPAA (paid, preferred for healthcare clients)
- Results route to dave@gocariflow.com
- Embed in CTA section as alternative to mailto link
- Commit: "feat: add contact form embed"
```

### [ ] 12. Analytics
Add before launch. Plausible recommended for healthcare-adjacent credibility.
```
- Plausible ($9/mo, privacy-first, no user tracking — good trust signal)
- OR Google Analytics 4 (free)
- Add script snippet to <head>
- Commit: "feat: add analytics"
```

---

## 🚀 Batch Kickoff Prompts

### Pre-Launch Polish (Tasks 1–5)
```
Open index.html in the cariflow-site repo. Work through these in order,
committing after each one:
1. Add SVG favicon (navy #1A2F45, letter C) and wire up in <head>
2. Add mobile hamburger nav for <768px viewports, pure JS
3. Add Open Graph meta tags for LinkedIn sharing (og:image commented out)
4. Wrap hero animations in prefers-reduced-motion media query
5. Auto-update footer copyright year via JS

When done: push all commits to branch feature/pre-launch-polish.
Do not touch main — I'll review the Cloudflare preview first.
```

### Static Files Pass (Tasks 9–10)
```
In the cariflow-site repo root, create two new files:
1. robots.txt — allow all crawlers, point to sitemap at https://gocariflow.com/sitemap.xml
2. sitemap.xml — single URL entry for https://gocariflow.com/, lastmod today

Commit both as "feat: add robots.txt and sitemap.xml" and push to feature/seo-static-files.
```

---

## ✅ Completed

- [x] Initial index.html site generated and committed — 2026-06-01
- [x] pitch.html interactive company pitch presentation — 2026-06-09
- [x] outreach.html First Outreach Kit (tabbed, copy-able scripts) — 2026-06-09
- [x] brand.html brand reference page — 2026-06-09
- [x] CLAUDE.md project context file added to repo — 2026-06-19
- [x] Cloudflare Pages CI/CD wired to GitHub main — 2026-06-19 (test domain active; gocariflow.com domain added to CF, not yet assigned to Pages project)
- [x] Git identity configured (dave@gocariflow.com / Dave Horton) — 2026-06-19
- [x] outreach.html restyled to Cariflow brand system (Lora, DM Sans, navy/blue palette) — 2026-06-19
