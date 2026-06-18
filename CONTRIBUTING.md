# Contributing

Thanks for your interest in Emotion Museum.

This project welcomes improvements to metadata quality, artwork attribution, accessibility, performance, interaction design, and documentation.

## Local Development

```bash
npm install
npm run dev
```

The app is designed as a static-first Cloudflare Workers project. Most of the interface currently lives in `public/index.html`.

## Artwork And Metadata

Please keep artwork rights visible when changing the dataset.

- Include source URLs for new artworks.
- Prefer public-domain or open-access sources with clear rights statements.
- Update `ATTRIBUTIONS.md` when adding or replacing bundled images.
- Keep emotion labels conservative and defensible. If a classification is interpretive, make sure the artwork notes explain the reasoning.

## Pull Requests

Good pull requests usually include:

- A short description of the user-facing change.
- Screenshots or screen recordings for visual changes.
- Notes about any data-source or attribution changes.
- A quick validation note, such as the browser and viewport used for testing.

## Scope

Emotion Museum is intentionally lightweight. Please avoid adding heavy frameworks or build complexity unless the change clearly improves maintainability, performance, or accessibility.
