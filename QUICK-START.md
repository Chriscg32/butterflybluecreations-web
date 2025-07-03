# 🚀 Quick Start Guide - ButterflyBlue Creations

## Immediate Next Steps (15 minutes total)

### 1️⃣ Deploy to Vercel (5 minutes)
```bash
# Option A: Using Vercel CLI
npm i -g vercel
cd butterflybluecreations
vercel

# Option B: Via Web Interface
# Go to https://vercel.com/new
# Import: Chriscg32/butterflybluecreations-web
```

### 2️⃣ Set Up Supabase (5 minutes)
1. Go to https://supabase.com/dashboard
2. Click "New Project"
3. Name: `butterflybluecreations`
4. Generate a strong password
5. Region: Choose closest to you
6. Click "Create new project"

### 3️⃣ Get Your Credentials (2 minutes)
In Supabase Dashboard:
- Go to Settings → API
- Copy:
  - `Project URL` → `REACT_APP_SUPABASE_URL`
  - `anon public` key → `REACT_APP_SUPABASE_ANON_KEY`

### 4️⃣ Add to Vercel (3 minutes)
In Vercel Dashboard:
1. Go to your project → Settings → Environment Variables
2. Add:
   ```
   REACT_APP_SUPABASE_URL = your-project-url
   REACT_APP_SUPABASE_ANON_KEY = your-anon-key
   ```
3. Redeploy: Deployments → ... → Redeploy

## 🎉 Your Site is Live!

Your website will be available at:
- `https://butterflybluecreations-web.vercel.app`
- Or your custom domain once configured

## 📱 Test Your Site
- [ ] Visit your Vercel URL
- [ ] Check mobile responsiveness
- [ ] Test all navigation links
- [ ] Verify animations work

## 🐛 Troubleshooting
- **Build fails?** Check environment variables
- **Blank page?** Clear browser cache
- **Supabase error?** Verify credentials

---

**Need the full guide?** See `docs/DEPLOYMENT.md`

**Questions?** The code is well-documented and ready to customize!