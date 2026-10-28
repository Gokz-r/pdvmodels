# PDFcurry Translate: translation models

The models PDFcurry Translate uses, kept in the repository as a backup and published with the app
(`dist/translate/models`), so the translator never depends on another website. Prepared by
`translate/tools/fetch-models.mjs` and stored here by `translate/tools/pack-models.mjs`; do not edit by hand.

- Files over 20 MiB are stored in parts of 20 MiB (`<file>.part0`, `.part1`, ...): GitHub refuses files over
  100 MB and Cloudflare Pages files over 25 MiB. The app downloads the parts and joins them, then checks the whole
  file against its SHA-256 in `translate/src/engine/models.json`.
- `SHA256SUMS`: the checksum of every file stored here. To check a copy restored from the repository:
  `cd translate/models && sha256sum -c SHA256SUMS`.

| Folder | What | Licence | Source |
|---|---|---|---|
| `bergamot/<from>-<to>/` | Mozilla's translation models (Firefox Translations), one direction each | MPL-2.0 | Mozilla, https://github.com/mozilla/translations |
| `indictrans2/en-indic/`, `indictrans2/indic-en/` | IndicTrans2 (Tamil, Hindi, Bengali), 16-bit ONNX | MIT (`LICENSE` in each folder) | AI4Bharat, IIT Madras, https://github.com/AI4Bharat/IndicTrans2 |
| `fonts/` | Noto fonts for writing translations (Chinese, Japanese, Korean, Tamil, Hindi, Bengali) | SIL Open Font License 1.1 (`*.LICENSE.txt`) | Google Fonts |

396 files, 3.51 GiB. The legal notices of the translator (`THIRD_PARTY_NOTICES.txt`)
list each of them.
