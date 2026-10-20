# Pavel Luzanov | Portfolio

Personal portfolio for Pavel Luzanov, lifecycle marketing and CRM lead based in Kuala Lumpur. It's a single static page styled after a late-90s web directory, hosted free on GitHub Pages.

**Live site:** `https://pavelluzanov.github.io`
**Contact:** pavelluzanov189@gmail.com | [LinkedIn](https://www.linkedin.com/in/luzanovpavel)

---

## What's in the repo

```
<your-github-username>.github.io/
├── index.html    The whole site: content, styling and search, in one file
├── README.md     This file
└── assets/       Images: headshot, logos, campaign creatives
```

There's no build step, framework or dependencies. Edit `index.html`, upload it, and the site updates.

### Page sections

The sections appear in this order in `index.html`. Search the file for these markers to jump to each one.

| Marker in `index.html` | What it is |
| --- | --- |
| `PORTAL HERO` | Wordmark, tagline, search box and topic links |
| `Pavel's quotes` | The stock-ticker box of headline metrics |
| `Previously at` | Companies, which will become logos |
| `id="about"` | Headshot and About copy |
| `id="work"` | Case studies |
| `id="recognition"` | Awards, certifications, MBA and mentoring |
| `id="contact"` | Email, LinkedIn and booking buttons |

### Add logos

Upload them to `assets/` (for example `logo-socar.png`), then replace the text line in the `Previously at` box with image tags. Delete the "Logos can go here later" note when you do.

### Change colors and fonts

Every color and font is defined once, in the `:root` block at the top of the `<style>` section:

| Token | Used for |
| --- | --- |
| `--purple` | Top bar, headings, wordmark |
| `--yellow` | Wordmark shadow, result box, step numbers |
| `--link` / `--visited` | Classic blue and purple links |
| `--grey` | Bevelled buttons |
| `--page` | Page background |
| `--serif` | Headings and wordmark (Times New Roman) |
| `--sans` | Body text (Verdana) |

Changing a value there updates it everywhere on the page.

---

## How the search works

The search box and topic links filter the case studies in the browser, with no server or external services involved. A case study stays visible if the search text appears in its `data-tags` or anywhere in its visible text. To make a case study findable for a new keyword, add that word to its `data-tags`.

---
