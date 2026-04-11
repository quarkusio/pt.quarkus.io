# Contributing to pt.quarkus.io

This repository contains the Portuguese localization of [quarkus.io](https://quarkus.io).

## Quick Start

1. **Clone** this repository locally:

```bash
git clone https://github.com/quarkusio/pt.quarkus.io.git
cd pt.quarkus.io
```

2. **Fork** this repository on GitHub

3. **Configure push** to your fork:

```bash
git remote set-url --push origin https://github.com/your-username/pt.quarkus.io.git
```

4. **Create a branch** for your contribution following conventional branch naming (`<type>/<description>`):

```bash
git checkout -b docs/translate-mutiny-primer
```

## Where to Contribute

Translation files are in `l10n/po/pt_BR/`:

- **`_guides/`** — Main guides
- **`_posts/`** — Blog posts

### Current Priority: Review Existing Translations

The **top priority** is reviewing and improving already-translated guides. Focus on removing "fuzzy" marks, correcting auto-translations, and improving fluency.

Check the translation status to find what needs work:

| Category | Status File |
|----------|-------------|
| Main guides | [latest-guides-translation.csv](l10n/stats/latest-guides-translation.csv) |
| Blog posts | [posts-translation.csv](l10n/stats/posts-translation.csv) |
| Misc (includes, data) | [misc-translation.csv](l10n/stats/misc-translation.csv) |

## Workflow

1. Create a **GitHub issue** indicating which file you want to translate or review (avoids duplication)
2. Create a branch with a descriptive name: `docs/translate-filename`
3. Edit the corresponding `.po` files using tools like [POEdit](https://poedit.net/)
4. Commit with a clear message using the `docs:` prefix:

```bash
git commit -m "docs: translate mutiny-primer.adoc.po"
```

5. **Squash** into a single commit before the PR
6. Open a **Pull Request** targeting the `main` branch

> **Note:** The site is built automatically on PRs, and a preview link is added to the PR in ~5 minutes.

## Need More Details?

See the full [Translation Guide](translation-guide.pt.md) (in Portuguese) for:
- How text extraction works with po4a
- Auto-translation and fuzzy review process
- Override files and HTML templates
- Complete contribution workflow
