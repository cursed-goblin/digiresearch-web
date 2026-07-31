# ZenvX DigiResearch — digiresearch.zenvx.in

Static website for ZenvX DigiResearch. Plain HTML, CSS and JavaScript — no build step, no framework, no server code. Bilingual (English / Malayalam) with a toggle in the header.

## Pages

| File | Page |
| --- | --- |
| `index.html` | Home |
| `services.html` | Services — website building + Meta ads, pricing |
| `method.html` | Our Method + the free growth audit |
| `about.html` | About the studio |
| `contact.html` | Contact — enquiry form, WhatsApp, FAQ |

Supporting files: `css/styles.css`, `js/main.js`, `assets/favicon.svg`, `robots.txt`, `sitemap.xml`.

## 1. Make the contact form work (required)

The form posts to [Web3Forms](https://web3forms.com), which emails submissions to `sk@zenvx.in`.

1. Get a free Access Key at web3forms.com using `sk@zenvx.in` (confirm via the email they send).
2. In `contact.html`, find:

   ```html
   <input type="hidden" name="access_key" value="PASTE_YOUR_WEB3FORMS_ACCESS_KEY_HERE">
   ```

3. Replace the placeholder with your key, keeping the quotes.

Until this is done the form shows a "not connected yet" message instead of silently failing. After deploying, submit it once and check `sk@zenvx.in` (including spam the first time).

## 2. Deploy

**Cloudflare Pages / Netlify (easiest)**

1. Connect this repository, or drag the folder in as a manual deploy. No build command, no output directory.
2. Add the custom domain `digiresearch.zenvx.in`.
3. In the `zenvx.in` DNS, add the CNAME record they show you (`digiresearch` → their target).

**GitHub Pages**

Settings → Pages → Deploy from branch → `main` / root, then add `digiresearch.zenvx.in` as the custom domain.

**cPanel / shared hosting**

Create the `digiresearch` subdomain, upload everything into its folder keeping `css/`, `js/` and `assets/` as folders, and enable free SSL. `index.html` must sit at the site root.

## Editing quick reference

| What | Search for |
| --- | --- |
| WhatsApp number | `919495029709` |
| Email | `sk@zenvx.in` |
| Starting price | `1,999` |
| Instagram | `zenvxdigiresearch` |
| Footer year | `2026` |

Malayalam copy lives in `data-ml="..."` attributes beside each English string — read through these once and adjust anything that sounds off.

No analytics or tracking pixels are installed. To add any, paste the snippet before `</head>` in each page.

There is no portfolio page yet by design. When there are results worth showing, add a "Work" link to the nav in every page and a new page following the structure of `services.html`.
