# DNS Configuration Guide

## Step 1: Deploy yarivzur.com to Vercel

1. Push yarivzur-landing repo to GitHub
2. Import to Vercel
3. In Vercel project settings, add domains:
   - yarivzur.com
   - www.yarivzur.com (redirect to apex)

## Step 2: Configure DNS (EuroDNS)

For yarivzur.com:
- Add A record: `@` → `76.76.21.21` (Vercel IP)
- Add CNAME: `www` → `cname.vercel-dns.com`

## Step 3: Configure pokarov.com Redirect

**Option A: Create new Vercel project for redirect**
- Create minimal project with vercel.json:
  ```json
  {
    "redirects": [
      { "source": "/:path*", "destination": "https://yarivzur.com", "permanent": true }
    ]
  }
  ```
- Point pokarov.com A record to this project

**Option B: Use DNS-level redirect (if EuroDNS supports)**

**CRITICAL: Ensure blog.pokarov.com continues pointing to the blog, NOT the redirect!**

## Verification Checklist

- [ ] yarivzur.com loads correctly
- [ ] www.yarivzur.com redirects to yarivzur.com
- [ ] pokarov.com redirects to yarivzur.com
- [ ] blog.pokarov.com still loads blog (NOT redirected)
- [ ] www.lokahi.me loads correctly
