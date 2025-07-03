# 🤝 Contributing to Cards – Open Source RSS Feeder

Welcome, and thank you for your interest in contributing to **Cards – Open Source RSS Feeder**!

This project is part of a larger mission to build intelligent, modular, and privacy-respecting open-source data tools for the future of the web. Contributions of any size, shape, or kind are welcome. Read on to learn how to get involved. 🌍🚀

---

## 📌 Table of Contents

- [How to Contribute](#how-to-contribute)
- [Code Style Guidelines](#code-style-guidelines)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Feature Requests](#feature-requests)
- [Reporting Bugs](#reporting-bugs)
- [Pull Request Process](#pull-request-process)
- [Community Rules](#community-rules)
- [Contact](#contact)

---

## ✅ How to Contribute

1. **Fork** this repository on GitHub.
2. **Clone** your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Cards--The-Open-Source-RSS-Feeder.git
   ```
3. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. Make your changes (see *Customization Pointers* below).
5. Commit and push:
   ```bash
   git add .
   git commit -m "feat: describe your change"
   git push origin feature/your-feature-name
   ```
6. **Open a Pull Request** from your fork/branch to the main repository.

---

## 🎯 Code Style Guidelines

- **Language:** HTML, CSS, JavaScript (vanilla, no framework)
- Use consistent indentation and spacing as in the original code.
- Use clear, descriptive variable and function names.
- Keep CSS in the `<style>` block and JS in `<script>` within `index.html`.
- Prefer readable code and concise comments (where relevant).
- When adding dependencies, use CDN links only (no build tools or npm).

---

## ✍️ Commit Message Guidelines

Follow [Conventional Commits](https://www.conventionalcommits.org/) for clarity:

| Type      | Purpose                                  |
|-----------|------------------------------------------|
| `feat`    | New feature                              |
| `fix`     | Bug fix                                  |
| `docs`    | Documentation only                       |
| `style`   | Formatting, whitespace, UI tweaks        |
| `refactor`| Code changes, no feature/bug impact      |
| `test`    | Adding/correcting tests                  |
| `chore`   | Build process or tooling changes         |

Example:

```bash
git commit -m "feat: add ability to block tags in feeds"
```

---

## 💡 Feature Requests

Want a new feature? Please open an [issue](../../issues/new?template=feature_request.md) and include:

- The problem it solves
- Example feeds or use-cases
- Your design idea (if any)

---

## 🐛 Reporting Bugs

1. Search for existing issues before creating a new one.
2. Create an issue using the **Bug Report** template.
3. Please include:
   - Steps to reproduce
   - Browser/device info
   - Feed URLs (if relevant)
   - Screenshots or error messages

---

## 🔁 Pull Request Process

- **Keep PRs focused**: One change or fix per PR.
- **Reference issues** where possible.
- **Test your changes** on desktop and mobile browsers.
- **Describe user-facing changes** in the PR description.
- PRs will be reviewed and, upon approval, merged to `main`.

---

## 🛠️ Customization Pointers (for code or PR suggestions)

- **RSS Sources**:  
  Edit the `feedUrls` array in the `<script>` section.
- **CORS Proxies**:  
  Edit the `parsers` array if you want to add/remove fallback proxies.
- **Card Layout/Style/Theme**:  
  Edit the CSS in the `<style>` section.
- **Social Share Icons**:  
  Edit the `<a>` tags in the `share.innerHTML` block of `createCard(post)`.
- **"Show More" Batch Size**:  
  Change `const LOAD_MORE_BATCH = 15;` and/or `const maxCards = 60;`.
- **Block Words (Backend Only)**:  
  Add or remove words in the `wordFilters` array to filter out posts by keyword.
- **Show/Hide Dark Mode Icon**:  
  Set `const showDarkModeIcon = "yes";` or `"no";` near the top of `<body>`.
- **Title/Description Font Weight**:  
  Change `.feed-title` and `.feed-desc` in the CSS for bold/regular weight.
- **Other behaviors**:  
  Feel free to suggest or implement new customizations!

---

## 🌱 Community Rules

- Be kind, helpful, and respectful.
- No spam, hate, or abuse.
- Share knowledge and improvements openly.
- Let's make open source better together!

---

## 📬 Contact

Maintainer: [@SaifsCode](https://github.com/SaifsCode)  
Email: saifscode [@] gmail [.] com  
Twitter: [@saifsbird](https://x.com/SaifsBird)

---

Thank you for helping make the web more open and useful! 🚀
