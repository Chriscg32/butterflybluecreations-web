# 🎯 NAMECHEAP DNS SETUP - EXACT INSTRUCTIONS

## Based on Netlify's DNS Configuration:

### For butterflybluecreations.com (apex domain):

**RECOMMENDED - Try this first:**
```
Type: ALIAS (or ANAME or Flattened CNAME)
Host: @
Value: apex-loadbalancer.netlify.com
```

**FALLBACK - If ALIAS is not available:**
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

## 📋 Step-by-Step in Namecheap:

1. **Login to Namecheap**
   - Go to: https://www.namecheap.com
   - Sign in to your account
   - Find `butterflybluecreations.com` in Domain List
   - Click "Manage"
   - Click "Advanced DNS" tab

2. **Delete Existing Records**
   - Remove any A records with Host "@"
   - Remove any CNAME records with Host "www"
   - Remove any other ALIAS/ANAME records

3. **Add New Records:**

   **First, check if Namecheap has ALIAS option:**
   - Look for: ALIAS, ANAME, or Flattened CNAME in the record type dropdown
   - If available, add:
     - Type: ALIAS (or ANAME)
     - Host: @
     - Value: apex-loadbalancer.netlify.com
     - TTL: Automatic

   **If NO ALIAS option exists, add this instead:**
   - Type: A Record
   - Host: @
   - Value: 75.2.60.5
   - TTL: Automatic

   **Then add the www record:**
   - Type: CNAME Record
   - Host: www
   - Value: unique-bavarois-80c441.netlify.app
   - TTL: Automatic

4. **Save Each Record**
   - Click the checkmark (✓) after adding each record

## ⚠️ IMPORTANT NOTES FROM NETLIFY:

1. **Performance Warning:** With butterflybluecreations.com as your primary domain, you won't benefit from the full advantages of a CDN.

2. **Netlify Recommends:** Set `www.butterflybluecreations.com` as your primary custom domain for better performance.

3. **To Change Primary Domain (Optional but Recommended):**
   - In Netlify, click "Options" next to www.butterflybluecreations.com
   - Select "Set as primary domain"
   - This will make www the main site and redirect non-www to www

## 🕐 Timeline:
- DNS propagation: 5-30 minutes (up to 24 hours maximum)
- SSL certificate: Automatically provisioned after DNS verification
- Both domains will work after setup

## ✅ How to Know It's Working:
1. Refresh your Netlify domain management page
2. The "Awaiting External DNS" warnings will disappear
3. SSL/TLS certificate section will become available
4. Both domains will be accessible via HTTPS

## 📝 Quick Copy Reference:
```
butterflybluecreations.com ALIAS apex-loadbalancer.netlify.com
OR
butterflybluecreations.com A 75.2.60.5

www CNAME unique-bavarois-80c441.netlify.app
```

## 🆘 Troubleshooting:
- If still showing "Awaiting External DNS" after 1 hour, double-check the records
- Make sure you deleted old records first
- Try clearing your browser cache
- DNS can take up to 24 hours in rare cases

---

**Alternative Option:** You can also use Netlify DNS (shown at bottom of their instructions) which would handle everything automatically, but requires changing your nameservers in Namecheap.