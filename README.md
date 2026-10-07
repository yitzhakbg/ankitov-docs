# AnkiTov Documentation

Source for the AnkiTov documentation site: **https://yitzhakbg.github.io/ankitov-docs/**

- mdBook built from [`docs/src`](./docs/src) and published to GitHub Pages by
  [.github/workflows/docs.yml](.github/workflows/docs.yml) (mdBook 0.5.4).
- This is the **public subset** of AnkiTov's documentation — closed
  architecture chapters are intentionally excluded. Regenerated from the
  AnkiTov sources; the core code lives at
  [ankitov](https://github.com/yitzhakbg/ankitov).

Build locally: `mdbook build docs` (config in [`docs/book.toml`](./docs/book.toml)).
