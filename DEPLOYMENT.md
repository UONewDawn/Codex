# Cloudflare Pages Deployment

This document explains how to deploy the New Dawn Codex to Cloudflare Pages.

## Overview

The codex is built with MkDocs and Material theme, and deployed as a static site on Cloudflare Pages.

## Cloudflare Pages Setup

### Prerequisites

1. Cloudflare account
2. Domain configured in Cloudflare (codex.uonewdawn.com)
3. GitHub repository connected to Cloudflare Pages

### Deployment Configuration

In Cloudflare Pages dashboard:

**Build Configuration:**
- **Framework preset:** None
- **Build command:** `pip install -r requirements.txt && mkdocs build`
- **Build output directory:** `site`
- **Root directory:** (leave empty)

**Environment Variables:**
- **PYTHON_VERSION:** `3.11`

### Custom Domain

1. Go to Cloudflare Pages project
2. Navigate to "Custom domains"
3. Add `codex.uonewdawn.com`
4. DNS will be configured automatically

## Local Development

### Setup Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### Run Development Server

```bash
mkdocs serve
```

Visit `http://localhost:8000` to view the site.

### Build for Production

```bash
mkdocs build
```

This creates the `site/` directory with static files.

## Automatic Deployment

Cloudflare Pages automatically deploys when:

1. **Push to main branch:** Triggers production deployment
2. **Pull request:** Creates preview deployment
3. **Manual trigger:** From Cloudflare dashboard

## Deployment Process

When you push to GitHub:

1. Cloudflare detects the push
2. Runs build command
3. Installs Python dependencies
4. Builds MkDocs site
5. Deploys to CDN
6. Updates codex.uonewdawn.com

Deployment typically takes 1-3 minutes.

## Preview Deployments

Pull requests automatically get preview URLs:
- Unique URL for each PR
- Test changes before merging
- Share with team for review

## Troubleshooting

### Build Fails

**Check:**
- requirements.txt is valid
- Python version is correct
- No syntax errors in mkdocs.yml
- All markdown files are valid

### Site Not Updating

**Try:**
- Clear Cloudflare cache
- Force rebuild in dashboard
- Check deployment logs
- Verify build completed successfully

### Custom Domain Issues

**Verify:**
- DNS records are correct
- SSL certificate is active
- Domain is added in Cloudflare Pages
- Propagation completed (can take up to 24h)

## Performance Optimization

### Cloudflare Features

Enable in Cloudflare dashboard:

- **Auto Minify:** HTML, CSS, JS
- **Brotli Compression:** Better than gzip
- **Rocket Loader:** JS optimization
- **Image Optimization:** Auto-optimize images

### CDN Caching

Cloudflare automatically caches:
- All static assets
- HTML pages
- Images and files

Cache is purged on each deployment.

## Monitoring

### Analytics

View in Cloudflare Pages:
- Page views
- Unique visitors
- Bandwidth usage
- Geographic distribution

### Deployment History

Track in dashboard:
- All deployments
- Build logs
- Deploy time
- Commit information

## Rollback

To rollback to previous version:

1. Go to deployment history
2. Find working deployment
3. Click "Rollback to this deployment"
4. Confirm rollback

## Security

### HTTPS

- Automatic HTTPS enabled
- HTTP automatically redirects to HTTPS
- Free SSL certificate from Cloudflare

### Security Headers

Cloudflare automatically adds:
- X-Content-Type-Options
- X-Frame-Options
- X-XSS-Protection

## Cost

Cloudflare Pages Free Tier includes:
- Unlimited sites
- Unlimited requests
- Unlimited bandwidth
- 500 builds per month

New Dawn Codex should stay well within free tier limits.

## Support

For deployment issues:
- Check Cloudflare Pages documentation
- Review build logs
- Ask in Discord #tech-support
- Open GitHub issue

---

**The codex will be live at https://codex.uonewdawn.com after setup!**
