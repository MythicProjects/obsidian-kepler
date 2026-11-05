# Changelog

## 2.0.0

Kepler 2.0 changes what follows the mode. The note area, everything you read and study, now always uses the light palette. Switching between light and dark mode changes only the interface around it.

### What's new

- **A light page in both modes.** Notes (editor and reading view), hover previews, Kanban boards, Bases, canvas and Mermaid diagrams use the light palette in light and dark mode alike.
- **A light interface in light mode.** In light mode, sidebars, tabs, menus and the status bar use light greys instead of staying dark. They sit a step darker than the white page and are faintly tinted with your accent colour, so the page stands apart from the interface. A grey accent gives a neutral grey interface.
- **A softer dark interface.** The dark-mode background is now `#1F1F1F` instead of `#131313`, and the greys above it move up by the same step.

### Fixes

- **Mermaid diagrams no longer render black.** Obsidian 1.15 colours diagrams from `--mermaid-*` variables that it declares on `<body>`, so they took the interface colours. Kepler now resolves them against the note palette. On Obsidian 1.14, Kepler switches off the dark-mode inversion that turned diagrams black on a light page.
- **Graph view labels are easier to read in light mode.** They use the darker accent: 6.3:1 with the default accent, at least 6.1:1 with any accent.

### Accessibility

- New colour pairs for the light interface are documented in `theme.css` and checked by `tools/check_contrast.py` across 580 accents. Interface text is 4.5:1 or better, and icons are 3:1 or better.
- To keep these ratios, a few details changed in light mode:
  - Icons use a slightly darker accent.
  - The active row in the file explorer uses dark text, still marked by its accent tint and bar.
  - Calendar days from other months are more opaque.

### Upgrading from 1.x

- **The dark note palette is gone.** If you used Kepler for dark notes, the note area will now be light in dark mode too. This is the main change in 2.0.
- No settings to change. Your accent colour carries over and now also tints the light interface.
- Snippets that set colours on `body.theme-light` now affect the light interface, which is no longer dark.

### Requirements

Obsidian 1.14.5 or later, desktop and mobile. Tested with Obsidian 1.15.0.
