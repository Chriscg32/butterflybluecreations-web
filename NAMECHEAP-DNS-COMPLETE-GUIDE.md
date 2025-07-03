# 🎯 Namecheap DNS Setup - Step by Step

## Based on Netlify's Instructions:

### Option 1: RECOMMENDED by Netlify (Better Performance)
**Use ALIAS record if Namecheap supports it:**

For butterflybluecreations.com:
```
Type: ALIAS (or ANAME or Flattened CNAME)
Host: @
Value: apex-loadbalancer.netlify.com
```

### Option 2: If Namecheap doesn't support ALIAS
**Use these records instead:**

For butterflybluecreations.com:
```
Type: A Record
Host: @
Value: 75.2.60.5
```

For www.butterflybluecreations.com:
```
Type: CNAME Record
Host: www
Value: unique-bavarois-80c441.netlify.app
```

## 📋 Step-by-Step in Namecheap:

1. **Login to Namecheap**
   - Go to: https://www.namecheap.com
   - Sign in → Domain List → Manage butterflybluecreations.com
   - Click "Advanced DNS" tab

2. **Delete Existing Records**
   - Remove any A records with Host "@"
   - Remove any CNAME records with Host "www"

3. **Add New Records**

   **First, try to add ALIAS record:**
   - Type: ALIAS (might be called ANAME)
   - Host: @
   - Value: apex-loadbalancer.netlify.com
   
   **If ALIAS is not available, add:**
   - Type: A Record
   - Host: @
   - Value: 75.2.60.5

   **Then add the www record:**
   - Type: CNAME Record
   - Host: www
   - Value: unique-bavarois-80c441.netlify.app

4. **Save Changes**
   - Click checkmark (✓) after each record

## ⚠️ Important Notes:

1. **Netlify recommends** setting `www.butterflybluecreations.com` as your primary domain for better CDN performance

2. **Current setup** has `butterflybluecreations.com` as primary, which means:
   - butterflybluecreations.com → main site
   - www.butterflybluecreations.com → redirects to main

3. **To change primary domain** (optional but recommended):
   - In Netlify, click "Options" next to www.butterflybluecreations.com
   - Select "Set as primary domain"

## 🕐 Timeline:
- DNS propagation: 5-30 minutes
- SSL certificate: Auto-provisioned after DNS verification
- Full setup: Usually complete within 1 hour

## ✅ How to verify it's working:
1. The "Awaiting External DNS" warnings will disappear
2. Both domains will show green checkmarks
3. SSL certificate will be automatically provisioned

---

**Quick Reference:**
- ALIAS: @ → apex-loadbalancer.netlify.com (preferred)
- OR A: @ → 75.2.60.5 (fallback)
- CNAME: www → unique-bavarois-80c441.netlify.app