# 🎯 Namecheap DNS Setup - Final Instructions

Based on your Netlify DNS configuration screens, here's exactly what to add in Namecheap:

## Step 1: Login to Namecheap
1. Go to: https://www.namecheap.com
2. Sign in to your account
3. Find `butterflybluecreations.com`
4. Click "Manage" → "Advanced DNS"

## Step 2: Delete Existing Records
Delete any existing:
- A records with Host "@"
- CNAME records with Host "www"
- ALIAS/ANAME records (if any)

## Step 3: Add These Records

### For butterflybluecreations.com (apex domain):
Since Namecheap doesn't support ALIAS records, use the fallback option:

**A Record:**
- Type: **A Record**
- Host: **@**
- Value: **75.2.60.5**
- TTL: **Automatic**

### For www.butterflybluecreations.com:
**CNAME Record:**
- Type: **CNAME Record**
- Host: **www**
- Value: **unique-bavarois-80c441.netlify.app**
- TTL: **Automatic**

## Step 4: Save Changes
Click the checkmark (✓) to save each record.

## ⚠️ Important Note from Netlify:
Netlify warns that with the current configuration (apex domain as primary), you won't benefit from the full advantages of a CDN. They recommend setting `www.butterflybluecreations.com` as your primary custom domain instead.

## 📋 Summary of Records to Add:
```
A Record: @ → 75.2.60.5
CNAME Record: www → unique-bavarois-80c441.netlify.app
```

## ⏱️ Timeline:
- DNS propagation: 5-30 minutes (up to 24 hours in rare cases)
- SSL certificate: Automatically provisioned after DNS verification
- Both domains will work, with www redirecting to the apex domain

## 🔍 To Check Progress:
1. Refresh your Netlify domain management page
2. The "Awaiting External DNS" warnings will disappear
3. SSL certificate will be automatically provisioned

---

**Alternative:** If you want better CDN performance, you could:
1. Set www.butterflybluecreations.com as primary in Netlify
2. Then butterflybluecreations.com would redirect to www instead