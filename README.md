# Kepler

A theme for [Obsidian](https://obsidian.md) 1.14.5+ on desktop and mobile, built around one idea: **the app stays out of the way, and the note is for reading.**

## What makes Kepler different

- **Always-dark interface, light or dark note.** Sidebars, tabs, menus and the status bar stay dark in both modes. Switching Obsidian to light mode changes only the note area: editor, reading view, hover previews, canvas, Bases and Kanban boards. So you can read on white without the whole window flashing bright. The header above a canvas, base or board stays dark like a note's, and the canvas controls switch with the canvas. PDF, image, audio, video, web viewer and graph views keep the dark UI by design, and Excalidraw switches its own theme.
- **Reading-first typography.** Inter at a 1.65 line height and a ~70-character line (720 px with *Readable line length* on), with even 0.75 em spacing between paragraphs and headings. Source and reading views use identical margins, so switching between them doesn't move the text.
- **Headings you can tell apart at a glance.** Each level has its own shape, not just its own size: H1 is an accent block, H2 is underlined, H3 has a side bar, H4 is accent-coloured with a short underline, H5 is an uppercase label, and H6 is italic with a dashed rule.
- **Documented contrast.** Every text colour pair has its WCAG 2.x ratio next to it in `theme.css`, and `tools/check_contrast.py` checks them all, for the default accent and across 580 custom accents. Body text is 4.5:1 or better in both modes, and code syntax colours are 4.5:1 or better on their code background. Syntax also uses shape (bold keywords, italic comments), not colour alone.
- **Built on Obsidian's variables.** Kepler sets Obsidian's own CSS variables wherever one exists, and uses selectors only where none does, so it stays light and survives app updates. Every theme-owned variable is prefixed `--kepler-*`.

## Custom accent
Kepler follows **Settings → Appearance → Accent color**. The colour you pick sets the hue and saturation of every accent detail: links, the heading blocks and bars, highlights, icons, the callout accent, the code-block edge, code keywords and tags, the graph and the Excalidraw active tool.

Kepler fixes the lightness of each of those elements to keep its documented contrast, so what you see is a tuned version of the picked colour, not the same hex. Very saturated colours are toned down a little, which also keeps them from clipping. A grey accent gives a grey theme. Code blocks stay grey with any accent, and the other syntax colours (functions, strings, values, properties) keep their fixed colours, so code stays readable whatever you pick. With no custom accent, Kepler uses its default teal.

On mobile WebViews without relative colour support (older than iOS 18 or Android WebView 119), Kepler falls back to its default teal.

<details>
<summary><b>🎨 Click to expand Accent & Mode Showcase Gallery</b></summary>
<br>

### Blue / Teal (Default Accent)
| Note View (White) | Note View (Dark) |
| :-: | :-: |
| <img src="_img/blue-white.png" width="100%" alt="Blue White View"> | <img src="_img/blue-dark.png" width="100%" alt="Blue Dark View"> |
| **Code View (White)** | **Code View (Dark)** |
| <img src="_img/blue-code-white.png" width="100%" alt="Blue Code White View"> | <img src="_img/blue-code-dark.png" width="100%" alt="Blue Code Dark View"> |

---

### Green Accent
| Note View (White) | Note View (Dark) |
| :-: | :-: |
| <img src="_img/green-white.png" width="100%" alt="Green White View"> | <img src="_img/green-dark.png" width="100%" alt="Green Dark View"> |
| **Code View (White)** | **Code View (Dark)** |
| <img src="_img/green-code-white.png" width="100%" alt="Green Code White View"> | <img src="_img/green-code-dark.png" width="100%" alt="Green Code Dark View"> |

---

### Red Accent
| Note View (White) | Note View (Dark) |
| :-: | :-: |
| <img src="_img/red-white.png" width="100%" alt="Red White View"> | <img src="_img/red-dark.png" width="100%" alt="Red Dark View"> |
| **Code View (White)** | **Code View (Dark)** |
| <img src="_img/red-code-white.png" width="100%" alt="Red Code White View"> | <img src="_img/red-code-dark.png" width="100%" alt="Red Code Dark View"> |

---

### Yellow / Orange Accent
| Note View (White) | Note View (Dark) |
| :-: | :-: |
| <img src="_img/yellow-white.png" width="100%" alt="Yellow White View"> | <img src="_img/yellow-dark.png" width="100%" alt="Yellow Dark View"> |
| **Code View (White)** | **Code View (Dark)** |
| <img src="_img/yellow-code-white.png" width="100%" alt="Yellow Code White View"> | <img src="_img/yellow-code-dark.png" width="100%" alt="Yellow Code Dark View"> |

</details>

## Supported plugins

| Plugin | What Kepler does |
|---|---|
| **Dataview** | Numbered rows and a header rule in `TABLE` views. |
| **Excalidraw** | The active tool uses the light accent with dark icons, in both modes. |
| **Code Styler** | Code blocks follow the note's light/dark palette instead of the dark UI. |
| **Kanban** | Boards follow the note's light/dark palette. Cards are raised above their lanes (lighter in dark mode), lanes alternate two neutral greys, and the add buttons stay readable on hover. |
| **Calendar** | The accent for today, a faint accent tint on weekends, readable other-month days, and theme colours for headings. |

## Supported plugins

| Plugin | What Kepler does |
|---|---|
| **Dataview** | Numbered rows and a header rule in `TABLE` views. |
| **Excalidraw** | The active tool uses the light accent with dark icons, in both modes. |
| **Code Styler** | Code blocks follow the note's light/dark palette instead of the dark UI. |
| **Kanban** | Boards follow the note's light/dark palette. Cards are raised above their lanes (lighter in dark mode), lanes alternate two neutral greys, and the add buttons stay readable on hover. |
| **Calendar** | The accent for today, a faint accent tint on weekends, readable other-month days, and theme colours for headings. |

## File explorer

Folders and files get a simple line icon in the accent colour (Lucide's folder, open folder and file), and the folder that holds the open file is tinted, with its icon in the lighter accent. Rows that already have an icon from Iconize keep theirs. To turn Kepler's icons off, add this CSS snippet:

```css
body { --kepler-tree-icons: none; }
```

## CSS classes

Add these to a note's `cssclasses` property.

| Class | Effect |
|---|---|
| `img-zoom` | In reading view, press and hold an image to see it fullscreen; release to return. |

```yaml
---
cssclasses:
  - img-zoom
---
```

## Recommended settings

- **Settings → Editor → Readable line length:** on (for the 720 px column).
- **Settings → Appearance → Show indentation guides:** on. Kepler relies on Obsidian's own guides in the file explorer and tag pane.

## Installation

### Community theme store
1. Open **Settings → Appearance → Themes → Manage**.
2. Search for **Kepler**, then select **Install and use**.

### BRAT
1. Install the **BRAT** plugin from the community plugins.
2. Run **BRAT: Add a beta theme for testing** and enter this repository's URL.
3. Pick **Kepler** in **Settings → Appearance → Themes**.

### Manual
1. Download `theme.css` and `manifest.json` from the latest release.
2. Put them in `<your vault>/.obsidian/themes/Kepler/`.
3. Reload Obsidian and pick **Kepler** in **Settings → Appearance → Themes**.

## Testing

Copy the `tests` folder to the root of a vault: the canvas embeds `tests/kepler-test.md` by that path.

- `kepler-test.md` exercises every element the theme styles. Open it in both modes, in live preview and reading view.
- `kepler-test.canvas` has one card per colour, a markdown card, a note embed, labelled groups and labelled edges.
- `kepler-test.base` shows the files in its own folder as a table, a grouped table, cards and a kanban board.
- `kepler-test-kanban.md` is a board for the Kanban plugin.

## License

[MIT](LICENSE) © 2026 Mateu Bennasar
