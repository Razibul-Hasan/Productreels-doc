---
description: What data ProductReels uses and which external services it may contact.
---

# Privacy and external services

ProductReels does **not** send website or visitor information to ProductReels servers.

## Visitor data

* **View limiting:** to stop refreshes from inflating counts, visitor IP addresses are **temporarily hashed** with your WordPress salts. They are **not stored** in the analytics tables.
* **Analytics:** statistics store counts (views, clicks, orders, revenue) per reel and day, not personal profiles.
* **Public API:** the optional public endpoint returns reel and product information only, **never** anything about visitors or orders. You can turn it off in [Settings](settings.md#public-api).

## External services

Self-hosted videos (uploads and direct MP4/WebM links) do **not** need any external provider. The services below are contacted only if you use them, and their scripts load only when needed.

### Vimeo

* Adding a Vimeo URL may request video metadata (poster and duration) from `https://vimeo.com/api/oembed.json`, sending **only the submitted video URL**.
* Opening a Vimeo reel may load `https://player.vimeo.com/api/player.js`. Do Not Track is enabled where supported.
* [Vimeo terms](https://vimeo.com/terms) · [Vimeo privacy](https://vimeo.com/privacy)

You can disable the metadata lookup entirely with the [`productreels_allow_provider_lookup`](developers.md#filters) filter.

### YouTube

* Video thumbnails may be served from `https://img.youtube.com/vi/...`.
* Opening a YouTube reel may load `https://www.youtube.com/iframe_api`.
* [YouTube terms](https://www.youtube.com/t/terms) · [Google privacy policy](https://policies.google.com/privacy)

## Fonts and credits

The admin interface uses the **Inter** font (SIL OFL 1.1), shipped with the plugin and loaded only on ProductReels admin screens, never on your storefront. Icons are from Lucide (ISC) and drag-and-drop uses dnd-kit (MIT).

{% hint style="success" %}
**Need help with a privacy policy or consent setup for video providers?** Ask on [live chat](https://bestwebexpert.com/) or [hire BestWebExpert](https://bestwebexpert.com/).
{% endhint %}
