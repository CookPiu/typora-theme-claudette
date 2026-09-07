# Claudette

A warm, understated light theme for [Typora](https://typora.io).

Paper-toned background, a single terracotta accent, serif headings, sans-serif body text and hairline rules. Restraint over ornament.

![Claudette theme screenshot](screenshot.png)

![Claudette Dark theme screenshot](screenshot-dark.png)

## Features

- **Two variants** — `claudette.css` (light) and `claudette-dark.css` (dark). The dark file imports the light one and only swaps the tokens, so both stay in sync.
- **Warm paper palette** — `#faf9f5` page, `#f2f0e9` sidebar, `#ece9df` fills, near-black `#141413` text, alpha hairlines instead of solid gray borders, and one terracotta accent `#d97757` (interactive `#c6613f`) used sparingly.
- **Editorial typography** — serif headings at weight 400 with tight line-height; the first paragraph after an H1 is styled as a lead paragraph; H6 becomes a small uppercase label.
- **Quiet code blocks** — soft `#f5f4ed` surface, hairline border, 12px radius, language pill in the corner, and the syntax palette used on claude.com's code panels (keyword `#c2452d`, string `#9c4a21`, number `#9a6700`, function `#6f42c1`, comment `#6e7781`).
- **Hairline tables** — horizontal rules only, uppercase column headers, subtle row hover.
- **Whole-app styling** — sidebar, file tree, outline, quick-open, search panel, context menus, dialogs, buttons, source mode and scrollbars all follow the same palette and radii.
- **Print-ready** — decorations and hover states are stripped when exporting to PDF.

## Installation

1. Download `claudette.css` and `claudette-dark.css` (or the whole repository as a ZIP).
2. In Typora open **Preferences → Appearance → Open Theme Folder**.
3. Copy both files into that folder (the dark theme requires `claudette.css` next to it).
4. Restart Typora and pick **Claudette** or **Claudette Dark** from the **Themes** menu.

## Fonts

Claudette does not bundle any fonts. It prefers the following if installed and falls back to system fonts otherwise:

| Role | Preferred | Fallbacks |
|---|---|---|
| Headings | [Source Serif 4](https://fonts.google.com/specimen/Source+Serif+4) | Charter, Georgia, Noto Serif SC |
| Body | [Inter](https://rsms.me/inter/) | Source Sans 3, Segoe UI, PingFang SC, Microsoft YaHei |
| Code | [JetBrains Mono](https://www.jetbrains.com/lp/mono/) | Maple Mono, Cascadia Code, Consolas |

To change them, edit the three `--font-*` variables at the top of `:root` in `claudette.css`.

## Customization

All colors live in `:root` as CSS variables. The most useful ones:

```css
:root {
    --accent: #d97757;             /* terracotta accent */
    --accent-interactive: #c6613f; /* hover / active accent */
    --bg-primary: #faf9f5;         /* page */
    --bg-secondary: #f5f4ed;       /* code blocks */
    --bg-sidebar: #f2f0e9;         /* sidebar, search panel */
    --fg-primary: #141413;         /* body text */
    --line: rgba(31, 30, 29, .12); /* hairlines */
}
```

Font weights are declared as `--wt-regular` / `--wt-medium` / `--wt-semibold` (400 / 460 / 540). Variable fonts such as Inter render those exactly; static fonts snap to the nearest available weight.

The optional decorations (H1 rule, H3 dot, blockquote mark, asterisk on `<hr>`, table hover, …) are grouped at the end of the file under the `点缀` / decorations comment. Delete any block you do not want.

## License

MIT
