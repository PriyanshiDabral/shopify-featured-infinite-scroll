# shopify-featured-infinite-scroll
Shopify collection page with featured products + infinite scroll


# Shopify Featured Products + Infinite Scroll Collection

## Project Overview
This project is a Shopify collection page implementation that:
- Displays 100 products in a collection
- Pins 15 featured products at the top on default view
- Implements infinite scroll loading 20 products per request
- Supports sorting and filtering using Shopify native behavior
- Prevents duplicate products during pagination

---

## Tech Stack
- Shopify Liquid
- JavaScript (ES6)
- Shopify AJAX Cart & Collection API
- Custom Web Components

---

## Featured Product Logic
- Products with tag `featured` are separated on initial load
- All featured products are displayed at the top
- Remaining products are shown after featured products
- Featured logic is disabled when filter or sorting is applied

---

## Infinite Scroll Implementation
- Loads 20 products per request using Shopify pagination
- Uses scroll event / intersection observer
- Fetches next pages dynamically via AJAX
- Appends only non-duplicate products

---

## Duplicate Prevention
- Each product ID is tracked using a Set
- Prevents rendering same product multiple times across pages

---

## Sorting & Filtering Behavior
- When sorting or filtering is applied:
  - Shopify default behavior is used
  - Featured pinning is disabled
  - Ensures no conflict with Shopify backend logic

---

## Scalability
- Uses pagination instead of full collection load
- DOM updates are incremental
- Efficient for large collections (1000+ products)

---

## Limitations
- Featured ordering only applies to default view
- Shopify Liquid cannot persist custom JS sorting across filters
- Relies on frontend JS for post-processing

---

## How to Run
1. Upload theme to Shopify dev store
2. Open collection page
3. Scroll to trigger infinite loading
