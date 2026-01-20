# Deployment Guide for Robotics Website

## Recommended: Vercel (Easiest for Static Sites)

### Option 1: Deploy via Vercel Dashboard (No Git Required)

1. **Sign up/Login to Vercel**
   - Go to: https://vercel.com
   - Sign up with GitHub, GitLab, or email

2. **Deploy**
   - Click "Add New Project"
   - Click "Browse" or drag and drop the `robotics website` folder
   - Vercel will auto-detect it's a static site
   - Click "Deploy"

3. **Custom Domain Setup**
   - After deployment, go to Project Settings → Domains
   - Add `xmachina.com` and `www.xmachina.com`
   - Vercel will show DNS records to add in GoDaddy:
     - **A Record**: `@` → Vercel IP (shown in dashboard)
     - **CNAME Record**: `www` → `cname.vercel-dns.com`
   - Add these records in GoDaddy DNS panel
   - Wait 24-48 hours for DNS propagation

### Option 2: Deploy via Git (Recommended for Updates)

1. **Create GitHub Repository**
   ```bash
   cd "/Users/niravdesai/robotics website"
   git init
   git add .
   git commit -m "Initial commit"
   # Create repo on GitHub and push
   ```

2. **Connect to Vercel**
   - Go to Vercel Dashboard
   - Click "Add New Project"
   - Import your GitHub repository
   - Vercel auto-detects settings
   - Click "Deploy"

3. **Auto-deployments**
   - Every push to main branch = automatic deployment
   - Preview deployments for pull requests

---

## Alternative: Netlify (Also Great)

### Deploy via Netlify Dashboard

1. **Sign up/Login**
   - Go to: https://www.netlify.com
   - Sign up with GitHub, GitLab, or email

2. **Deploy**
   - Drag and drop the `robotics website` folder
   - Netlify auto-deploys
   - Get instant URL: `your-site.netlify.app`

3. **Custom Domain**
   - Go to Site Settings → Domain Management
   - Add custom domain: `xmachina.com`
   - Netlify shows DNS records:
     - **A Record**: `@` → Netlify IP
     - **CNAME Record**: `www` → `your-site.netlify.app`
   - Add in GoDaddy DNS panel

---

## Google Cloud Run (If You Prefer GCP)

### Setup for Static Site

1. **Create a simple Dockerfile**
   ```dockerfile
   FROM nginx:alpine
   COPY index.html /usr/share/nginx/html/
   EXPOSE 80
   ```

2. **Deploy to Cloud Run**
   ```bash
   cd "/Users/niravdesai/robotics website"
   gcloud run deploy robotics-website \
     --source . \
     --region us-central1 \
     --allow-unauthenticated \
     --project your-project-id
   ```

3. **Map Custom Domain**
   ```bash
   gcloud run domain-mappings create \
     --service robotics-website \
     --domain xmachina.com \
     --region us-central1
   ```

4. **Update GoDaddy DNS**
   - Cloud Run will provide DNS records to add
   - Usually a CNAME record pointing to Cloud Run URL

**Note**: Cloud Run is overkill for static sites but works if you want everything in GCP.

---

## Comparison

| Feature | Vercel | Netlify | Cloud Run |
|---------|--------|---------|-----------|
| **Setup Time** | 2 minutes | 2 minutes | 10-15 minutes |
| **Free Tier** | ✅ Generous | ✅ Generous | ⚠️ Pay per use |
| **Custom Domain** | ✅ Free | ✅ Free | ✅ Free |
| **HTTPS** | ✅ Auto | ✅ Auto | ✅ Auto |
| **CDN** | ✅ Global | ✅ Global | ⚠️ Cloud CDN (extra) |
| **Best For** | Static sites, Next.js | Static sites, JAMstack | Containerized apps |

---

## My Recommendation: **Vercel**

**Why?**
- ✅ Fastest setup (literally 2 minutes)
- ✅ Best performance for static sites
- ✅ Free custom domain + SSL
- ✅ Great developer experience
- ✅ Easy updates (just push to Git)

**Steps:**
1. Go to https://vercel.com
2. Sign up/login
3. Drag and drop your `robotics website` folder
4. Add custom domain `xmachina.com`
5. Update GoDaddy DNS with records Vercel provides
6. Done! 🎉

---

## GoDaddy DNS Configuration (After Choosing Platform)

### For Vercel:
- **A Record**: `@` → `76.76.21.21` (or IP shown in Vercel dashboard)
- **CNAME Record**: `www` → `cname.vercel-dns.com`

### For Netlify:
- **A Record**: `@` → Netlify IP (shown in dashboard)
- **CNAME Record**: `www` → `your-site.netlify.app`

### For Cloud Run:
- **CNAME Record**: `@` → Cloud Run provided URL
- **CNAME Record**: `www` → Cloud Run provided URL

---

## Quick Start Commands

### Vercel CLI (Optional)
```bash
npm i -g vercel
cd "/Users/niravdesai/robotics website"
vercel
```

### Netlify CLI (Optional)
```bash
npm i -g netlify-cli
cd "/Users/niravdesai/robotics website"
netlify deploy --prod
```


