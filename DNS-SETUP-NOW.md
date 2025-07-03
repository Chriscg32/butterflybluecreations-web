# 🎯 Quick DNS Setup Instructions

## What You See in Netlify:
✅ **butterflybluecreations.com** - Primary domain (Awaiting External DNS)  
✅ **www.butterflybluecreations.com** - Redirects to primary (Awaiting External DNS)  
✅ **Netlify subdomain**: unique-bavarois-80c441.netlify.app

## Now Go to Namecheap:

### 1. Login to Namecheap
- Go to: https://www.namecheap.com
- Sign in
- Click "Domain List"
- Find "butterflybluecreations.com"
- Click "Manage"

### 2. Go to Advanced DNS Tab
Click the "Advanced DNS" tab at the top

### 3. Delete Old Records
⚠️ **IMPORTANT**: Delete any existing:
- A Records with Host "@"
- CNAME Records with Host "www"

### 4. Add These Two Records:

**Record 1 - A Record:**
- Type: **A Record**
- Host: **@**
- Value: **75.2.60.5**
- TTL: **Automatic**

**Record 2 - CNAME Record:**
- Type: **CNAME Record**
- Host: **www**
- Value: **unique-bavarois-80c441.netlify.app**
- TTL: **Automatic**

### 5. Save Each Record
Click the checkmark (✓) after adding each record

## ⏱️ What Happens Next:
1. DNS propagation takes 5-30 minutes
2. The "Awaiting External DNS" warning will disappear
3. Netlify will automatically provision SSL certificates
4. Your site will be live at https://butterflybluecreations.com

## 🔍 Check Progress:
- Refresh your Netlify page in 10-15 minutes
- The warning should change to a green checkmark
- SSL certificate will show as "Netlify-managed certificate"

---

**Need help?** The DNS records are:
- A Record: @ → 75.2.60.5
- CNAME: www → unique-bavarois-80c441.netlify.app