---
description: Shortcodes, the block, the REST endpoint, hooks and database tables.
---

# Developer reference

Everything below is stable, public surface you can build on. All hooks are prefixed `productreels_`.

## Shortcodes

| Shortcode | Attributes | Output |
| --- | --- | --- |
| `[productreels]` | `id` (required), `product` (optional product ID) | A widget. |
| `[productreels_reel]` | `id` (required) | A single reel without widget chrome. |

The shortcodes print a lightweight mount node. A script then paints the widget from the REST payload, which is the **same data the editor preview uses**, so the preview and the live site can never disagree.

## Gutenberg block

| | |
| --- | --- |
| Block name | `productreels/reels` |
| Category | Widgets |
| Attribute | `widgetId` (string) |
| Supports | `align` (wide, full) and margin spacing |

```html
<!-- wp:productreels/reels {"widgetId":"1"} /-->
```

## REST API

Base namespace: `/wp-json/productreels/v1/`

| Route | Access | Notes |
| --- | --- | --- |
| `GET /render/{id}` | Public (see **Allow public fetch** in [Settings](settings.md#public-api)) | Returns the widget payload: reel titles, video and cover links, view counts and product links. Never visitor or order data. |

Admin routes for reels, widgets, products, settings, statistics and tracking require a user who can manage ProductReels and a valid REST nonce.

## Actions

| Hook | Fires when |
| --- | --- |
| `productreels_reel_created` | A reel is created. Receives the reel ID. |
| `productreels_reel_updated` | A reel is updated. |
| `productreels_reel_deleted` | A reel is deleted. |
| `productreels_widget_created` | A widget is created. Receives the widget ID. |
| `productreels_widget_updated` | A widget is updated. |
| `productreels_widget_deleted` | A widget is deleted. |
| `productreels_settings_updated` | Settings are saved. Receives the saved settings. |
| `productreels_view_tracked` | A view is counted. |
| `productreels_click_tracked` | A click is counted. |
| `productreels_activated` / `productreels_deactivated` | The plugin is activated or deactivated. |
| `productreels_rest_routes_registered` | ProductReels REST routes are registered. |

## Filters

| Filter | Purpose |
| --- | --- |
| `productreels_allow_provider_lookup` | Return `false` to stop ProductReels from requesting Vimeo video metadata (poster and duration). See [Privacy](privacy.md). |

```php
// Never contact Vimeo for video metadata.
add_filter( 'productreels_allow_provider_lookup', '__return_false' );
```

```php
// Example: log every new reel.
add_action( 'productreels_reel_created', function ( $reel_id ) {
	error_log( 'New ProductReels reel: ' . $reel_id );
} );
```

## Database tables

ProductReels creates seven tables, each prefixed with your WordPress table prefix (usually `wp_`):

| Table | Holds |
| --- | --- |
| `productreels_widgets` | Widgets and their style settings. |
| `productreels_reels` | Reels: title, cover, buttons and products, view count. |
| `productreels_widget_reels` | Which reels belong to which widget, and their order. |
| `productreels_files` | The video files and sources attached to each reel. |
| `productreels_clicks` | Click counts per button. |
| `productreels_daily` | Views and clicks per day, for date ranges. |
| `productreels_sales` | Paid order lines linked to a reel. |

Plugin settings are stored in the `productreels_settings` option. See [Settings → Data](settings.md#data) for what happens on uninstall.

## Source code

Readable JS, JSX and SCSS sources ship with the plugin in `admin/src`, `public/src`, `block/src` and `src/shared`. Build instructions are in the plugin's `README.md`.

{% hint style="success" %}
### Need help? Chat live or hire an expert

Our team at BestWebExpert is ready to help: **[start a live chat](https://bestwebexpert.com/)** or **[hire BestWebExpert](https://bestwebexpert.com/)** to set up, style or extend ProductReels for you.
{% endhint %}
