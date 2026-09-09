# herdr-sidebar

**The sidebar your terminal was missing** — a VS Code-inspired file explorer + source
control panel in one dockable herdr pane.

<img src="docs/media/hero.png" alt="The sidebar Explorer and live preview interface" width="860">

**The full tour lives in the [repo README](../../README.md)** — features, screenshots,
keys, and settings.

## Install

Requires herdr 0.8 or newer.

```
herdr plugin install alexarthurs/herdr-sidebar/plugins/herdr-sidebar
```

or from a local checkout:

```
cargo build --release
herdr plugin link .
```

Open it (or just focus a tab — the hook docks it):

```
herdr plugin action invoke herdr-sidebar.open-sidebar-windows   # windows
herdr plugin action invoke herdr-sidebar.open-sidebar           # linux / macos
```

## Paste Image from Clipboard

Paste screenshots directly into your project and pass them straight to agents without leaving your terminal:

- **Context menu:** Right-click or press `m` on any folder → `Paste Image from Clipboard…`.
- **Keyboard shortcuts:** Press `p` or `Ctrl+V` on any folder in the Explorer tree.
- **Automatic `img/` creation:** Automatically creates an `img/` folder (or reuses an existing `img/` or `assets/` directory) and initializes an `img/.gitignore` (`*` and `!.gitignore`) so pasted images are never committed by accident.
- **Timestamped naming:** Saved as `clip_<timestamp>.png` using UNIX epoch timestamps.
- **Automatic 7-day retention sweep:** Automatically removes older `clip_*.png` images after 7 days to prevent repository bloat.
- **Automatic IPC path injection:** Automatically injects `./<relative-path>` into neighboring agent panes via Herdr IPC so your coding assistant is immediately primed with the image path.

