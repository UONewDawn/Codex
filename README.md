# NewDawn-Codex

The comprehensive wiki and knowledge base for New Dawn, an Ultima Online server.

## Overview

This repository contains the source for the New Dawn Codex, built with [MkDocs](https://www.mkdocs.org/) and the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme.

**Live Site:** [https://codex.uonewdawn.com](https://codex.uonewdawn.com)

## Features

- 📚 Comprehensive game guides and documentation
- 🎨 Beautiful Material Design theme with dark mode
- 🔍 Full-text search functionality
- 📱 Fully responsive mobile design
- 🚀 Fast static site hosted on Cloudflare Pages
- ✏️ Easy to edit Markdown content

## Local Development

### Prerequisites

- Python 3.11 or higher
- pip (Python package manager)

### Setup

```bash
# Clone the repository
git clone https://github.com/markdwags/NewDawn-Codex.git
cd NewDawn-Codex

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Run Development Server

```bash
mkdocs serve
```

Then open [http://localhost:8000](http://localhost:8000) in your browser.

The site will automatically reload when you make changes to the documentation.

### Build for Production

```bash
mkdocs build
```

This generates the static site in the `site/` directory.

## Content Structure

```
docs/
├── index.md                    # Home page
├── getting-started/            # New player guides
│   ├── index.md
│   ├── new-player-guide.md
│   ├── character-creation.md
│   └── controls-interface.md
├── game-mechanics/             # Game systems
│   ├── index.md
│   ├── skills/
│   ├── stats.md
│   ├── combat.md
│   ├── magic.md
│   └── crafting.md
├── world/                      # World information
│   ├── index.md
│   ├── towns/
│   ├── dungeons/
│   └── geography.md
├── items/                      # Items & equipment
│   ├── index.md
│   ├── weapons.md
│   ├── armor.md
│   ├── resources.md
│   └── special-items.md
└── community/                  # Community resources
    ├── index.md
    ├── discord.md
    └── contributing.md
```

## Contributing

We welcome contributions! See [CONTRIBUTING.md](docs/community/contributing.md) for guidelines.

### Quick Contribution Guide

1. Fork the repository
2. Create a branch for your changes
3. Edit the Markdown files in `docs/`
4. Test locally with `mkdocs serve`
5. Submit a pull request

## Deployment

The site is automatically deployed to Cloudflare Pages when changes are pushed to the `main` branch.

See [DEPLOYMENT.md](DEPLOYMENT.md) for detailed deployment information.

### Cloudflare Pages Configuration

- **Build command:** `pip install -r requirements.txt && mkdocs build`
- **Build output directory:** `site`
- **Environment variable:** `PYTHON_VERSION=3.11`

## Technology Stack

- **[MkDocs](https://www.mkdocs.org/)** - Static site generator
- **[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)** - Theme
- **[Python Markdown Extensions](https://facelessuser.github.io/pymdown-extensions/)** - Enhanced Markdown features
- **[Cloudflare Pages](https://pages.cloudflare.com/)** - Hosting and CDN

## License

Content is provided as-is for the New Dawn community.

## Support

- 💬 [Discord](https://discord.gg/uonewdawn)
- 🐛 [Report Issues](https://github.com/markdwags/NewDawn-Codex/issues)
- 📖 [View Live Site](https://codex.uonewdawn.com)

---

Built with ❤️ for the New Dawn community
