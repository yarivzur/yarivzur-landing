# Brand Architecture Handover

## What Was Completed

### 1. yarivzur.com Landing Page (DONE)
- Built new Astro 5 + Tailwind v4 site at `yarivzur-landing/`
- Single-page hub with two-column layout: Lokahi (professional) / Bitterness Inc. (personal)
- Deployed to Vercel, DNS configured
- Live at: **www.yarivzur.com**
- GitHub: github.com/yarivzur/yarivzur-landing

### 2. blog.pokarov.com Updates (DONE)
- Updated site URL from `bitterness-inc.vercel.app` to `blog.pokarov.com` in astro.config.mjs
- Replaced About page (`src/pages/about.astro`) with branded content including Lokahi cross-link
- Added footer cross-link: "Personal writing by Yariv Zur | Professional work at Lokahi"
- Replaced default Astro favicon with serif "B"
- Added CONTENT-GUIDELINES.md to repo
- GitHub: github.com/yarivzur/pokarov-blog

### 3. www.lokahi.me Updates (DONE)
- Created new About page at `src/pages/about.astro` (has placeholder text — see below)
- Added "About" to navigation in `src/config.ts`
- Added footer cross-link: "Lokahi Advisory | Personal writing at Bitterness Inc."
- Replaced default Astro favicon with canoe icon from logo
- Added CONTENT-GUIDELINES.md to repo
- GitHub: github.com/yarivzur/lokahi-advisory-site

### 4. Documentation (DONE)
- `DNS-SETUP.md` — Vercel + EuroDNS configuration (completed)
- `CONTENT-GUIDELINES.md` — Content placement decision framework (in all 3 repos)
- `SOCIAL-UPDATES.md` — LinkedIn and email signature copy (in yarivzur-landing repo)

### 5. DNS Configuration (DONE)
- www.yarivzur.com — live (primary domain)
- blog.pokarov.com — live
- www.lokahi.me — live

---

## What Still Needs To Be Done

### A. Fill In Lokahi About Page Placeholders
**File:** `src/pages/about.astro` in the lokahi-advisory-site repo
**Two placeholders to replace:**
1. `[PLACEHOLDER: Founder needs to add core services/value proposition]` — describe what Lokahi does
2. `[PLACEHOLDER: 2-3 sentence professional bio needed from founder]` — Yariv's professional bio

### B. Set Up pokarov.com → yarivzur.com Redirect
The apex domain `pokarov.com` should redirect to `yarivzur.com` so that `blog.pokarov.com` still works but `pokarov.com` itself points to the hub. Two options:
- **Option A:** Create a minimal Vercel project with just a vercel.json containing a redirect rule
- **Option B:** Use EuroDNS DNS-level redirect if supported
- **CRITICAL:** `blog.pokarov.com` must NOT be affected by this redirect

### C. Update LinkedIn Profiles
Copy is ready in `SOCIAL-UPDATES.md` (in the yarivzur-landing repo):

**Personal LinkedIn (linkedin.com/in/yarivzur):**
- Headline: "Advisor & Strategist | Founder, Lokahi"
- Website: yarivzur.com
- Add to About: links to both blogs

**Company LinkedIn (linkedin.com/company/lokahiadvisory):**
- Website: www.lokahi.me
- Add to About: "Founded by Yariv Zur" + link to personal blog

### D. Update Email Signatures
Copy is ready in `SOCIAL-UPDATES.md`:

**Professional (yariv@lokahi.me):**
Yariv Zur / Founder, Lokahi / yariv@lokahi.me / www.lokahi.me

**Personal (yariv.zur@gmail.com):**
Yariv Zur / yarivzur.com / Professional: Lokahi | Personal: Bitterness Inc.

---

## Architecture Summary

```
yarivzur.com (hub)
├── → www.lokahi.me (professional: advisory, strategy, client-facing)
└── → blog.pokarov.com (personal: cultural commentary, essays, unfiltered)

pokarov.com → yarivzur.com (redirect, NOT YET SET UP)
```

## Tech Stack (all sites)
- Astro 5.17.1
- Tailwind CSS v4
- Vercel (auto-deploy from GitHub main branch)
- EuroDNS (DNS management)

## Contact Info
- Professional: yariv@lokahi.me
- Personal: yariv.zur@gmail.com
- LinkedIn (personal): linkedin.com/in/yarivzur
- LinkedIn (company): linkedin.com/company/lokahiadvisory
