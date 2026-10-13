# atara-roll-translations

Static hosting for the on-device translation model used by [Atara Roll](https://github.com/AtaraBastruka)
(an offline D&D character sheet). Served through GitHub Pages so the app can download the files in the
browser, once, when the user opts in to translating content. Nothing runs here: it is only files.

## What is in here

| Path | What | Size (gzip) |
| --- | --- | --- |
| `models/en-es/model.enes.intgemm.alphas.bin.gz` | English to Spanish translation model | ~22.7 MB |
| `models/en-es/lex.50.50.enes.s2t.bin.gz` | Lexical shortlist | ~2.3 MB |
| `models/en-es/vocab.enes.spm.gz` | SentencePiece vocabulary | ~0.4 MB |
| `models/en-es/manifest.json` | Sizes and SHA-256 of every file; the app checks them after download | |

## Attribution and license

These model files are **unmodified copies** of the Firefox Translations models published by Mozilla,
built for the [Bergamot](https://github.com/mozilla/bergamot-translator) / [Marian](https://marian-nmt.github.io/) engine
(`base-memory` architecture, FLORES200+ BLEU 27.5, COMET22 0.854). They are the same gzip files Mozilla
publishes; the compressed model decompresses to the uncompressed SHA-256 listed in `manifest.json`.

- Source: https://github.com/mozilla/firefox-translations-models and
  https://github.com/mozilla/translations (training pipeline). The files were copied from Mozilla's public
  model storage, listed in the registry at
  https://storage.googleapis.com/moz-fx-translations-data--303e-prod-translations-data/db/models.json
  (exact upstream folder in `manifest.json`).
- License: [Mozilla Public License 2.0](LICENSE). The files are redistributed as published, without changes,
  under the same license. The Source Code Form is available at the links above.
- The translation engine (`bergamot-translator`, also MPL-2.0) is not part of this repository.

If you are Mozilla and want something changed or removed, please open an issue.
