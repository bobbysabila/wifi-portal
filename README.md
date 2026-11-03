# Capital Mining WiFi Portal

A clean, mobile-friendly login page for the Capital Mining guest and staff WiFi network.

**Live preview:** https://bobbysabila.github.io/wifi-portal/

![Capital Mining WiFi portal screenshot](screenshot.png)

## Features

- Single self-contained `index.html`. No build step, no external fonts, scripts or images.
- Works before login: nothing is loaded from the internet, so it is safe to serve from a captive portal.
- Mobile-first card layout with large tap targets.
- Username and password fields with show/hide password.
- Inline validation, loading state and a "You're connected" confirmation.
- Keyboard accessible, with visible focus and reduced-motion support.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The complete login page, with the company logo embedded. |
| `README.md` | This document. |
| `screenshot.png` | Preview image shown above. |

## Connecting it to your gateway

The page currently runs as a demo: it validates the fields and then shows a success message. To make it a working login, replace the `setTimeout` block at the bottom of `index.html` with a request to your gateway's login endpoint.

Typical set-ups:

1. **Upload to the router.** Copy `index.html` to the gateway's hotspot or portal folder (for example, MikroTik `hotspot/login.html`).
2. **Host externally.** Serve the page from GitHub Pages and add `bobbysabila.github.io` to the gateway's pre-login allow list (walled garden), so devices can load it before signing in.

Keep the form field names `username` and `password` unless your gateway requires different ones.

## Customising

All styling is in the `<style>` block at the top of `index.html`. Brand colours are defined as CSS variables under `:root`:

```css
--yellow: #ffe600;
--red:    #d9291c;
--ink:    #16140d;
```

To change the logo, replace the base64 image in the `<img class="logo">` tag with your own.

## Local preview

Open `index.html` in any browser. No server is needed.

## Ownership

Maintained by Capital Mining IT. The Capital Mining name and logo are company property and are not licensed for reuse.
