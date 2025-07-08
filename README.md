# GA4 + Shopify Tracking Setup

This repository accompanies the YouTube tutorial on how to set up GA4 tracking for Shopify stores using a custom pixel and Google Tag Manager.

> This setup is ideal for Shopify brands that want cleaner data and more control over ecommerce tracking than the default Google & YouTube app provides.

## 🧩 Overview

We cover:

- Setting up a Shopify custom pixel for GA4
- Importing a pre-configured GTM container with ecommerce tags and triggers
- Disabling duplicate tracking from Shopify's native GA4 integration

## 📁 Files

### `custom_pixel.js`
JavaScript for the Shopify Custom Pixel. Originally written by [Karol Krajcir](https://karolk.dev), shared with permission via [Analytics Mania](https://www.analyticsmania.com). We've customized it slightly to focus on ecommerce and pageview tracking.

### `gtm_container.json`
A pre-configured Google Tag Manager container export that includes:
- GA4 configuration tag (with `send_page_view: false`)
- Custom event tag for pageviews
- Purchase, add_to_cart, and other ecommerce events

> ⚠️ Be sure to update the GA4 Measurement ID inside GTM after importing.

## 🔧 Setup Instructions

### 1. Add the Custom Pixel
1. Go to Shopify Admin → Settings → Customer Events
2. Click "Add Custom Pixel"
3. Paste in the contents of `custom_pixel.js`
4. Save and enable the pixel

### 2. Import the GTM Container
1. In GTM, go to Admin → Import Container
2. Select `gtm_container.json`
3. Choose a new or existing workspace
4. Confirm the import

> Make sure you **update the GA4 Measurement ID** in the relevant tag.

### 3. Disable Native GA4 Tracking
1. In the GA4 interface → Admin → Data Streams → Enhanced Measurement → Disable
2. In Shopify Admin → Apps → Google & YouTube → Disconnect (if GA4 is auto-installed)

### 4. Test the Setup
- Use Chrome DevTools → Network tab to check `collect` requests
- GTM's preview mode will not show data from the custom pixel (Shopify sandboxes it)

## 🙏 Credits

- Code base by [Karol Krajcir](https://karolk.dev)
- Shared via [Analytics Mania](https://www.analyticsmania.com)
- Video Tutorial by Reese Garcia / https://www.youtube.com/@reeseagarcia

## 📄 License

GNU License
