# Insider Opinion — Hugo + Netlify CMS Starter (Podcast)

A zero-cost, SEO-friendly podcast website starter using **Hugo** and **Netlify CMS**.  
- Fast static site, no ads  
- `/admin` login to edit content in a dashboard  
- Episode pages with audio/YouTube/Spotify embeds  
- SEO meta tags + RSS enabled

## 1) Prereqs
- Install Hugo Extended: https://gohugo.io/installation/
- Install Git: https://git-scm.com/downloads

Check:
```bash
hugo version
```

## 2) Run locally
```bash
git clone <this-repo>
cd insider-opinion-hugo-netlifycms-starter
hugo server -D
# open http://localhost:1313
```

## 3) Deploy to Netlify (recommended)
1. Create a new GitHub repo and push this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<you>/podcast-site.git
   git push -u origin main
   ```
2. Go to **Netlify → Add New Site → Import from Git** → choose your repo.
3. Build settings:  
   - **Build command:** `hugo --gc --minify`  
   - **Publish dir:** `public`  
   - Set `HUGO_VERSION` to `0.128.1` (matches `netlify.toml`)

## 4) Enable Netlify Identity + Git Gateway (for /admin login)
- On Netlify, go to **Identity** → Enable Identity.
- Click **Settings & usage** → Enable **Git Gateway**.
- Invite yourself (and your team) as users.
- Visit `/admin` on your deployed site → log in → you now have a dashboard to create/edit episodes.

## 5) Custom domain
- In Netlify **Domain settings**, add your domain (e.g., `insideropinion.in`).
- Update DNS as instructed.
- HTTPS auto-configures via Let's Encrypt.

## 6) Episode authoring
Each episode is a Markdown file in `content/episode/`. Front matter supports:
```yaml
title: "Your Episode Title"
date: 2025-10-01T10:00:00+05:30
description: "Short SEO description"
tags: ["AI", "India"]
audio: "https://your-cdn/audio.mp3"
youtube: "https://youtu.be/VIDEO_ID"
spotify: "https://open.spotify.com/episode/ID"
cover: "/images/og-default.jpg"
seo_title: "Custom SEO Title"
seo_description: "Custom SEO description"
```
Write transcripts and show notes in the Markdown body (great for SEO).

## 7) Google Analytics & Search Console
- In `config.toml`, set `googleAnalytics = "G-XXXXXXXXXX"`.
- Add your site to Google Search Console and submit the sitemap at `/sitemap.xml`.

## 8) Optional tweaks
- Update brand colors in `assets/css/custom.css`.
- Edit layouts in `layouts/_default/` for custom UI.
- Add more collections to `static/admin/config.yml` (e.g., "Guests").

---

**Made for Insider Opinion.** Fast, simple, and built for SEO.
