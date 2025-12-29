# New Dawn Codex Setup Guide

This guide will help you get the New Dawn Codex up and running locally and deployed to Cloudflare Pages.

## Overview

The New Dawn Codex is a comprehensive wiki for an Ultima Online server, built with:
- **MkDocs** - Static site generator
- **Material for MkDocs** - Modern, feature-rich theme
- **Cloudflare Pages** - Free hosting with global CDN

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/markdwags/NewDawn-Codex.git
cd NewDawn-Codex
```

### 2. Install Python Dependencies

```bash
# Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### 3. Run Local Development Server

```bash
mkdocs serve
```

Open your browser to http://localhost:8000

The site will automatically reload when you edit files!

## Project Structure

```
NewDawn-Codex/
├── docs/                      # All markdown content
│   ├── index.md              # Home page
│   ├── getting-started/      # New player guides
│   ├── game-mechanics/       # Skills, combat, magic
│   ├── world/                # Towns, dungeons, geography
│   ├── items/                # Weapons, armor, resources
│   ├── community/            # Discord, contributing
│   ├── stylesheets/          # Custom CSS
│   └── _headers              # Cloudflare security headers
├── mkdocs.yml                # MkDocs configuration
├── requirements.txt          # Python dependencies
├── .gitignore               # Git ignore rules
├── README.md                # Project README
└── DEPLOYMENT.md            # Deployment instructions
```

## Content Editing

### Adding New Pages

1. Create a new `.md` file in the appropriate directory under `docs/`
2. Add the page to the navigation in `mkdocs.yml`
3. Write your content using Markdown
4. Test locally with `mkdocs serve`

### Markdown Syntax

The site supports extended Markdown features:

```markdown
# Main Heading
## Sub Heading

**Bold** and *italic* text
[Link text](url)

- Bullet lists
1. Numbered lists

!!! note "Callout Box"
    Important information here

!!! tip "Pro Tip"
    Helpful advice

!!! warning "Watch Out"
    Warnings

| Column 1 | Column 2 |
|----------|----------|
| Data     | Data     |
```

### Using Material Theme Features

**Admonitions (Callout Boxes):**
```markdown
!!! note
    Standard note

!!! tip
    Helpful tip

!!! warning
    Warning message

!!! danger
    Critical warning
```

**Grid Cards (Home page style):**
```markdown
<div class="grid cards" markdown>

-   :material-icon:{ .lg .middle } __Title__

    ---

    Description text

    [:octicons-arrow-right-24: Link](url)

</div>
```

## Building for Production

```bash
mkdocs build
```

This creates the `site/` directory with all static files ready for deployment.

## Deployment to Cloudflare Pages

### Initial Setup

1. **Sign up for Cloudflare** (free): https://dash.cloudflare.com/sign-up

2. **Connect GitHub Repository:**
   - Go to Workers & Pages
   - Click "Create application"
   - Select "Pages" tab
   - Click "Connect to Git"
   - Select your repository

3. **Configure Build Settings:**
   ```
   Framework preset: None
   Build command: pip install -r requirements.txt && mkdocs build
   Build output directory: site
   Root directory: (leave empty)
   ```

4. **Environment Variables:**
   ```
   PYTHON_VERSION = 3.11
   ```

5. **Custom Domain:**
   - Go to Custom domains in your project
   - Add `codex.uonewdawn.com`
   - Cloudflare will configure DNS automatically

### Automatic Deployments

After initial setup, every push to the main branch automatically:
1. Triggers a build on Cloudflare
2. Installs dependencies
3. Builds the static site
4. Deploys to the global CDN
5. Updates your site (usually takes 1-3 minutes)

### Preview Deployments

Pull requests automatically get preview URLs for testing changes before merging.

## Maintenance

### Updating Dependencies

```bash
pip install --upgrade mkdocs mkdocs-material pymdown-extensions
pip freeze > requirements.txt
```

### Testing Changes

Always test locally before pushing:

```bash
mkdocs serve
# Check the site at http://localhost:8000
# Make your changes
# Verify everything works
mkdocs build --strict  # Build with warnings as errors
```

## Troubleshooting

### Build Errors

**"Module not found"**
- Run `pip install -r requirements.txt`
- Check that you're in the virtual environment

**"Configuration error"**
- Check `mkdocs.yml` for syntax errors
- Ensure all paths in navigation exist

**"Broken links"**
- Use relative paths: `../page.md` not `/page.md`
- Verify linked files exist

### Deployment Issues

**Site not updating on Cloudflare**
- Check build logs in Cloudflare dashboard
- Verify build command is correct
- Check Python version is set to 3.11

**404 errors on pages**
- Ensure pages are in navigation
- Check that files were committed to Git
- Verify paths are correct in mkdocs.yml

## Getting Help

- 📖 [MkDocs Documentation](https://www.mkdocs.org/)
- 🎨 [Material Theme Docs](https://squidfunk.github.io/mkdocs-material/)
- 💬 [Discord Support](https://discord.gg/uonewdawn)
- 🐛 [Report Issues](https://github.com/markdwags/NewDawn-Codex/issues)

## Contributing

See [Contributing Guide](docs/community/contributing.md) for detailed information on how to contribute to the Codex.

Quick steps:
1. Fork the repository
2. Create a branch
3. Make your changes
4. Test locally
5. Submit a pull request

---

**Happy documenting! 📚**
