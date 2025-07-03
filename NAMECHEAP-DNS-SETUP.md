# 🚀 Quick DNS Setup - Namecheap to Netlify

## Your Current Status
✅ Netlify site: `unique-bavarois-80c441.netlify.app`  
✅ Domains added in Netlify  
⚠️ Need to update DNS in Namecheap  

## Step 1: Login to Namecheap
1. Go to: https://www.namecheap.com
2. Sign in to your account
3. Click "Domain List" in your dashboard

## Step 2: Access DNS Settings
1. Find `butterflybluecreations.com`
2. Click "Manage" button
3. Click "Advanced DNS" tab

## Step 3: Add These DNS Records

**Delete any existing A or CNAME records first!**

Then add these two records:

### Record 1 - A Record (for root domain)
- **Type:** A Record
- **Host:** @
- **Value:** 75.2.60.5
- **TTL:** Automatic

### Record 2 - CNAME Record (for www)
- **Type:** CNAME Record  
- **Host:** www
- **Value:** unique-bavarois-80c441.netlify.app
- **TTL:** Automatic

## Step 4: Save Changes
Click the checkmark (✓) to save each record

## Step 5: Wait & Watch
- DNS changes take 5-30 minutes to propagate
- Check back in Netlify - the warning will disappear when ready
- SSL certificate will be automatically provisioned

## 🎯 That's It!

Your site will be live at:
- https://butterflybluecreations.com
- https://www.butterflybluecreations.com

## Need Help?

**Check DNS Status:**
- Visit: https://www.whatsmydns.net
- Enter: butterflybluecreations.com
- Should show: 75.2.60.5

**Still showing "Awaiting External DNS" after 1 hour?**
- Double-check the records in Namecheap
- Make sure you deleted old records
- Try clicking "Options" → "Verify DNS configuration" in Netlify

---
⏱️ Typical setup time: 15-30 minutes