# Matt Martnick Art Shop - Shopify Theme

A custom Shopify theme matching the portfolio site at matthewmartnick.com.

## Theme Structure

```
shopify-theme/
├── assets/
│   └── base.css              # All theme styles
├── config/
│   ├── settings_schema.json  # Theme customizer options
│   └── settings_data.json    # Default settings
├── layout/
│   └── theme.liquid          # Main layout wrapper
├── sections/
│   ├── header.liquid         # Site header & nav
│   ├── footer.liquid         # Site footer
│   ├── cart-drawer.liquid    # Slide-out cart
│   ├── collection-template.liquid
│   ├── product-template.liquid
│   ├── cart-template.liquid
│   ├── featured-collection.liquid
│   ├── page-template.liquid
│   └── 404-template.liquid
├── snippets/
│   └── product-card.liquid   # Reusable product card
└── templates/
    ├── index.json            # Homepage
    ├── collection.json       # Collection pages
    ├── product.json          # Product pages
    ├── cart.json             # Cart page
    ├── page.json             # Generic pages
    └── 404.json              # 404 page
```

## How to Connect to Shopify via GitHub

### Step 1: Push to GitHub
Make sure your repo (including the `shopify-theme` folder) is pushed to GitHub.

### Step 2: Connect in Shopify
1. In Shopify Admin, go to **Online Store → Themes**
2. Click **Add theme → Connect from GitHub**
3. Authorize Shopify to access your GitHub account
4. Select your repository
5. Choose the `shopify-theme` folder as the theme root
6. Click **Connect**

### Step 3: Publish
Once connected, Shopify will sync the theme. You can then:
- Click **Publish** to make it live
- Any push to the connected branch will auto-update the theme

## Customization

### Colors
Edit `config/settings_data.json` or use the Theme Customizer:
- Background: `#111111`
- Secondary: `#1a1a1a`
- Text: `#e5e5e5`
- Muted: `#888888`
- Border: `#333333`

### Navigation Links
Edit `sections/header.liquid` to update navigation links to your portfolio.

### Social Links
Update social URLs in:
- `sections/header.liquid`
- `sections/footer.liquid`
- Or via Theme Customizer settings

## Features

- ✓ Dark theme matching portfolio
- ✓ Responsive design (mobile drawer menu)
- ✓ Product grid with hover effects
- ✓ Slide-out cart drawer
- ✓ Product page with image gallery
- ✓ Cart page
- ✓ Collection pages with pagination
- ✓ Inter font (matches portfolio)
- ✓ Font Awesome icons
