# 🎯 NAMECHEAP DNS SETUP - EXACT INSTRUCTIONS

## Based on Netlify's DNS Configuration:

### For butterflybluecreations.com (apex domain):

**Option 1 - RECOMMENDED (if Namecheap supports ALIAS):**
```
Type: ALIAS (or ANAME or Flattened CNAME)
Host: @
Value: apex-loadbalancer.netlify.com
```

**Option 2 - FALLBACK (if ALIAS not supported):**
```
Type: A Record
Host: @
Value: 75.2.60.5
```

### For www.butterflybluecreations.com:
```
Type: CNAME Record
Host: www
Value: unique-bavarois-80c441.netlify.app
```

## 📋 Step-by-Step Instructions:

1. **Go to Namecheap**
   - Login at https://www.namecheap.com
   - Find butterflybluecreations.com
   - Click "Manage" → "Advanced DNS"

2. **Delete These Records** (if they exist):
   - Any A records with Host "@"
   - Any CNAME records with Host "www"
   - Any ALIAS/ANAME records

3. **Add New Records:**

   **First, check if Namecheap has ALIAS option:**
   - Look for: ALIAS, ANAME, or Flattened CNAME
   - If available, add:
     - Type: ALIAS
     - Host: @
     - Value: apex-loadbalancer.netlify.com

   **If NO ALIAS option, add this instead:**
   - Type: A Record
   - Host: @
   - Value: 75.2.60.5

   **Then add the www record:**
   - Type: CNAME
   - Host: www
   - Value: unique-bavarois-80c441.netlify.app

4. **Save Each Record**
   - Click the checkmark (✓)

## ⚠️ IMPORTANT NOTES:

1. **Netlify Warning:** With butterflybluecreations.com as primary domain, you won't get full CDN benefits

2. **Netlify Recommends:** Set www.butterflybluecreations.com as primary domain for better performance

3. **To Change Primary Domain** (optional):
   - In Netlify, click "Options" next to www.butterflybluecreations.com
   - Select "Set as primary domain"
   - This will make www the main site and redirect non-www to www

## 🕐 Timeline:
- DNS propagation: 5-30 minutes (up to 24 hours max)
- SSL certificate: Auto-provisioned after DNS verification
- Both domains will work after setup

## ✅ How to Know It's Working:
1. Refresh Netlify domain page
2. "Awaiting External DNS" warnings disappear
3. SSL certificate section appears
4. Both domains accessible via HTTPS

## 📝 Quick Reference:
```
butterflybluecreations.com ALIAS apex-loadbalancer.netlify.com
OR
butterflybluecreations.com A 75.2.60.5

www CNAME unique-bavarois-80c441.netlify.app
```

---

**Need help?** Most issues are resolved by:
- Double-checking the record values
- Waiting for DNS propagation
- Clearing browser cache