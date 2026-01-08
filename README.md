# Valt Landing Page

A static landing page for the Valt personal budget management application, built with Jekyll for GitHub Pages.

## Features

- Multilingual support (English and Portuguese)
- Responsive design (mobile-friendly)
- Dark theme with Bitcoin-inspired accent colors
- Automatic language detection and redirect
- SEO optimized

## Local Development

### Prerequisites

- Ruby 2.7+ with Bundler
- Jekyll 4.3+

### Setup

```bash
# Install dependencies
bundle install

# Start local server
bundle exec jekyll serve

# Visit http://localhost:4000
```

## Deploying to GitHub Pages

1. Create a new repository on GitHub (e.g., `valt-landing-page` or `valt`)
2. Push this directory to the repository
3. Go to repository Settings > Pages
4. Select "Deploy from a branch" and choose `main` branch
5. Your site will be available at `https://yourusername.github.io/repository-name/`

### Custom Domain (Optional)

1. Add a `CNAME` file with your domain name
2. Configure DNS settings with your domain provider

## Customization

### Adding Screenshots

1. Add your screenshots to `assets/images/screenshots/`
2. Update the HTML in `en/index.html` and `pt-br/index.html`
3. Replace the placeholder divs with actual `<img>` tags

Example:
```html
<!-- Replace this -->
<div class="screenshot-placeholder">
  Screenshot: Dashboard
</div>

<!-- With this -->
<img src="/assets/images/screenshots/dashboard.png" alt="Dashboard">
```

### Updating Content

- **English text**: Edit `_data/en.yml`
- **Portuguese text**: Edit `_data/pt-br.yml`

### Styling

- Main stylesheet: `assets/css/style.css`
- Uses CSS custom properties for easy theming

### GitHub Repository Links

Update the GitHub links in:
- `_includes/header.html` - Main navigation
- `_includes/footer.html` - Footer links
- `en/index.html` and `pt-br/index.html` - Download buttons

Replace `btcdoomguy/valt` with your actual repository path.

## Structure

```
valt-landing-page/
├── _config.yml          # Jekyll configuration
├── _data/
│   ├── en.yml           # English translations
│   └── pt-br.yml        # Portuguese translations
├── _includes/
│   ├── header.html      # Site header/navigation
│   └── footer.html      # Site footer
├── _layouts/
│   └── default.html     # Main layout template
├── assets/
│   ├── css/
│   │   └── style.css    # Main stylesheet
│   └── images/
│       ├── favicon.svg
│       └── screenshots/ # Add screenshots here
├── en/
│   └── index.html       # English homepage
├── pt-br/
│   └── index.html       # Portuguese homepage
├── index.html           # Root redirect
├── Gemfile              # Ruby dependencies
└── README.md            # This file
```

## License

MIT License - Same as the Valt project
