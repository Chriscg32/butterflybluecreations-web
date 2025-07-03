# 🚀 NAMECHEAP DNS SETUP - QUICK REFERENCE

## DNS Records to Add in Namecheap:

### 1. For butterflybluecreations.com:

**First, check if Namecheap supports ALIAS/ANAME:**
```
Type: ALIAS (or ANAME or Flattened CNAME)
Host: @
Value: apex-loadbalancer.netlify.com
TTL: Automatic
```

**If ALIAS is NOT available, use this instead:**
```
Type: A Record
Host: @
Value: 75.2.60.5
TTL: Automatic
```

### 2. For www.butterflybluecreations.com:
```
Type: CNAME Record
Host: www
Value: unique-bavarois-80c441.netlify.app
TTL: Automatic
```

## 📋 Step-by-Step in Namecheap:

1. **Login to Namecheap**
   - https://www.namecheap.com
   - Domain List → butterflybluecreations.com → Manage
   - Click "Advanced DNS" tab

2. **Delete Existing Records**
   - Remove any A records with Host "@"
   - Remove any CNAME records with Host "www"

3. **Add the Records Above**
   - Try ALIAS first for butterflybluecreations.com
   - If no ALIAS option, use A record
   - Add CNAME for www

4. **Save Each Record**
   - Click the checkmark (✓)

## ⚠️ Netlify's Recommendations:

1. **Performance Warning:** Using butterflybluecreations.com as primary domain won't give full CDN benefits

2. **Netlify Suggests:** Set www.butterflybluecreations.com as primary domain instead

3. **To Change Primary (Optional):**
   - In Netlify, click "Options" next to www.butterflybluecreations.com
   - Select "Set as primary domain"

## 🕐 Timeline:
- DNS propagation: 5-30 minutes
- SSL certificate: Auto-provisioned after DNS verification

## ✅ Success Indicators:
- "Awaiting External DNS" warnings disappear
- SSL/TLS certificate section becomes available
- Both domains accessible via HTTPS

---

**Quick Copy-Paste Reference:**
```
butterflybluecreations.com ALIAS apex-loadbalancer.netlify.com
OR
butterflybluecreations.com A 75.2.60.5

www CNAME unique-bavarois-80c441.netlify.app
```