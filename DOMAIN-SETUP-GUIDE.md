# 🌐 Domain Setup Guide - ButterflyBlue Creations

## Current Status
✅ Domains added to Netlify:
- `butterflybluecreations.com` (Primary)
- `www.butterflybluecreations.com` (Redirect)

⚠️ Status: **Awaiting External DNS**

## Step-by-Step DNS Configuration

### 1. Get Netlify's DNS Records
From your Netlify dashboard, you need to add these DNS records in Namecheap:

**For butterflybluecreations.com:**
- Type: `A`
- Host: `@`
- Value: `75.2.60.5`

**For www.butterflybluecreations.com:**
- Type: `CNAME`
- Host: `www`
- Value: `unique-bavarois-80c441.netlify.app`

### 2. Configure in Namecheap

1. **Login to Namecheap**
   - Go to: https://www.namecheap.com
   - Sign in to your account

2. **Navigate to DNS Settings**
   - Dashboard → Domain List
   - Find `butterflybluecreations.com`
   - Click "Manage"
   - Go to "Advanced DNS" tab

3. **Remove Existing Records**
   - Delete any existing A records for `@`
   - Delete any existing CNAME records for `www`

4. **Add Netlify Records**
   
   **A Record:**
   - Type: `A Record`
   - Host: `@`
   - Value: `75.2.60.5`
   - TTL: `Automatic`
   
   **CNAME Record:**
   - Type: `CNAME Record`
   - Host: `www`
   - Value: `unique-bavarois-80c441.netlify.app`
   - TTL: `Automatic`

5. **Save Changes**
   - Click the checkmark to save each record
   - Changes will take 5-30 minutes to propagate

### 3. Verify DNS Propagation

Check if your DNS changes have propagated:
- Visit: https://www.whatsmydns.net
- Enter: `butterflybluecreations.com`
- Check if it shows `75.2.60.5`

### 4. Wait for Netlify Verification

Once DNS propagates:
1. Netlify will automatically detect the changes
2. Status will change from "Awaiting External DNS" to "Netlify DNS"
3. SSL certificate will be automatically provisioned

### 5. SSL Certificate

Netlify provides free SSL certificates automatically:
- ✅ Auto-renewing
- ✅ Let's Encrypt powered
- ✅ Covers both www and non-www

## 🎯 Quick Checklist

- [ ] Login to Namecheap
- [ ] Navigate to Advanced DNS for butterflybluecreations.com
- [ ] Add A record: @ → 75.2.60.5
- [ ] Add CNAME record: www → unique-bavarois-80c441.netlify.app
- [ ] Save changes
- [ ] Wait 5-30 minutes
- [ ] Check Netlify dashboard for status update

## ⏱️ Timeline

- **DNS Propagation**: 5-30 minutes (can take up to 48 hours in rare cases)
- **SSL Certificate**: Issued automatically after DNS verification
- **Full Setup**: Usually complete within 1 hour

## 🆘 Troubleshooting

**Still showing "Awaiting External DNS" after 1 hour?**
1. Double-check the DNS records in Namecheap
2. Clear your browser cache
3. Try: `nslookup butterflybluecreations.com`

**SSL Certificate Issues?**
- Click "Options" → "Renew certificate" in Netlify
- Make sure both domains are properly configured

## 📞 Support

- **Netlify Support**: https://answers.netlify.com
- **Namecheap Support**: https://www.namecheap.com/support

---

Your domain will be live at https://butterflybluecreations.com once DNS propagates! 🎉