# Petal & Crumb

The Petal & Crumb bakery website — a single-page [Jekyll](https://jekyllrb.com/)
static site, hosted on GitHub Pages.

It's built so you can **edit the content without touching code**. Almost
everything you'd want to change lives in two places:

| What you want to change | Where to edit |
| --- | --- |
| Bakery name, tagline, hero text, story, contact, Instagram, address | `_config.yml` |
| Menu items & prices | `_data/menu.yml` |
| Market hours | `_data/hours.yml` |

After you edit a file and commit it (or save it through the GitHub web
editor), GitHub rebuilds and republishes the site in about a minute.

---

## Editing content

### The words (`_config.yml`)
Open `_config.yml` and change the text after each `:`. For example, to
change the tagline:

```yaml
tagline: Artisan Bakery        # ← change this text
```

Keep quotes where they already exist. Lines under `paragraphs:` are a list —
each `- "…"` is one paragraph; add or remove lines to add or remove
paragraphs.

> **Note:** changes to `_config.yml` only appear after a fresh build. On
> GitHub Pages that happens automatically. If you're previewing locally,
> restart the server (see below).

### The menu (`_data/menu.yml`)
Each item is three lines. Copy a block to add an item, delete one to remove it:

```yaml
- name: Beignets
  price: "$10"
  description: "Served with caramel dipping sauce — or powdered sugar on request."
```

### Market hours (`_data/hours.yml`)
```yaml
- day: Saturday
  time: "9:00 am – 6:00 pm"
```

### Adding photos
The hero image, the map, and the Instagram grid currently show striped
placeholders. To use a real hero photo, drop the file in
`assets/images/` and point to it in `_config.yml`:

```yaml
hero:
  image: "/assets/images/hero.jpg"
```

(The map and Instagram grid have comments in `_includes/find.html` and
`_includes/instagram.html` showing how to swap those too.)

---

## Project layout

```
_config.yml          Site-wide content & settings (edit me)
_data/menu.yml       Menu items (edit me)
_data/hours.yml      Market hours (edit me)
index.html           The page — just pulls in the sections below
_layouts/default.html  HTML shell (head, header, footer)
_includes/           One file per section: hero, story, menu, find, instagram…
_includes/sprig.html The reusable botanical logo mark
assets/css/style.css All styling; the brand palette lives at the top as variables
assets/images/       Photos, favicon
```

---

## Previewing locally (optional)

You only need this if you want to see changes before pushing. Requires Ruby.

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000/petal-and-crumb/>. Stop with `Ctrl-C`;
restart after editing `_config.yml`.

---

## Deploying (GitHub Pages)

This repo is set up for GitHub Pages' classic, build-from-branch mode:

1. Push to the `main` branch on GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Set the branch to **`main`** and folder to **`/ (root)`**, then **Save**.

The site publishes at `https://chmille4.github.io/petal-and-crumb/`.

> **Custom domain?** If you add one (or rename the repo to
> `chmille4.github.io`), set `baseurl: ""` in `_config.yml` so links resolve
> correctly.
