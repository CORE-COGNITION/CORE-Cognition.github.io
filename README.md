# Binz Lab — website

A small, dependency-free static site. Plain HTML + one CSS file, no build step,
no JavaScript. Edit the files directly and refresh the browser.

## Files

```
index.html           Main page
people.html          People
resources.html       Resources
open-positions.html  Open Positions
styles.css           All styling (colors, layout, typography)
favicon.svg          Browser tab icon
```

## Run it locally

Just open `index.html` in a browser — that's it. Or serve the folder so links
behave exactly like in production:

```sh
python -m http.server 8000
# then visit http://localhost:8000
```

## Edit the content

- **Text**: open the relevant `.html` file and edit the words between the tags.
- **Placeholders**: search for `TODO` — every spot you still need to fill in
  (the third research interest, lab members, publications, open roles) is
  marked, and shows as a small yellow tag on the page.
- **Add a page / tab**: copy an existing `.html` file, change its content, then
  add a `<a href="new-page.html">New tab</a>` line to the `<nav>` block. The nav
  is duplicated in each file (by design — no build step); update all four. On
  the new page, mark its own nav link with `aria-current="page"`.

## Change the look

All colors and fonts are CSS variables at the top of `styles.css` (`:root`).
For example, to change the accent blue, edit `--brand-bright`. The palette
currently matches the MPI for Biological Cybernetics in Tübingen.

## People photos

On `people.html`, each person uses a circular initials placeholder. To use a
real photo, drop the image in an `img/` folder and replace the placeholder:

```html
<!-- before -->
<div class="avatar" aria-hidden="true">MB</div>
<!-- after -->
<img class="avatar" src="img/marcel-binz.jpg" alt="Marcel Binz">
```

## Deploy

Any static host works. The simplest is **GitHub Pages**: push this folder to a
repo and enable Pages on the default branch — `index.html` is served as the home
page. Netlify, Cloudflare Pages, or a plain web server work the same way.
