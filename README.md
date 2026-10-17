# Padel Kulture — Landing Page

A single-page landing site for **Padel Kulture**, a screen-printed tee and
art-print brand built around padel court culture. Hero background art,
copy, and shop grid are all self-contained — no build step required.

## Structure

```
.
├── index.html                       # Standalone site — open directly in a browser
├── wordpress/
│   └── template-padel-prints.php    # WordPress custom Page Template version
└── README.md
```

## Using `index.html`

This is a single, self-contained HTML file (CSS and the hero artwork are
inlined, the hero image as a base64 data URI) — no dependencies, no build
step. Open it directly in a browser, or deploy it as-is to any static host
(Netlify, Vercel, GitHub Pages, S3, plain Apache/Nginx, etc.) by pointing
your domain at this file.

### Deploying to GitHub Pages
1. Push this repo to GitHub.
2. In **Settings → Pages**, set the source branch and root folder.
3. GitHub Pages serves `index.html` automatically at your Pages URL.

## Using the WordPress template

`wordpress/template-padel-prints.php` is a custom **Page Template** —
it intentionally skips `get_header()`/`get_footer()` so no theme chrome
wraps the design, but still calls `wp_head()` and `wp_footer()` so
plugins, analytics, and the admin bar keep working.

1. Copy `template-padel-prints.php` into your active theme's folder:
   `wp-content/themes/your-theme/template-padel-prints.php`
   (or into a child theme — recommended, so theme updates don't remove it).
2. In WP Admin, create or edit a Page.
3. In the **Page Attributes** panel, set **Template** to
   **"Padel Kulture Landing."**
4. Publish.

## Customizing

- **Copy / prices / concept names:** edit directly in the HTML — it's all
  plain markup, no templating syntax.
- **Colors:** CSS custom properties are defined at the top of the
  `<style>` block (`--ink`, `--paper`, `--court`, `--ball`, etc.).
- **Hero background image:** currently embedded as a base64 JPEG inside
  the `.hero-bg` element's inline `style`. To swap it, replace the
  `data:image/jpeg;base64,...` string, or externalize it to an `/assets`
  image file and point `background-image` at a relative path instead.

## License

All rights reserved — adjust this section if you intend to open-source it.
