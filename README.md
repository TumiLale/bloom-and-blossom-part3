# Bloom and Blossom

Website for **Bloom and Blossom**, a flower boutique situated in Johannesburg and Menlyn.
Built for the WEDE5020 Portfolio of Evidence (POE) at The Independent Institute of Education.

- **Live site:** https://YOUR-USERNAME.github.io/bloomandblossom/ *(replace after deploying)*
- **Repository:** https://github.com/YOUR-USERNAME/bloomandblossom *(replace)*

## Pages

| Page | File | Purpose |
|------|------|---------|
| Home | `index.html` | Welcome page with four featured bouquet photos and links to the main sections |
| About Us | `about.html` | Business story and a detailed "Where to find us" tab for both locations (jQuery tabs) |
| Services | `services.html` | Photo gallery with lightbox, searchable product list, ordering FAQ (jQuery accordion) |
| Enquiries | `enquiries.html` | Validated enquiry form with confirmation modal |
| Contact | `contact.html` | Two separate interactive Leaflet maps (Johannesburg and Menlyn), phone, WhatsApp and social links, and a "Send us a message" form |

## Folder structure

```
bloomandblossom/
  index.html, about.html, services.html, enquiries.html, contact.html
  README.md
  _images/            photos and icons
  css_assets/
    myfirststyles.css the only stylesheet (all pages)
  js_assets/
    main.js           scroll animation (all pages)
    about.js          tabs
    lightbox.js       image viewer
    services.js       product list, search/filter/sort, accordion
    enquiries.js      form validation, modal, WhatsApp link
    contact.js        the two Leaflet maps
    contactform.js    message form validation and modal (Contact page)
    jquery-3.7.1.min.js
    leaflet/          Leaflet 1.9.4 (js, css, marker images)
```

jQuery and Leaflet are stored in the project instead of loaded from a CDN. This keeps the site fast,
works offline and means no third-party scripts can be swapped in (see Security).

## Part 3 features

**JavaScript**
- Tabs (About) and accordion (Services) using jQuery.
- Two separate interactive maps (one for Johannesburg, one for Menlyn) using Leaflet and OpenStreetMap (Contact). Each has links to open the place in Google Maps and to get directions (Google, 2026a).
- CSS animations and transitions: page title slide-in, scroll fade-in (JavaScript), hover and focus transitions. Animations switch off for visitors who prefer reduced motion.
- DOM manipulation: product cards, lightbox and tabs are created in JavaScript; the enquiry form reads `?flower=` from the URL; the confirmation modal is filled in from the form.
- Gallery with lightbox (click, arrow keys, Escape).
- Dynamic content: the Services page builds its product cards from a list in `services.js`, with search, colour and type filters and sorting.

**Forms (two):**
1. *Enquiries page:* name, phone, email, flower type, collection location (radio buttons) and optional message.
2. *Contact page, "Send us a message":* name, email, occasion (drop-down), optional date (past dates blocked), how we should reply (radio buttons) and a message of 10 to 500 characters.

JavaScript checks each field in both forms and shows a message under the field. The site has no server, so a valid form opens a modal where the visitor sends it on WhatsApp.

**SEO** (based on Google, 2026b)
- Keyword research: *flower boutique Johannesburg*, *flower boutique Menlyn*, *rose bouquets*, *red rose bouquet*, *pink rose bouquet*, *tulips bouquet*, *order flowers Pretoria*. These are used in titles, meta descriptions, headings, alt text and link text.
- Unique `<title>` and meta description on every page; Open Graph tags for social sharing.
- One `h1` per page with `h2`/`h3` below it; descriptive alt text on every image; descriptive file names (`redandpinkbouquet.jpg`, `tulips.avif`).
- Clean URLs (short lowercase file names) and internal links between pages in the page text and footer.
- Mobile-friendly: viewport tag plus tablet and smartphone media queries.
- Local SEO: `Florist` structured data (JSON-LD; Schema.org, 2026) with phone number, areas served and social profiles.
- Off-page SEO (cannot be done in code, planned): list the business on Google Business Profile for both locations, link to the site from the Instagram and TikTok bios, and ask local suppliers/wedding vendors to link to it.

**Page speed:** logo reduced from 2000 x 2000 px to 400 x 400 px (108 KB to 25 KB), `loading="lazy"` and `decoding="async"` on gallery images, width/height set on images, no external libraries to download.

**Security:** Content Security Policy on every page (Mozilla Contributors, 2026o) (scripts only from this site), referrer policy, `rel="noopener noreferrer"` on external links, no user text inserted with `innerHTML` (JavaScript uses `textContent`), form input validated before use. Serve the site over HTTPS (GitHub Pages and Netlify do this automatically).

## Running the site locally

Open the folder in VS Code and start Live Server, or double-click `index.html`.

## Deploying (GitHub Pages)

1. Push the project to a GitHub repository.
2. Repository **Settings > Pages**, choose the `main` branch and the root folder, then save.
3. Copy the live address into the links at the top of this README (replace `YOUR-USERNAME`).

## What Part 2 delivered (the starting point for Part 3)

This is what the site looked like when Part 3 started, so every change below can be traced back to it.

- Five pages (`index.html`, `about.html`, `services.html`, `enquiries.html`, `contact.html`) sharing one external stylesheet, `css_assets/myfirststyles.css`.
- A logo and an ordered-list menu on every page.
- Default styles, typography and colour for the page, plus the classes `.responsive-image` and `.container` (created but not yet used in the HTML).
- Media queries at 600px and 300px that only changed the page background colour.
- Two Google Maps iframes on the Contact page and a basic enquiries form with no submit button.
- No JavaScript, no README and no changelog.

Part 2 marks were lost on: using Part 1 feedback (changelog), pseudo-classes, media queries, responsive layout, typography, navigation menu, images, README, changelog and references. Every one of these is dealt with in the changelog below (entries 1 to 9).

## Changelog

All edits made in Part 3 (30 October 2026). The "Reason" column links each edit to the feedback received.

### Feedback from Part 2 (formative 2, 53/100)

| # | File(s) | Change | Reason |
|---|---------|--------|--------|
| 1 | `css_assets/myfirststyles.css` | Menu selectors changed from `nav ul` to `nav ol` (the HTML uses `<ol>`). Menu is now a horizontal flex row. | Navigation styling was never applied; Part 2 "Navigation Menu" adjustments 0/5 |
| 2 | `css_assets/myfirststyles.css` | Menu link colour changed from antiquewhite to dark pink `#7a1f57` so it can be read on the pink background. | Text was almost invisible; readability |
| 3 | `css_assets/myfirststyles.css` | Pseudo-classes corrected: `:hover`, `:focus`, `:active`, `:visited`, `:focus-visible` on menu links, buttons, form fields and cards. The old hover (bisque text on antiquewhite) was unreadable. | Part 2 "Pseudo-classes used incorrectly" 5/10 |
| 4 | `css_assets/myfirststyles.css` | Media queries rebuilt. Breakpoints are now 768px (tablet) and 480px (smartphone) instead of 600px and 300px. Original background colours kept. Added: smaller headings, 2-column then 1-column card grid, stacked menu, smaller logo and gallery images, smaller map. | Part 2 "Layout" and "Typography" adjustments 0/5 and "Media Queries" 5/10 |
| 5 | `css_assets/myfirststyles.css` | Added base typography on `body` (font family, size, line height, colour) and `p`, `h3` spacing; heading and body sizes shrink on small screens. | Part 2 "Typography adjustments" 0/5 |
| 6 | all `.html` files | `class="responsive-image"` added to every content image (logo and icons included). | Feedback: "Class created but not implemented"; Part 2 "Images" adjustments 2/5 |
| 7 | `services.html`, `css_assets/myfirststyles.css` | `.container` class now used for the product card grid. Fixed `padding: 20` (no unit, ignored) to `20px`, and card text colour from bisque to dark so it is readable. | Feedback: "Class created but not implemented" |
| 8 | all `.html` files | Added comments to the HTML, CSS and JavaScript explaining each Part 3 change. | Part 1 "Comments" 0/5 |
| 9 | `README.md` | README rewritten: description, pages, folder structure, features, deployment, changelog and references. | Part 2 README 3/5; Part 2 Changelog 0/5; Part 2 References 0/5 |

### Feedback from Part 1 (formative 1, 66/100)

| # | File(s) | Change | Reason |
|---|---------|--------|--------|
| 10 | all `.html` files | Page content moved out of `<header>` into `<main>`; `<footer>` added. `<header>` now only holds the logo, menu and h1. `index.html` also gained a `<header>`. | Part 1 "HTML Structure: Tags for Layout" 5/10 (semantic elements) |
| 11 | `index.html` | Tagline changed from `<h3>` to `<h2>` (class `tagline` keeps the same size). | Correct heading order (h1 then h2) for structure and SEO |
| 12 | all `.html` files | Fixed the `<link rel="stylesheet">` tag, which was missing its closing `>` and was swallowing the `<title>` tag. | Pages had no real title; stylesheet link was malformed |
| 13 | `index.html` | Menu link `href="contact"` fixed to `contact.html` and the missing `</li>` added. | Broken link on the home page; Part 1 "Menu/Links" |
| 14 | `contact.html` | The social/phone list items were not inside a list; wrapped in `<ul class="contact-list">`. Icons given alt text, width and height. | Invalid HTML; image alt text |

### New in Part 3

| # | File(s) | Change | Reason |
|---|---------|--------|--------|
| 15 | `about.html`, `js_assets/about.js` | Existing about text split into two jQuery tabs ("Our story", "Where to find us"). Wording unchanged. | Part 3 2.1 Interactive elements |
| 16 | `services.html`, `js_assets/services.js` | Added accordion with three ordering questions. | Part 3 2.1 Interactive elements |
| 17 | `services.html`, `js_assets/lightbox.js`, `js_assets/services.js` | The four existing photos became a gallery; each opens in a lightbox. Alt text rewritten to describe each photo. | Part 3 2.1 Gallery with lightbox; SEO image optimisation |
| 18 | `services.html`, `js_assets/services.js` | Added "Find your flowers": six product cards built in JavaScript with search box, colour filter, type filter and sort. "View photo" opens the lightbox; "Enquire" links to the form. | Part 3 2.2 Dynamic content and search |
| 19 | `contact.html`, `js_assets/contact.js`, `js_assets/leaflet/` | The two Google Maps iframes were replaced with Leaflet maps. (Updated in entry 34: now two separate maps.) The same two places (Midrand, Johannesburg and Menlyn, Pretoria) are used. | Part 3 2.1 Interactive maps |
| 20 | `css_assets/myfirststyles.css`, `js_assets/main.js` | Added title slide-in animation, scroll fade-in, and hover/focus transitions on links, cards, buttons and gallery. Reduced-motion setting respected. | Part 3 2.1 Animations and transitions |
| 21 | `enquiries.html` | Form fixed and completed: `<lable>` typo corrected, `<select>` closed, `<br></br>` removed, labels connected to inputs with `for`/`id`, submit and reset buttons added. Added email, collection location (radio buttons) and message fields, and a first "Please choose..." option. Option names kept. | Form was incomplete (no submit button); Part 3 forms outcome |
| 22 | `js_assets/enquiries.js` | JavaScript validation: name (letters only, min 2), South African phone number, email format, flower and location required. Messages appear under each field and the first error gets focus. Message box has a character counter. | Part 3 JavaScript validation |
| 23 | `enquiries.html`, `js_assets/enquiries.js` | jQuery modal shows the enquiry summary after a valid submit, with a "Send on WhatsApp" button (message prefilled). The form also reads `?flower=` from the URL so "Enquire" on a product card pre-selects it. | Part 3 modals and DOM manipulation. The site has no server, so WhatsApp delivers the enquiry |
| 24 | all `.html` files | Unique title tag and meta description per page, Open Graph tags and author tags. | Part 3 3.1 Title tags and meta descriptions |
| 25 | `index.html` | Added `Florist` JSON-LD structured data. | Part 3 3.2 Local SEO |
| 26 | `index.html`, `about.html`, `services.html`, `enquiries.html`, `contact.html` | Added links between pages inside the page text and a footer with links and phone number. | Part 3 3.1 Internal linking |
| 27 | `_images/businesslogo.png` | Reduced from 2000 x 2000 px to 400 x 400 px; same file name. | Part 3 3.3 Page speed |
| 28 | `services.html` | `loading="lazy"` and `decoding="async"` added to gallery images. | Part 3 3.3 Page speed |
| 29 | all `.html` files | Content Security Policy and referrer policy meta tags; `rel="noopener noreferrer"` on external links. | Part 3 3.3 Security |
| 30 | `js_assets/` | jQuery 3.7.1 and Leaflet 1.9.4 stored locally. | Page speed and security (no third-party scripts) |
| 31 | `index.html`, `css_assets/myfirststyles.css` | Added an "Our favourite bouquets" section to the home page with four photos that already existed in `_images` (redandpinkbouquet, tulips, redonlybouquet, pinkbouquet). Each photo links to the Services page; there is also a "See all our bouquets" button. Photos have alt text, width/height and lazy loading, and use the `.responsive-image` class. The grid is 4 columns on desktop, 2 on tablet and 1 on a smartphone. | Home page had no images; Part 2 "Images" feedback; SEO image optimisation |
| 32 | `about.html`, `css_assets/myfirststyles.css` | The "Where to find us" tab now has detail for each location (Johannesburg/Midrand and Menlyn), who each location suits, how to collect an order, and how to find and follow us, with links to other pages. The original sentence was kept. | More content requested; keywords and internal linking for SEO |
| 33 | `contact.html`, `js_assets/contact.js` | Locations checked against the coordinates in the original Google Maps embeds (Midrand: -25.9819021, 28.1329403; Menlyn: -25.7818819, 28.2767811). Each map now opens already zoomed to street level with its pop-up open. | Make sure the map locations work |
| 34 | `contact.html`, `js_assets/contact.js`, `css_assets/myfirststyles.css` | One map replaced by TWO separate maps (`#map-johannesburg` and `#map-menlyn`), each with its own heading. Each has an "Open in Google Maps" link and a "Get directions" link that work even if the map tiles do not load. The old "Show Johannesburg/Menlyn" buttons were removed because each map is now separate. The maps sit side by side on desktop and stack on tablet and smartphone. | Two separate maps requested; Part 3 2.1 Interactive maps |
| 35 | `contact.html`, `js_assets/contactform.js`, `css_assets/myfirststyles.css` | Added a second form, "Send us a message": name, email, occasion drop-down, optional date (the date picker blocks past dates), reply method radio buttons and a message (10 to 500 characters, with live counter). JavaScript validation, a jQuery modal summary and a WhatsApp button, like the enquiries form. jQuery is now also loaded on the Contact page. | Second form requested; Part 3 forms and JavaScript validation |
| 36 | all `js_assets/*.js` (not the libraries), `README.md` | Every JavaScript file now lists the full Harvard (IIE Anglia) references for the techniques it uses, and the code has in-text citations next to the relevant lines. README has a new "Where the JavaScript code was sourced" table and an updated reference list. | JavaScript sources must be referenced; Part 2 References 0/5 |
| 37 | all `.html` files, `README.md` | Dates in the README and reference access dates updated to 30 October 2026. | Accuracy |


### Not changed
Page text (including the original wording on the About page), image file names, the logo design, the colour scheme and the original menu labels were left as they were.

## Known limitations
- Enquiries are sent through WhatsApp, not stored. A form service or server would be needed to store them.
- Social media links are built from the `@BloomAndBlossom` handle; check they open the correct accounts.

## Where the JavaScript code was sourced

The JavaScript was written for this project using the techniques in the documentation below. The libraries jQuery and Leaflet are unmodified copies of the official releases. The full Harvard references are in the References list that follows, and each file also lists them in its header comment with in-text citations next to the code.

| File | What it does | Sources (in-text) |
|------|--------------|-------------------|
| `js_assets/main.js` | Scroll fade-in animation | (Mozilla Contributors, 2026a; 2026b) |
| `js_assets/about.js` | Tabs on the About page | (OpenJS Foundation, 2023a; 2023b; W3C, 2023a) |
| `js_assets/lightbox.js` | Gallery lightbox | (Mozilla Contributors, 2026c; 2026d; 2026e; W3C, 2023b) |
| `js_assets/services.js` | Product cards, search, filter, sort, accordion | (Mozilla Contributors, 2026c; 2026f; 2026g; 2026h; 2026i; OpenJS Foundation, 2023c; W3C, 2023c) |
| `js_assets/enquiries.js` | Enquiry form validation, modal, WhatsApp link | (Mozilla Contributors, 2026i; 2026j; 2026k; 2026l; 2026m; OpenJS Foundation, 2023d; W3C, 2023b; WhatsApp, 2026) |
| `js_assets/contactform.js` | Message form validation, modal, WhatsApp link | (Mozilla Contributors, 2026i; 2026j; 2026k; 2026l; 2026n; OpenJS Foundation, 2023d; W3C, 2023b; WhatsApp, 2026) |
| `js_assets/contact.js` | The two Leaflet maps | (Agafonkin, 2023a; 2023b; OpenStreetMap Foundation, 2026; OpenStreetMap contributors, 2026) |
| `js_assets/jquery-3.7.1.min.js` | jQuery library | (OpenJS Foundation, 2023e) |
| `js_assets/leaflet/` | Leaflet library | (Agafonkin, 2023c) |

The letters (2026a, 2026b...) tell apart sources by the same author in the same year; they match the reference list below.

## Acknowledgement of AI assistance

The code, comments and README for Part 3 were produced with the help of an AI assistant, then tested in a browser: Anthropic (2026) *Claude* [Large language model]. Available at: https://claude.ai (Accessed: 30 October 2026). Check the IIE rules on AI use and add this acknowledgement to your submission if it is required.

## References

Agafonkin, V. (2023a) *Leaflet Quick Start Guide*. Available at: https://leafletjs.com/examples/quick-start/ (Accessed: 30 October 2026).

Agafonkin, V. (2023b) *Leaflet API reference*. Available at: https://leafletjs.com/reference.html (Accessed: 30 October 2026).

Agafonkin, V. (2023c) *Leaflet: an open-source JavaScript library for interactive maps (version 1.9.4)*. Available at: https://leafletjs.com/ (Accessed: 30 October 2026).

Anthropic (2026) *Claude* [Large language model]. Available at: https://claude.ai (Accessed: 30 October 2026).

Google (2026a) *Maps URLs*. Available at: https://developers.google.com/maps/documentation/urls/get-started (Accessed: 30 October 2026).

Google (2026b) *Search Engine Optimization (SEO) starter guide*. Available at: https://developers.google.com/search/docs/fundamentals/seo-starter-guide (Accessed: 30 October 2026).

Mozilla Contributors (2026a) *Intersection Observer API*. Available at: https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API (Accessed: 30 October 2026).

Mozilla Contributors (2026b) *Element: classList property*. Available at: https://developer.mozilla.org/en-US/docs/Web/API/Element/classList (Accessed: 30 October 2026).

Mozilla Contributors (2026c) *Document: createElement() method*. Available at: https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement (Accessed: 30 October 2026).

Mozilla Contributors (2026d) *KeyboardEvent: key property*. Available at: https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key (Accessed: 30 October 2026).

Mozilla Contributors (2026e) *Event: preventDefault() method*. Available at: https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault (Accessed: 30 October 2026).

Mozilla Contributors (2026f) *Array.prototype.filter()*. Available at: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter (Accessed: 30 October 2026).

Mozilla Contributors (2026g) *Array.prototype.sort()*. Available at: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort (Accessed: 30 October 2026).

Mozilla Contributors (2026h) *String.prototype.localeCompare()*. Available at: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/localeCompare (Accessed: 30 October 2026).

Mozilla Contributors (2026i) *encodeURIComponent()*. Available at: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent (Accessed: 30 October 2026).

Mozilla Contributors (2026j) *Client-side form validation*. Available at: https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms/Form_validation (Accessed: 30 October 2026).

Mozilla Contributors (2026k) *Regular expressions*. Available at: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions (Accessed: 30 October 2026).

Mozilla Contributors (2026l) *Node: textContent property*. Available at: https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent (Accessed: 30 October 2026).

Mozilla Contributors (2026m) *URLSearchParams*. Available at: https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams (Accessed: 30 October 2026).

Mozilla Contributors (2026n) *<input type="date">*. Available at: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date (Accessed: 30 October 2026).

Mozilla Contributors (2026o) *Content Security Policy (CSP)*. Available at: https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CSP (Accessed: 30 October 2026).

OpenJS Foundation (2023a) *jQuery API documentation*. Available at: https://api.jquery.com/ (Accessed: 30 October 2026).

OpenJS Foundation (2023b) *jQuery .on()*. Available at: https://api.jquery.com/on/ (Accessed: 30 October 2026).

OpenJS Foundation (2023c) *jQuery .slideDown()*. Available at: https://api.jquery.com/slidedown/ (Accessed: 30 October 2026).

OpenJS Foundation (2023d) *jQuery .fadeIn()*. Available at: https://api.jquery.com/fadein/ (Accessed: 30 October 2026).

OpenJS Foundation (2023e) *jQuery (version 3.7.1)*. Available at: https://jquery.com/ (Accessed: 30 October 2026).

OpenStreetMap contributors (2026) *Copyright and license*. Available at: https://www.openstreetmap.org/copyright (Accessed: 30 October 2026).

OpenStreetMap Foundation (2026) *Tile usage policy*. Available at: https://operations.osmfoundation.org/policies/tiles/ (Accessed: 30 October 2026).

Schema.org (2026) *Florist*. Available at: https://schema.org/Florist (Accessed: 30 October 2026).

W3C (2023a) *Tabs pattern, WAI-ARIA Authoring Practices Guide*. Available at: https://www.w3.org/WAI/ARIA/apg/patterns/tabs/ (Accessed: 30 October 2026).

W3C (2023b) *Dialog (Modal) pattern, WAI-ARIA Authoring Practices Guide*. Available at: https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/ (Accessed: 30 October 2026).

W3C (2023c) *Accordion pattern, WAI-ARIA Authoring Practices Guide*. Available at: https://www.w3.org/WAI/ARIA/apg/patterns/accordion/ (Accessed: 30 October 2026).

WhatsApp (2026) *How to use click to chat*. Available at: https://faq.whatsapp.com/5913398998672934 (Accessed: 30 October 2026).
