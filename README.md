# Ariel Power Ltd — Solar EPC & Green Energy

A responsive corporate website for a Bangladeshi solar energy company. Presents the company's EPC services, completed projects, and contact channels. Built with pure HTML5 and CSS3 — no framework, no build step, no JavaScript dependencies beyond a small script for the mobile menu.

**Live:** [arielpowerltd.com](https://arielpowerltd.com)

---

## Stack

| Layer | Choice |
| --- | --- |
| Markup | HTML5 (semantic) |
| Styling | CSS3 · Flexbox · Grid |
| Responsive | Custom media queries · Mobile-first |
| Animations | CSS transitions · Keyframes |
| Deployment | cPanel · Shared hosting |
| Tools | VS Code · Git |

---

## Why no framework?

The site is a brochure — a handful of pages, no user accounts, no dynamic content, no data fetching. A React or Next.js build would add significant JavaScript, a build pipeline, and a Node dependency for zero functional gain. Plain HTML + CSS loads in under 100 ms on a 3G connection and works even with JavaScript disabled.

The one exception is the mobile menu toggle — that's a small amount of vanilla JS.

---

## Structure

```
ariel-power-solutions/
├── index.html          Home
├── about.html          About the company
├── services.html       EPC services
├── projects.html       Completed installations
├── contact.html        Contact form + map
├── css/
│   ├── reset.css
│   ├── style.css       Main styles
│   └── responsive.css  Media queries
├── js/
│   └── menu.js         Mobile nav toggle
└── assets/
    ├── images/
    └── icons/
```

---

## Running locally

No build step needed. Open `index.html` directly in a browser, or run a tiny static server:

```bash
# Python 3
python -m http.server 8000

# or Node
npx serve .
```

Then visit `http://localhost:8000`.

---

## Design decisions

- **CSS Grid for page layout, Flexbox for components.** Grid handles the two-dimensional structure (hero + content + sidebar), Flexbox handles one-dimensional rows (nav links, card contents).
- **Mobile-first media queries.** Base styles target small screens; `@media (min-width: ...)` layers on desktop layouts. Result: faster mobile load, less CSS to override.
- **Semantic HTML.** `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` throughout — better for SEO, screen readers, and future maintenance.
- **No JavaScript for content.** Everything except the mobile menu works without JS. If a script fails to load, the site still renders.

---

## Deployment

Uploaded via cPanel's File Manager to the hosting account's `public_html` directory. DNS points at the shared host. No CI, no build — commit locally, upload the changed files, done.

---

## Notes

- Contact form posts to the hosting provider's built-in mail handler — no third-party service.
- Images are compressed and served as WebP where the browser supports it, with JPG fallback otherwise.
- Verify Lighthouse scores on the live site before publishing any performance claims.