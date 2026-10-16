# VoltEdge Electrical — Company Website

Static single-page company website for a fictional electrical services company,
built with [Tailwind CSS v4](https://tailwindcss.com) and deployed on
[GitHub Pages](https://pages.github.com/).

Layout and design language are inspired by the Astra
[Brandstore](https://wpastra.com/templates/brandstore-02/) template:
hero with promo headline, trust strip, category cards, services grid with
prices and badges, dark special-offer banner, benefits row, about section with
stats, quote form, and a multi-column footer.

> ⚠️ All company details (name, phone, address, license number, reviews) are
> placeholder content — replace them with real business info.

## Structure

```
index.html          # The whole site (single page, anchored sections)
assets/css/main.css # Compiled Tailwind CSS (committed so Pages needs no build)
assets/img/         # Photos (Pexels) + favicon
src/input.css       # Tailwind source with design tokens (@theme)
```

## Development

```bash
npm install
npm run watch   # rebuild CSS while editing
npm run build   # minified production build
```

After changing classes in `index.html`, run `npm run build` and commit the
updated `assets/css/main.css`.

## Deployment

The site is live at: **https://kamqb.github.io/teststrona/**

GitHub Pages serves the `main` branch root. Pushing to `main` deploys
automatically — no CI needed since the compiled CSS is committed.

## Credits

- Photos: [Pexels](https://www.pexels.com/) (free to use)
- Template inspiration: [Astra Brandstore](https://wpastra.com/templates/brandstore-02/)
