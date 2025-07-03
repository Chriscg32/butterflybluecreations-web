# ButterflyBlue Creations - Deployment Checklist

## Pre-Deployment

- [ ] All code committed to GitHub
- [ ] No errors in `npm run build`
- [ ] Environment variables documented
- [ ] README updated with latest information

## Vercel Setup

- [ ] Import repository from GitHub
- [ ] Add environment variables:
  - `REACT_APP_SUPABASE_URL`
  - `REACT_APP_SUPABASE_ANON_KEY`
- [ ] Verify build settings:
  - Build Command: `cd frontend && npm run build`
  - Output Directory: `frontend/build`
  - Install Command: `cd frontend && npm install`

## Supabase Setup

- [ ] Create new Supabase project
- [ ] Run SQL migrations from DEPLOYMENT.md
- [ ] Enable Row Level Security on all tables
- [ ] Copy project URL and anon key
- [ ] Test database connection

## Domain Configuration

- [ ] Add domain in Vercel settings
- [ ] Configure DNS in Namecheap:
  - A record: @ → 76.76.21.21
  - CNAME: www → cname.vercel-dns.com
- [ ] Wait for DNS propagation
- [ ] Verify SSL certificate is active

## Post-Deployment Testing

- [ ] Homepage loads correctly
- [ ] All navigation links work
- [ ] Contact form submission works
- [ ] Mobile responsive design works
- [ ] Animations load smoothly
- [ ] No console errors in browser
- [ ] Check page load speed

## Content Setup

- [ ] Add initial projects via Supabase
- [ ] Create first journal entry
- [ ] Add sample reviews
- [ ] Test feedback submission

## Final Checks

- [ ] Share website with test users
- [ ] Gather initial feedback
- [ ] Monitor Vercel analytics
- [ ] Set up error tracking (optional)

---

**Deployment Date:** _________________

**Deployed By:** _________________

**Notes:** _________________