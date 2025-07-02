
Free-RSS-Feed-Puller-Multi-Parser - README.md
==========================================

Description:
------------
This is a minimal yet powerful responsive web app that aggregates and displays content from multiple RSS feeds in a card-based layout. It supports light/dark themes, infinite scrolling, social sharing, and works across modern devices and screen sizes.

![image](https://github.com/user-attachments/assets/f3d27d62-f929-4760-bb88-dc27ac501985)
![image](https://github.com/user-attachments/assets/3af9f46e-242d-4b57-9027-e2eca494fc75)

Use Case:
---------
Ideal for:
- Personal dashboards
- Content aggregators
- News/media curators
- Knowledge feeds
- Tech blog previews
- Feeds on personal websites

Features:
---------
✅ Multi-column responsive layout  
✅ Light/Dark mode toggle  
✅ Load more functionality  
✅ Shareable links (Facebook, Twitter, LinkedIn, WhatsApp, Reddit)  
✅ Scroll-to-top button  
✅ Auto-sort by date & de-duplicate posts  
✅ Smart thumbnail handling  
✅ CORS-free feed fetching with multiple fallback proxies

How It Works:
-------------
- Uses JavaScript to fetch RSS feeds from a list of URLs.
- Parses and normalizes the data using public CORS proxy APIs.
- Renders each post into a stylized card including thumbnail, title, source tag, relative timestamp, and share buttons.
- Implements a progressive loading strategy (e.g., 15 posts per batch).

Setup Instructions:
-------------------
1. Clone or download the repository.
2. Open `index.html` in any modern web browser.
3. Internet connection is required (feeds are fetched live).

Customization Guide:
--------------------
```javascript

📌 RSS Feed Sources:

Edit the `feedUrls` array in the `<script>` section of the HTML to include or remove sources:

const feedUrls = [
  'https://www.labnol.org/rss.xml',
  'https://techcrunch.com/feed/',
  ...
];


📌Proxy API Fallbacks:

If a feed does not load due to CORS issues, the script uses the following fallback services:

const parsers = [
  url => `https://api.rss2json.com/v1/api.json?rss_url=${encodeURIComponent(url)}`,
  url => `https://api.allorigins.win/get?url=${encodeURIComponent(url)}`,
  url => `https://api.codetabs.com/v1/proxy/?quest=${encodeURIComponent(url)}`
];

You can add your own proxy or use a self-hosted CORS bypass API.


📌Card Style & Theme:

Customize the look and feel by editing the <style> block in the <head>:

Colors, font size, border radius

.dark-mode section for dark theme override

.feed-card, .tag, .feed-title, etc.


📌 Load More Behavior:

Change how many posts are loaded initially or per batch:

"const maxCards = 60;
let batch = 15;"


📌 Share Icons:
Add/remove sharing platforms inside the createCard(post) function in the JavaScript section:
<a href="https://www.facebook.com/sharer/sharer.php?u=${shareUrl}">...</a>


📌 Toggle Dark Mode:
A button is located in the top-right of the page:
<button class="toggle-dark" onclick="toggleDarkMode()">Toggle Dark Mode</button>


📌 Scroll-to-Top Button:
This button appears after scrolling down. You can customize its style via .scroll-top CSS class.

```

Deployment:

Simply host index.html on GitHub Pages, Netlify, Vercel, or any static file host.


License:

MIT License – Free to use, modify, and distribute with attribution.



Author:
Developed by Saif Ansari @Saifscode with the help of Neo, my personalized AI from OpenAI
Inspired by the need for a customizable, fast, and beautiful RSS aggregator for my company's website.

This is my first code I have ever written. Hope it is useful to you.

