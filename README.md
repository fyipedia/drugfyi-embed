# drugfyi-embed

[![npm](https://img.shields.io/npm/v/drugfyi-embed)](https://www.npmjs.com/package/drugfyi-embed)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue)](https://www.typescriptlang.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/drugfyi-embed)

Embed **DrugFYI** widgets — drugs, glossary terms, interactive tools, and inline elements — on any website. **7 widget types**, zero dependencies, Shadow DOM style isolation, 4 built-in themes (light, dark, sepia, auto), 2 styles (modern, clean), and live data from the [DrugFYI](https://drugfyi.com) database.

Every widget includes a "Powered by DrugFYI" backlink and a medical disclaimer directing readers to consult healthcare professionals.

> **Try the interactive widget builder at [widget.drugfyi.com](https://widget.drugfyi.com)**

⚕️ **Medical Disclaimer**: All Health FYI widgets include an educational disclaimer. This information is for educational purposes only and should not replace professional medical advice.

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-drugfyi="entity" data-slug="drugs" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/drugfyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the DrugFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `entity` | `<div data-drugfyi="entity" data-slug="..."></div>` | Entity detail card |
| `glossary` | `<div data-drugfyi="glossary" data-slug="..."></div>` | Glossary term definition |
| `guide` | `<div data-drugfyi="guide" data-slug="..."></div>` | Guide summary card |
| `search` | `<div data-drugfyi="search" data-slug="..."></div>` | Search box |
| `compare` | `<div data-drugfyi="compare" data-slug="..."></div>` | Side-by-side comparison |
| `faq` | `<div data-drugfyi="faq" data-slug="..."></div>` | FAQ accordion |
| `formula` | `<div data-drugfyi="formula" data-slug="..."></div>` | Inline molecular formula with subscripts |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-drugfyi` | entity, compare, glossary, guide, search, faq, [tools] | required | Widget type |
| `data-slug` | e.g. "drugs" | — | Entity slug from the DrugFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-style-variant` | modern, clean | modern | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search Drugs..." | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-drugfyi="entity" data-slug="drugs" data-theme="light"></div>

<!-- Dark -->
<div data-drugfyi="entity" data-slug="drugs" data-theme="dark"></div>

<!-- Sepia -->
<div data-drugfyi="entity" data-slug="drugs" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-drugfyi="entity" data-slug="drugs" data-theme="auto"></div>
```

## Styles

```html
<!-- Modern (default) — clean lines, rounded corners, accent gradients -->
<div data-drugfyi="entity" data-slug="drugs" data-style-variant="modern"></div>

<!-- Clean — minimal borders, utility-focused, data-first aesthetic -->
<div data-drugfyi="entity" data-slug="drugs" data-style-variant="clean"></div>
```

## Web Components (Custom Elements)

As an alternative to `data-*` attributes, you can use native HTML custom elements:

```html
<!-- Custom element form -->
<drugfyi-entity slug="drugs" theme="light"></drugfyi-entity>
<drugfyi-compare slugs="drugs,other-slug"></drugfyi-compare>
<drugfyi-search placeholder="Search Drugs..."></drugfyi-search>

<script src="https://cdn.jsdelivr.net/npm/drugfyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/drugfyi-embed@1/dist/embed.min.js"></script>
```

### Specific version (production stability)

```html
<script src="https://cdn.jsdelivr.net/npm/drugfyi-embed@1.0.0/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install drugfyi-embed
```

```javascript
import 'drugfyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **2 styles**: Modern (accent gradients) and Clean (minimal, data-first)
- **4 themes**: Light, Dark, Sepia, Auto (OS preference detection)
- **CORS**: DrugFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Rich Snippets**: DefinedTerm JSON-LD injected for glossary widgets
- **Medical Disclaimer**: All widgets include an educational disclaimer footer
- **Bundle size**: Tree-shaken per site — only includes tools available on DrugFYI

## Learn More

Visit [drugfyi.com](https://drugfyi.com) — DrugFYI is a comprehensive drugs reference with interactive tools, guides, and developer resources.

- **API docs**: [drugfyi.com/developers/](https://drugfyi.com/developers/)
- **Widget builder**: [widget.drugfyi.com](https://widget.drugfyi.com)
- **npm package**: [npmjs.com/package/drugfyi-embed](https://www.npmjs.com/package/drugfyi-embed)
- **GitHub**: [github.com/fyipedia/drugfyi-embed](https://github.com/fyipedia/drugfyi-embed)

## Health FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Health FYI covers anatomy, drugs, pharmacology, and nutrition. Hub: [bodyfyi.com](https://bodyfyi.com).

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| AnatomyFYI | [anatomyfyi.com](https://anatomyfyi.com) | 14,692 anatomical structures, body systems, regions | [npm](https://www.npmjs.com/package/anatomyfyi-embed) |
| PillFYI | [pillfyi.com](https://pillfyi.com) | 4,934 FDA drugs, interactions, side effects | [npm](https://www.npmjs.com/package/pillfyi-embed) |
| **DrugFYI** | [drugfyi.com](https://drugfyi.com) | 4,009 drugs, molecular formulas, pharmacology | **[npm](https://www.npmjs.com/package/drugfyi-embed)** |
| NutriFYI | [nutrifyi.com](https://nutrifyi.com) | 15,236 foods, USDA nutrition data, 12 diets | [npm](https://www.npmjs.com/package/nutrifyi-embed) |

## FYIPedia Developer Tools

| Package | PyPI | npm | Description |
|---------|------|-----|-------------|
| colorfyi | [PyPI](https://pypi.org/project/colorfyi/) | [npm](https://www.npmjs.com/package/@fyipedia/colorfyi) | Color conversion, WCAG contrast, harmonies — [colorfyi.com](https://colorfyi.com) |
| emojifyi | [PyPI](https://pypi.org/project/emojifyi/) | [npm](https://www.npmjs.com/package/emojifyi) | Emoji encoding & metadata for 3,953 emojis — [emojifyi.com](https://emojifyi.com) |
| unitfyi | [PyPI](https://pypi.org/project/unitfyi/) | [npm](https://www.npmjs.com/package/unitfyi) | Unit conversion, 220 units — [unitfyi.com](https://unitfyi.com) |
| timefyi | [PyPI](https://pypi.org/project/timefyi/) | [npm](https://www.npmjs.com/package/timefyi) | Timezone ops & business hours — [timefyi.com](https://timefyi.com) |
| holidayfyi | [PyPI](https://pypi.org/project/holidayfyi/) | [npm](https://www.npmjs.com/package/holidayfyi) | Holiday dates & Easter calculation — [holidayfyi.com](https://holidayfyi.com) |
| fyipedia | [PyPI](https://pypi.org/project/fyipedia/) | — | Unified CLI for all FYI tools — [fyipedia.com](https://fyipedia.com) |

## Embed Widget

Embed [DrugFYI](https://drugfyi.com) widgets on any website with [drugfyi-embed](https://widget.drugfyi.com):

```html
<script src="https://cdn.jsdelivr.net/npm/drugfyi-embed@1/dist/embed.min.js"></script>
<div data-drugfyi="entity" data-slug="example"></div>
```

Zero dependencies · Shadow DOM · 4 themes (light/dark/sepia/auto) · [Widget docs](https://widget.drugfyi.com)

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
