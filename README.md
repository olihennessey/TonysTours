# Tony's Tours

A single-page site for a fictional day-trip tour company in Lanzarote. Plain HTML, CSS and vanilla JS, with no framework and no build step.

Tony's Tours is not a real company and is not taking bookings. The booking form is a demo: it shows a confirmation on the page and sends nothing anywhere.

## Files

```
index.html          the page
css/styles.css      all styling, including light and dark themes
js/main.js          the booking form confirmation
assets/hero.webp    background photo behind the hero
assets/tony.jpg     photo used in the About section
assets/favicon.svg  site icon
```

## Running locally

Open `index.html` in a browser. That is enough, since there is nothing to compile.

If you would rather serve it over HTTP, run one of these from the project folder:

```bash
python -m http.server 8000
```

```bash
npx serve
```

## Deploying to Vercel

The site is static with `index.html` at the root, so it needs no configuration and no `vercel.json`.

Either push the folder to a Git repository and import it at [vercel.com/new](https://vercel.com/new), leaving the framework preset as "Other", or deploy straight from this folder:

```bash
npx vercel
```

Add `--prod` when you want it on the production URL rather than a preview one.

## Photos

**The hero.** The background photo is `assets/hero.webp`. To change it, drop a new file in at that name, or point the `background-image` line in the `.hero` rule at a different one. A dark gradient sits over the photo so the heading stays readable against a bright sky, so leave that in place. Landscape images work best, and anything under about 1600px wide will soften on a large screen.

**The About photo** is a plain `<img>` in the markup, so it can be swapped in `index.html`. Update the `alt` text to match whatever you put there.

**Tour cards** can take a photo too, though none currently do. Add a `<figure>` as the first thing inside a `<li class="tour">` and the styling is already there:

```html
<li class="tour">
  <figure><img src="assets/your-photo.jpg" alt="Describe the photo here"></figure>
  <h3>Puerto Calero Walk</h3>
  ...
</li>
```

Photos are cropped to a fixed height so a row of cards stays level, which means the middle of the image is what shows. Every one needs `alt` text describing what is in it.

## Notes

- Fonts (Shrikhand and Instrument Sans) load from Google Fonts. Nothing else is loaded from a third party: no cookies, no analytics, no tracking.
- Light and dark themes follow the system setting. To pin the page to one, set `data-theme="light"` or `data-theme="dark"` on the `<html>` element.
