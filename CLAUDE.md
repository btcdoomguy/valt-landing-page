# CLAUDE.md

This file provides guidance to Claude Code when working with the Valt landing page.

## Project Overview

Static landing page for Valt (personal budget management app for bitcoiners), built with Jekyll for GitHub Pages. Supports English and Portuguese languages.

## URLs

- **Live site**: https://valtapp.com
- **Repository**: https://github.com/btcdoomguy/valt-landing-page
- **Main app repo**: https://github.com/btcdoomguy/valt

## Build and Run Commands

```bash
# Install dependencies
bundle install

# Run locally (access at http://localhost:4000/)
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

Note: Ruby 4.0.0 requires extra gems in Gemfile (logger, csv, base64, bigdecimal, ostruct).

## Project Structure

```
valt-landing-page/
├── _config.yml              # Jekyll config (custom domain: valt.app)
├── _data/
│   ├── en.yml               # English translations
│   └── pt-br.yml            # Portuguese translations
├── _includes/
│   ├── header.html          # Navigation with language switcher
│   ├── footer.html          # Footer (by @BtcChicoFatal)
│   └── download-script.html # GitHub releases API integration
├── _layouts/
│   └── default.html         # Base template (loads Geist Mono font)
├── assets/
│   ├── css/style.css        # Main stylesheet (Valt app colors)
│   └── images/
│       ├── valt-logo.png    # App logo (copied from main repo)
│       └── screenshots/     # Add screenshots here
├── en/index.html            # English homepage
├── pt-br/index.html         # Portuguese homepage
├── index.html               # Root redirect (auto-detects browser language)
└── Gemfile                  # Ruby dependencies
```

## Key Features

### Multilingual Support
- English: `_data/en.yml` and `en/index.html`
- Portuguese: `_data/pt-br.yml` and `pt-br/index.html`
- Language switcher in header
- Root index auto-redirects based on browser language

### Design System
- **Font**: Geist Mono (loaded from jsDelivr CDN)
- **Colors** (from Valt app's ColorResources.axaml):
  - Primary/Accent: `#ffa122` (orange)
  - Background: `#1a1a1a`, `#333333`, `#262626`
  - Text: `#fdfdfc`, `#a8a6a4`
  - Borders: `#3b342b`

### Dynamic Download Links
- `_includes/download-script.html` fetches latest release from GitHub API
- Buttons have `data-platform="windows|linux|macos"` attributes
- Script auto-detects assets by filename patterns
- Falls back to releases page if no matching assets found

## Content Sections

1. **Hero** - Main tagline and CTA buttons
2. **Features** - 8 feature cards highlighting:
   - Privacy (local data, no cloud)
   - Open source & free
   - Account/transaction management
   - Fixed expenses tracking
   - Average price tracking
   - Multiple currencies
   - Bitcoin-denominated view
   - Cross-platform support
3. **Screenshots** - Placeholder grid (add images to `assets/images/screenshots/`)
4. **Download** - Platform buttons with GitHub releases integration

## Adding Screenshots

1. Add images to `assets/images/screenshots/`
2. Edit `en/index.html` and `pt-br/index.html`
3. Replace placeholder divs:
```html
<!-- Replace this -->
<div class="screenshot-placeholder">Screenshot: Dashboard</div>

<!-- With this -->
<img src="{{ '/assets/images/screenshots/dashboard.png' | relative_url }}" alt="Dashboard">
```

## Updating Content

- **Text changes**: Edit `_data/en.yml` or `_data/pt-br.yml`
- **Styling**: Edit `assets/css/style.css`
- **Layout**: Edit files in `_layouts/` and `_includes/`
- **Logo**: Replace `assets/images/valt-logo.png`

## Important Notes

- Custom domain: valtapp.com (baseurl is empty)
- Internal links use `| relative_url` filter
- Footer credits @BtcChicoFatal
- GitHub API has rate limits; download script handles failures gracefully
