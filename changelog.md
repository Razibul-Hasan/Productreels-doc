---
description: Release notes for ProductReels.
---

# Changelog

## 1.1.4

* Hardened database queries: table names go through `$wpdb->prepare()` with the `%i` identifier placeholder, and every query is built from literal SQL (WordPress Plugin Check clean).
* The readme title now matches the plugin name: "ProductReels – Shoppable Video Reels for WooCommerce".

## 1.1.3

* Replaced the Halloween notice with a dismissible Black Friday notice on the Widgets screen, shown only to administrators until December 31, 2026.

## 1.1.2

* Added a "Hire an expert" link to the ProductReels admin bar for custom website work.
* Added a dismissible Halloween notice on the Widgets screen, shown only to administrators until October 31, 2026.

## 1.1.1

* Added automatic product-page placement and current-product reels, with fallback videos.
* Added `[productreels]` product targeting and sales attribution with date-range reports.
* Fixed view and click tracking for reels selected by current product.

## 1.1.0

* Redesigned admin, live widget editor and responsive previews.
* Added video cover selection, upload progress, reel filters and product search.
* Improved storefront styling, accessibility, translations and mobile layouts.

## 1.0.0

* Initial release.

{% hint style="info" %}
**Upgrading?** Your existing reels, widgets and settings are preserved across updates. Version 1.1.1 added two database tables; existing data is kept.
{% endhint %}

{% hint style="success" %}
### Need help? Chat live or hire an expert

Our team at BestWebExpert is ready to help: **[start a live chat](https://bestwebexpert.com/)** or **[hire BestWebExpert](https://bestwebexpert.com/)** to set up, style or extend ProductReels for you.
{% endhint %}
