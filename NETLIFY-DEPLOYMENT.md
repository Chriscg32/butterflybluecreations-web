# 🚀 Deploy to Netlify - Step by Step Guide

## Why Netlify?
- ✅ **100% Free** for personal projects
- ✅ **No credit card required**
- ✅ **Automatic deployments** from GitHub
- ✅ **Free SSL certificate**
- ✅ **Custom domain support**

## Step 1: Sign Up / Login (1 minute)
1. Go to: https://app.netlify.com/signup
2. Click "Sign up with GitHub"
3. Authorize Netlify to access your GitHub

## Step 2: Import Your Project (2 minutes)
1. Click "Add new site" → "Import an existing project"
2. Choose "Deploy with GitHub"
3. Search for: `butterflybluecreations-web`
4. Click on your repository

## Step 3: Configure Build Settings (Auto-detected!)
The settings should auto-populate from `netlify.toml`:
- **Base directory**: `frontend`
- **Build command**: `npm run build`
- **Publish directory**: `build`

Just click "Deploy butterflybluecreations-web"!

## Step 4: Wait for Build (2-3 minutes)
Watch the deploy log. You'll see:
```
Building...
Installing dependencies...
Running build command...
Deploy complete! 🎉
```

## Step 5: Get Your URL
Your site will be live at:
```
https://[random-name].netlify.app
```

## Step 6: Add Supabase Credentials (Important!)
1. Go to Site Settings → Environment Variables
2. Click "Add a variable"
3. Add these two variables:
   ```
   Key: REACT_APP_SUPABASE_URL
   Value: [Your Supabase URL]
   
   Key: REACT_APP_SUPABASE_ANON_KEY
   Value: [Your Supabase Anon Key]
   ```
4. Click "Save"
5. Trigger a redeploy: Deploys → "Trigger deploy" → "Deploy site"

## Step 7: Custom Domain (Optional)
1. Go to Domain Settings
2. Add custom domain: `butterflybluecreations.com`
3. Follow DNS instructions for Namecheap

## 🎉 You're Live!

### Quick Links:
- **Netlify Dashboard**: https://app.netlify.com
- **Your Repository**: https://github.com/Chriscg32/butterflybluecreations-web
- **Supabase Dashboard**: https://supabase.com/dashboard

### Test Your Site:
- [ ] Homepage loads
- [ ] Navigation works
- [ ] Mobile responsive
- [ ] Contact form (after Supabase setup)

### Next Steps:
1. Set up Supabase (see QUICK-START.md)
2. Add your environment variables
3. Configure custom domain
4. Start adding content!

---

**Need help?** Netlify has excellent documentation at docs.netlify.com