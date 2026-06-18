# Emotion Museum

**Emotion Museum** is an interactive artwork atlas for exploring paintings through mood, movement, and visual association.

Instead of browsing artworks by period, artist, or collection alone, Emotion Museum arranges public-domain and open-access artworks across an emotional field. Users can move through a luminous atlas of paintings, focus on a specific feeling, inspect individual works, and generate shareable artwork cards.

Live demo: <https://emotion-museum.kesenlab.workers.dev>

Chinese documentation: [README.zh-CN.md](./README.zh-CN.md)

[Launch the demo](https://emotion-museum.kesenlab.workers.dev)

## Preview

![Emotion Museum overview](./github-assets/output/emotion-museum-github-01.png)

## Why It Exists

Art history is often organized by chronology, school, institution, and authorship. Those structures are important, but they are not always how people encounter images in daily life.

Emotion Museum experiments with a different entry point: mood as an interface. It asks a simple question:

> What if a museum could be navigated by how an image feels?

The project is designed as a lightweight digital humanities project, a visual browsing interface, and a public-facing cultural experience.

## Highlights

- **Emotion-based artwork atlas**  
  Paintings are mapped onto 13 mood fields, including calm, tenderness, joy, excitement, anger, longing, dread, unease, melancholy, solitude, bewilderment, reverence, and wonder.

- **Curated public-domain and open-access collection**  
  The current dataset includes 135 artworks from sources such as The Metropolitan Museum of Art and Wikimedia Commons.

- **Fast visual browsing**  
  The atlas uses lightweight WebP thumbnails for the initial map while preserving full-size local images for detail panels and share cards.

- **Interactive focus mode**  
  Selecting an emotion highlights related artworks and draws connection lines between the mood field and matching works.

- **Manual emotion tour**  
  A cinematic browsing mode lets users move through emotions with on-screen controls or keyboard navigation.

- **Shareable artwork cards**  
  Each artwork can open a card layout with artwork notes, mood interpretation, and artist context.

- **Cloudflare-ready deployment**  
  The repository includes a minimal Cloudflare Workers + Static Assets setup.

## Demo

<https://emotion-museum.kesenlab.workers.dev>

## Quick Start

```bash
npm install
npm run dev
```

Wrangler will print a local development URL.

## Deploy To Cloudflare

Create a Cloudflare API token with Workers deployment permissions, then run:

```bash
CLOUDFLARE_API_TOKEN="your-token" npm run deploy
```

Never commit API tokens. Use environment variables locally and repository secrets in CI.

## Project Structure

```text
public/
  index.html                         # Main single-page app
  art-nebula-assets/
    manifest.json                    # Local image and thumbnail manifest
    met-expansion.json               # Artwork dataset
    local-data.js                    # Offline data bundle loaded by the app
    images/                          # Cached full-size artwork images
    thumbs/                          # Lightweight WebP thumbnails for the atlas
    export-data/                     # On-demand embedded image data for share-card export
  vendor/                            # Browser-side export dependency
github-assets/
  output/                            # README preview image
src/
  worker.js                          # Cloudflare Worker entry
wrangler.toml                        # Cloudflare deployment config
ATTRIBUTIONS.md                      # Artwork source list
```

## Data And Images

The project bundles cached artwork images to keep the demo stable and fast. The atlas uses thumbnails for the initial view, then loads larger images only when an artwork is selected or used in a share card.

Current local image profile:

- 135 full-size artwork images
- 135 WebP thumbnails
- On-demand embedded export data for PNG/JPG share-card downloads
- 224 manifest image entries, including historical cache records
- About 48 MB of public assets

## Rights And Attribution

The application code is released under the MIT License.

Artwork images and artwork metadata are **not** covered by the MIT License. They remain subject to the rights statements, licenses, and terms of their original source institutions or source projects.

Before reusing or redistributing the bundled artwork images, review the source links in [ATTRIBUTIONS.md](./ATTRIBUTIONS.md).

## Design Notes

Emotion Museum uses mood as a spatial interface. Each artwork has up to three associated emotions. The initial atlas blends semantic placement with an organic nebula-like distribution so the view feels alive rather than grid-based. When an emotion is selected, matching artworks are gathered into focus and connected back to the selected mood field.

The interface is intentionally bilingual in places: the product identity and mood system are readable in both Chinese and English, while the current artwork notes are primarily written in Chinese.

## Roadmap

- Add reproducible artwork ingestion and thumbnail generation scripts.
- Expand metadata quality, including rights statements and source-specific license fields.
- Add search by artist, title, period, source, and mood.
- Improve mobile layout and accessibility.
- Split the current single-file app into smaller modules if the project grows.
- Add optional language switching for artwork notes.

## Contributing

Contributions are welcome, especially around metadata quality, accessibility, performance, and new browsing modes.

Please keep artwork rights and attribution visible when adding new images or metadata.
