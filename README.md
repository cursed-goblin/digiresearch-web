# ZenvX DigiResearch — digiresearch.zenvx.in

Static website for **ZenvX DigiResearch**, a research-led digital marketing studio (website building + Meta ads).
No build step, no framework. Plain HTML, CSS and JS — upload the files anywhere.

## Pages

| File | Page |
| --- | --- |
| `index.html` | Home |
| `services.html` | Services + pricing |
| `method.html` | Our Method + free audit |
| `about.html` | About / team |
| `contact.html` | Contact + enquiry form |

Assets: `css/styles.css`, `css/bad.css`, `js/main.js`, `js/bad.js`, `assets/favicon.svg`, `robots.txt`, `sitemap.xml`.

## TWO FACES

The site ships with two complete looks. A button in the header switches between them.

1. **Good boy (default)** — minimal, light, fast, calm. Business-first.
2. **Bad boy** — dark "site of the day" mode: preloader, custom cursor, animated gradient blobs, grain, scroll progress bar, kinetic marquee, per-character heading reveals, glass cards, page-transition curtain.

### How it works

- The active face is stored in `localStorage` under **`zenvx-face`** (`good` or `bad`) and applied as `data-face` on `<html>`.
- A tiny inline script in `<head>` sets `data-face` **before paint**, so there is no flash of the wrong theme.
- `sessionStorage` key **`zenvx-seen`** makes the bad-boy preloader play only once per browser session.
- All bad-face styling lives in `css/bad.css` (scoped to `html[data-face="bad"]`) and all motion in `js/bad.js`.
- `prefers-reduced-motion` is respected: animations are disabled while the dark look is kept.
- Language toggle (EN / മലയാളം) works in both faces and is stored under `zenvx-lang`.

### Make bad boy the default

In the inline `<head>` script on each page, change:

```js
localStorage.getItem('zenvx-face') || 'good'
```

to:

```js
localStorage.getItem('zenvx-face') || 'bad'
```

### Remove the bad face entirely

Delete `css/bad.css` and `js/bad.js`, then remove from each page: the `bad.css` `<link>`, the inline `data-face` script, the `fx-*` divs right after `<body>`, the `<button class="face" ...>` in the header, and the `js/bad.js` `<script>` tag.

## Contact form (one thing to do before launch)

The form on `contact.html` posts to [Web3Forms](https://web3forms.com) and delivers to **sk@zenvx.in**.

1. Get a free access key from web3forms.com using that email address.
2. In `contact.html`, replace `PASTE_YOUR_WEB3FORMS_ACCESS_KEY_HERE` with your key.

Until then the form UI works but submissions will not be delivered. WhatsApp and email links work already.

## Deploy

Upload the repo contents to any static host (GitHub Pages, Netlify, Cloudflare Pages, cPanel) and point `digiresearch.zenvx.in` at it. `index.html` is the entry point.

After going live, update `sitemap.xml` dates if you change content.

## Contact

- Email: sk@zenvx.in
- WhatsApp: +91 94950 29709
- Instagram: [@zenvxdigiresearch](https://www.instagram.com/zenvxdigiresearch/)

© 2026 ZenvX DigiResearch · A ZenvX venture
