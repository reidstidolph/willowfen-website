# Willow Fen Farm website

A simple static website for Willow Fen Farm at Lake Wenatchee, Washington. It's plain HTML and CSS with no build step, so it works on GitHub Pages as-is.

## Files

```
index.html        the whole site (one page)
css/styles.css    colors, fonts and layout
images/           photos (resized and stripped of camera/GPS data) + favicon
.nojekyll         tells GitHub Pages to serve files as-is
```

## Publishing on GitHub Pages

1. Merge this into the repository's default branch.
2. On GitHub, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick the default branch and the `/ (root)` folder, then save.
4. After a minute or two the site will be live at `https://<username>.github.io/willowfen-website/`.

To use your own domain (for example `willowfenfarm.com`), enter it under **Settings → Pages → Custom domain** and follow GitHub's DNS instructions.

## Things to fill in

Search `index.html` for these:

- **Logo**: `images/logo.png` (dark, for light backgrounds) and `images/logo-light.png` (cream, for the photo banner and footer). Replace both if the logo changes.
- **Market days and hours**: the "When" line in the market section.
- **The writing**: the About and product text is a starting draft. Change anything that isn't quite right for your farm.

## Adding photos

Phone photos are usually 3–10 MB. Resize them to about 1200–2000 px wide before adding them so the site loads fast. Any image editor works, or with ImageMagick:

```bash
convert original.jpg -auto-orient -strip -resize 1600x1600\> -quality 78 images/new-photo.jpg
```

`-strip` removes location (GPS) data from the photo.

## Previewing locally

Open `index.html` in a browser, or run a tiny local server:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.
