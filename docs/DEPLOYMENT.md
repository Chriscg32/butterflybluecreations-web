# Deployment Guide

## Vercel Deployment

1. **Connect to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Sign in with your GitHub account
   - Click "New Project"
   - Import the `butterflybluecreations-web` repository

2. **Configure Environment Variables**
   In the Vercel dashboard, add these environment variables:
   - `REACT_APP_SUPABASE_URL`: Your Supabase project URL
   - `REACT_APP_SUPABASE_ANON_KEY`: Your Supabase anonymous key

3. **Deploy Settings**
   The `vercel.json` file is already configured with:
   - Build command: `cd frontend && npm run build`
   - Output directory: `frontend/build`
   - Install command: `cd frontend && npm install`

4. **Deploy**
   - Click "Deploy"
   - Vercel will automatically build and deploy your site

## Supabase Setup

1. **Create a Supabase Project**
   - Go to [supabase.com](https://supabase.com)
   - Create a new project
   - Note your project URL and anon key

2. **Create Database Tables**
   Run these SQL commands in the Supabase SQL editor:

```sql
-- Projects table
CREATE TABLE projects (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  name TEXT NOT NULL,
  summary TEXT,
  status TEXT CHECK (status IN ('MVP', 'Launched', 'Coming Soon')),
  review_score INTEGER CHECK (review_score >= 1 AND review_score <= 5),
  link TEXT,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Journal entries table
CREATE TABLE journal_entries (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  title TEXT NOT NULL,
  content TEXT NOT NULL,
  date DATE NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Reviews table
CREATE TABLE reviews (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  author TEXT NOT NULL,
  rating INTEGER NOT NULL CHECK (rating >= 1 AND rating <= 5),
  content TEXT NOT NULL,
  project TEXT,
  date DATE NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Feedback table
CREATE TABLE feedback (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  project TEXT,
  feedback TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Contact messages table
CREATE TABLE contact_messages (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  name TEXT NOT NULL,
  email TEXT NOT NULL,
  subject TEXT NOT NULL,
  message TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);
```

3. **Enable Row Level Security (RLS)**
   For each table, enable RLS and create appropriate policies:

```sql
-- Enable RLS on all tables
ALTER TABLE projects ENABLE ROW LEVEL SECURITY;
ALTER TABLE journal_entries ENABLE ROW LEVEL SECURITY;
ALTER TABLE reviews ENABLE ROW LEVEL SECURITY;
ALTER TABLE feedback ENABLE ROW LEVEL SECURITY;
ALTER TABLE contact_messages ENABLE ROW LEVEL SECURITY;

-- Allow public read access to projects, journal, and reviews
CREATE POLICY "Public can read projects" ON projects FOR SELECT USING (true);
CREATE POLICY "Public can read journal" ON journal_entries FOR SELECT USING (true);
CREATE POLICY "Public can read reviews" ON reviews FOR SELECT USING (true);

-- Allow public to submit feedback and contact messages
CREATE POLICY "Public can submit feedback" ON feedback FOR INSERT WITH CHECK (true);
CREATE POLICY "Public can submit contact" ON contact_messages FOR INSERT WITH CHECK (true);
```

## Domain Setup (Namecheap to Vercel)

1. **In Vercel:**
   - Go to your project settings
   - Navigate to "Domains"
   - Add `butterflybluecreations.com` and `www.butterflybluecreations.com`

2. **In Namecheap:**
   - Go to your domain management
   - Set up custom DNS:
     - Add an A record: `@` pointing to Vercel's IP (76.76.21.21)
     - Add a CNAME record: `www` pointing to `cname.vercel-dns.com`

3. **SSL Certificate**
   - Vercel automatically provisions SSL certificates
   - Wait for DNS propagation (can take up to 48 hours)

## Post-Deployment Checklist

- [ ] Test all pages and navigation
- [ ] Verify contact form submission
- [ ] Check responsive design on mobile
- [ ] Test feedback forms
- [ ] Verify Supabase connection
- [ ] Check SSL certificate is active
- [ ] Test domain redirects (www to non-www or vice versa)