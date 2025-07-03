# Cards - Open Source RSS Feeder

## Overview

A minimal yet powerful open source web app that aggregates and displays articles from multiple RSS feeds in a beautiful, responsive card layout. Features automatic thumbnail handling, light/dark theme, infinite scroll ("Show More"), social sharing, and robust feed parsing—no backend or server required. Designed for modern browsers and works on all devices.

![Screenshot 2025-07-03 231404](https://github.com/user-attachments/assets/78106b03-24e3-4c3a-a789-80e6ca90ae50)
![Screenshot 2025-07-03 231454](https://github.com/user-attachments/assets/0a134911-ff75-4698-a8c7-cec2c2dff557)

---

## Use Cases

- Personal dashboards and homepages
- Content/news aggregation for teams or communities
- Media curation and knowledge feeds
- Tech/news blog previews
- As a widget or section on personal/company websites

---

## Features

- ✅ Multi-column, fully responsive card layout (Masonry.js)
- ✅ Light/Dark mode with one-tap toggle
- ✅ "Show More" infinite scroll (batch loading)
- ✅ Social sharing: Facebook, Twitter, LinkedIn, WhatsApp, Telegram, Instagram (Direct), Email
- ✅ Scroll-to-top floating button
- ✅ Auto-sorting by date (most recent first)
- ✅ Duplicate removal across all feeds
- ✅ Smart thumbnail handling (works with all major feed formats)
- ✅ CORS-free RSS fetching with multiple fallback proxies (no server needed)
- ✅ Easy to customize: sources, style, batch size, share icons, and more
- ✅ **Backend word filter:** Hide cards containing certain words/phrases (see below)

---

## How It Works

1. **JavaScript** fetches RSS feeds from all URLs in the `feedUrls` array.
2. Feeds are parsed via public CORS proxy APIs (see `parsers` array). Once the free limit of one is reached, it automatically fetches from the second and so on.
3. All posts are normalized and deduplicated, and cards are rendered for each.
4. Cards include: thumbnail, source tag, title, description, timestamp, and share buttons.
5. "Show More" loads articles in batches (default: 15).
6. **Cards containing blocked words are NOT shown** (see [Word Filters](#word-filters)).
7. Responsive design ensures the deck looks great on desktop, tablet, and mobile.

---

## Setup & Usage

1. **Download or clone this repository.**
2. Open `index.html` in any modern web browser (Chrome, Edge, Firefox, Safari, mobile, etc.).
3. Done! No build step, no dependencies, no server—everything is in one HTML file.

---

## Customization Guide

### 1. **Change RSS Feed Sources**

Edit the `feedUrls` array inside the `<script>` section:

```javascript
const feedUrls = [
  'https://www.labnol.org/rss.xml',
  'https://techcrunch.com/feed/',
  // Add or remove feed URLs here
];
```

---

### 2. **Add/Remove CORS Proxy APIs**

Feeds are fetched through public proxies to bypass CORS. If a feed fails, the next proxy is tried.

```javascript
const parsers = [
  url => `https://api.rss2json.com/v1/api.json?rss_url=${encodeURIComponent(url)}`,
  url => `https://api.allorigins.win/get?url=${encodeURIComponent(url)}`,
  // Add or remove proxies here
];
```

---

### 3. **Edit Card Style, Layout, Theme**

All CSS is in the `<style>` block near the top:

- To change card color, border radius, font, etc., edit `.feed-card`, `.tag`, `.feed-title`, etc.
- For dark mode overrides, edit the `.dark-mode` sections.
- To adjust layout for mobile, use the `@media` queries.

---

### 4. **Change "Show More" Batch Size or Max Cards**

Near the top of the `<script>`:

```javascript
const maxCards = 60;      // Max cards shown at a time
const LOAD_MORE_BATCH = 15; // Number of articles per "Show More"
```

---

### 5. **Add/Remove Social Share Icons**

In the `createCard(post)` JavaScript function, find:

```javascript
share.innerHTML = `
  <a href="https://www.facebook.com/sharer/sharer.php?u=${shareUrl}" ...><i class="fab fa-facebook"></i></a>
  <a href="https://twitter.com/intent/tweet?text=${shareTitle}&url=${shareUrl}" ...><i class="fab fa-twitter"></i></a>
  <a href="https://www.linkedin.com/shareArticle?mini=true&url=${shareUrl}" ...><i class="fab fa-linkedin"></i></a>
  <a href="https://wa.me/?text=${shareTitle}%20${shareUrl}" ...><i class="fab fa-whatsapp"></i></a>
  <a href="https://t.me/share/url?url=${shareUrl}&text=${shareTitle}" ...><i class="fab fa-telegram"></i></a>
  <a href="https://www.instagram.com/direct/new/" ...><i class="fab fa-instagram"></i></a>
  <a href="mailto:?subject=${shareTitle}&body=${shareUrl}" ...><i class="fas fa-envelope"></i></a>
`;
```

Remove or add `<a>` tags to adjust which platforms are shown.

---

### 6. **Block Cards with Specific Words (Backend Filter)**

To hide any card containing certain words or phrases (case-insensitive, checks both title and description):

**Find this section in the code:**
```javascript
// --- WORD FILTERS (BACKEND ONLY) ---
// Add words below (lowercase, no spaces unless whole phrase) to block posts containing those words in title or description.
// Example: ["football", "bitcoin", "Satan"]
const wordFilters = [
  // Add your blocked words here, e.g.:
  // "AI", "RSS", "Covid"
];
// ------------------------------------
```

**Add your words inside the array**, for example:
```javascript
const wordFilters = [
  "cricket",
  "politics",
  "Netanyahu"
];
```
Any post whose title or description matches any of these will be **omitted from the feed**.

---

### 7. **How to toggle the dark mode icon in the UI**

The following line controls whether the dark mode toggle icon appears:
```JavaScript
const showDarkModeIcon = "yes"; // <--- CHANGE TO "no" TO HIDE THE ICON
```
Location: This line appears near the top of the <body>, right before the dark mode button and before any card rendering starts.

Set to "yes" (default) to show the icon, or "no" to hide it completely from the UI.

---

### 8. **Change Theme Colors, Fonts, or Responsive Behavior**

Edit the CSS in the `<style>` tag. Change colors, fonts, icons, and layout as desired.

---

### 9. **Other Customizations**

- To change the app title, edit the `<title>` tag in `<head>`.
- To change the "Show More" button text, edit `LOAD_MORE_TEXT`.
- To change the scroll-to-top button, edit `.scroll-top` and `.go-top-btn` CSS.
- To disable a feature, comment out or remove the relevant section of code.

---

## Deployment

- Host the `index.html` file on GitHub Pages, Netlify, Vercel, or any static site host.
- No server or backend services required.

---

## License

MIT License — Free to use, modify, and distribute with attribution.

---

## Author

Developed by Saif Ansari [@Saifscode](https://github.com/SaifsCode)  
With the help of Neo, my personalized AI from OpenAI.

Inspired by the need for a customizable, fast, and beautiful RSS aggregator for my company's website.  
This was my first code project. Hope you find it useful!

---
