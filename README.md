# Pavel Luzanov | Portfolio

Personal portfolio for Pavel Luzanov, lifecycle marketing and CRM lead based in Kuala Lumpur. It's a single static page styled after a late-90s web directory, hosted free on GitHub Pages.

**Live site:** `https://<your-github-username>.github.io`
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

---

## Put it online (first time)

1. Sign in to [github.com](https://github.com) and click **New repository**.
2. Name it exactly `<your-github-username>.github.io` and set it to **Public**.
3. Click **Add file > Upload files** and drag in `index.html`, `README.md` and the `assets` folder. Click **Commit changes**.
4. Go to **Settings > Pages**. Under **Source**, choose **Deploy from a branch**, then branch `main` and folder `/ (root)`. Click **Save**.
5. Wait one to two minutes, then open `https://<your-github-username>.github.io`.

**Optional: custom domain.** If you buy a domain such as `pavelluzanov.com`, add it under **Settings > Pages > Custom domain**, then follow GitHub's instructions for the DNS records at your domain registrar.

---

## Update the site

Edit files directly on GitHub: open the file, click the pencil icon, make your change, then **Commit changes**. The live site updates within a couple of minutes. If you don't see the change, do a hard refresh (Ctrl+Shift+R on Windows, Cmd+Shift+R on Mac).

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

### Edit a headline metric

Each row in the quotes box looks like this:

```html
<tr><td>Rebooking rate<span class="lbl">SOCAR lifecycle program</span></td><td class="up">▲ +6%</td></tr>
```

Change the label, the small grey source line, or the number. Copy a whole row to add a new one. Four or five rows is the sweet spot.

### Add or edit a case study

Each case study is an `<article class="case">` block. To add one, copy an existing block, paste it below the last case study, and change:

- **`data-tags`:** the hidden keywords the search box matches against. Include the company, tools, channels and topics, all lowercase.
- **`crumb`:** the breadcrumb, for example `Home &gt; Launches`. `&gt;` displays as `>`.
- **`h3`:** the title.
- **`meta`:** the company and dates.
- **Paragraphs:** two short ones work best. Cover the problem and what you did.
- **`result`:** the single biggest number and a one-line explanation.
- **`related`:** the clickable tags. Each one filters the page when clicked:
  ```html
  <a href="#q" data-q="braze">Braze</a>
  ```
- **`steps`** (optional): a numbered timeline. Only use it when the content really is a sequence, like a lifecycle or a purchase flow.

Then update the status line near the search box (`3 case studies across Mindvalley and SOCAR`) to match the new count.

### Add images

1. Upload the image into `assets/` with the filename shown in its grey placeholder box, for example `assets/mv-crm-1.jpg`.
2. In `index.html`, replace the placeholder:
   ```html
   <div class="slot inset">Cart abandonment email<br><code>assets/mv-crm-2.jpg</code></div>
   ```
   with:
   ```html
   <img class="inset" src="assets/mv-crm-2.jpg" alt="Cart abandonment email for Mindvalley">
   ```
   For the wide slot at the top of each case study, keep the `wide` class: `<img class="inset wide" ...>`.
3. Always write a real `alt` description. Screen readers use it, and it shows if an image fails to load.

**Image tips:** use JPG for photos and screenshots, and PNG or SVG with a transparent background for logos. Keep each file under about 500 KB so the page loads fast on mobile; [squoosh.app](https://squoosh.app) compresses images for free. Before publishing, blur or crop out customer names, emails and internal dashboard numbers.

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

## Before you share the link

- [ ] Every image placeholder is replaced, or removed.
- [ ] The "Logos can go here later" note is deleted.
- [ ] Every number is one you can explain in an interview.
- [ ] Nothing confidential is visible in screenshots.
- [ ] Email, LinkedIn and booking links all work when clicked.
- [ ] The page checks out on your phone.
- [ ] The link is added to your LinkedIn Featured section and Contact info.
