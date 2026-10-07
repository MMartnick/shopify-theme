# Concept 1984 Store — Shopify theme

Storefront for [Concept 1984](https://concept1984.com): prints, books and other
products by the artists the studio represents and produces. The look matches
the studio site (warm paper, key ink, CMYK accents, IBM Plex Sans KR / Mono).

## Structure

```
layout/theme.liquid            page shell, fonts, favicon, meta
sections/
  header.liquid                mark + nav (menu or Shop / Artists / Studio), studio IG, cart
  footer.liquid                store + studio links, studio IG
  store-intro.liquid           home intro plate
  featured-collection.liquid   product grid from any collection
  artists.liquid               artist directory (#artists)
  collection-template.liquid   product grid + artist/type filters + sort + pagination
  product-template.liquid      variant picker, add to cart (opens drawer)
  cart-drawer.liquid           AJAX cart (window.Cart.open / refresh)
  cart-template.liquid         /cart page
  page-template.liquid, 404-template.liquid
snippets/
  product-card.liquid          card with artist + product type
  artist-link.liquid           vendor -> artist collection (or vendor listing)
  meta-tags.liquid             Open Graph, Organization + Product JSON-LD
  icon.liquid                  inline SVG icons
```

## Store setup

**Artists are vendors.** Set each product's *Vendor* to the artist's name.
Product cards, product pages, the cart and structured data all read it.

**Artist pages.** Create a collection per artist named exactly like the vendor
(e.g. vendor `Jane Doe` → collection `Jane Doe`, handle `jane-doe`), with the
condition *Vendor is equal to Jane Doe*. Add a collection image and description
for the artist header. Every artist link points there; without the collection
it falls back to Shopify's automatic `/collections/vendors?q=` listing.

**Product types.** Set *Product type* (Poster, Book, Print, Apparel, …).

**Filters.** Install Shopify's **Search & Discovery** app and, under
*Filters*, add **Vendor** and **Product type** (optionally Availability and
Price). The collection page renders whatever filters are enabled there, with
live counts from the store; Vendor is labelled "Artist" and Product type
"Type". Filters only appear once enabled in the app.

**Home page.** In the theme editor, add an *Artist* block to the Artists
section for each artist (pick their collection, optional portrait, discipline
and bio). With no blocks, the section lists every vendor automatically.

**Navigation.** The header uses the `main-menu` menu; leave it empty to get
Shop / Artists / Studio. Studio Instagram is set under *Theme settings →
Social media* (default `@concept_1984`).

## Development

```bash
shopify theme dev --store your-store.myshopify.com
```

```bash
shopify theme push
```
