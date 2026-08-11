# UChicago Club Hockey — Team Website

A free, D1-style team site (roster + schedule) built as a static Jekyll site,
hosted free forever on GitHub Pages.

## What's in here
- `index.html` — home page (hero, record stat strip, next game)
- `roster.html` — auto-generated player grid from `_data/roster.yml`
- `schedule.html` — auto-generated schedule/results table from `_data/schedule.yml`
- `_data/roster.yml` — **edit this to update your roster**
- `_data/schedule.yml` — **edit this to update games/scores**
- `assets/css/style.css` — all styling (maroon theme, easy to recolor)
- `_layouts/default.html` — shared nav/footer wrapper

You will basically never touch the `.html` template files again after setup —
just edit the two YAML files in `_data/` when the roster or schedule changes.

## 1. Create the GitHub repo (2 min)
1. Go to github.com, log in (or make a free account).
2. Click **New repository**.
3. Name it `uchicago-club-hockey` (or anything).
4. Keep it **Public** (required for free GitHub Pages), don't add a README/gitignore (we already have them).
5. Click **Create repository**.

## 2. Push this site to GitHub
On your computer, open a terminal in this folder and run:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/uchicago-club-hockey.git
git push -u origin main
```

(No git installed, or don't want to use the terminal? On the GitHub repo page,
click **"Add file" → "Upload files"** and drag this whole folder in instead.)

## 3. Turn on GitHub Pages
1. In your repo, go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)`. Save.
4. Wait ~1 minute. Your site will be live at:
   `https://YOUR-USERNAME.github.io/uchicago-club-hockey/`

## 4. Set the `baseurl` (important!)
Open `_config.yml` and set:
```yaml
baseurl: "/uchicago-club-hockey"   # your repo name, with leading slash
url: "https://YOUR-USERNAME.github.io"
```
Commit and push that change — otherwise CSS/links may 404 on the live site.

> Tip: if you later buy a custom domain (e.g. `uchicagohockey.com`) and set it
> up in Settings → Pages, set `baseurl: ""` and `url` to your custom domain instead.

## 5. Update your roster or schedule
Just edit the YAML files and push:

```bash
git add _data/roster.yml _data/schedule.yml
git commit -m "Update roster and schedule"
git push
```

GitHub automatically rebuilds the site within about a minute — no other steps needed.

## 6. Customize branding
- **Colors:** edit the `:root` variables at the top of `assets/css/style.css` (`--maroon`, `--gold`, etc.)
- **Logo:** drop an image into `assets/img/` and swap the `.puck` span in `_layouts/default.html` for an `<img>` tag
- **Fonts:** currently Google Fonts "Archivo Black" + "Barlow" (both free), loaded in `_layouts/default.html`

## Previewing locally (optional)
If you have Ruby installed:
```bash
bundle install
bundle exec jekyll serve
```
Then open `http://localhost:4000`.
