# REINE Lab website

Built with [Quarto](https://quarto.org). Structure mirrors misbath.github.io but with a lab-oriented set of pages.

## 1. Install Quarto (one-time)

Not installed on this machine yet. Download and run the macOS installer:

```bash
curl -LO https://quarto.org/download/latest/quarto-macos.pkg
open quarto-macos.pkg
```

Follow the installer prompts (needs your admin password). Verify with:

```bash
quarto --version
```

## 2. Fill in the placeholders

Every `.qmd` file has bracketed `[placeholder]` text — lab mission statement, PI bio, team members,
research projects, funding, publications, contact email. Replace `images/lab-hero.jpg`,
`images/misbath.jpg`, and `images/placeholder.jpg` with real photos (same filenames, or update the
`.qmd` files to match).

## 3. Preview locally

```bash
quarto preview
```

Opens a live-reloading local preview in your browser.

## 4. Set up GitHub hosting

`reinelab.github.io` (no username/path) requires a GitHub **organization** named `reinelab`:

1. On github.com, click **+ → New organization** and create one named exactly `reinelab`
   (you'll own it; add lab members as members later).
2. Inside that org, create a new repository named exactly `reinelab.github.io`.
3. Add it as the remote for this local project:

```bash
git remote add origin https://github.com/reinelab/reinelab.github.io.git
git branch -M main
git push -u origin main
```

## 5. Publish

Simplest option — renders the site and pushes it to a `gh-pages` branch in one step:

```bash
quarto publish gh-pages
```

Then in the repo's **Settings → Pages**, set the source branch to `gh-pages` (Quarto's publish
command usually configures this automatically the first time). The site will be live at
https://reinelab.github.io within a few minutes.

Re-run `quarto publish gh-pages` any time you update content.
