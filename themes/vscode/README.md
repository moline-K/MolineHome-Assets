# MolineHome VS Code Themes

This folder contains an installable VS Code theme extension with:

- `MolineHome Dark`
- `MolineHome Light`

Recommended font pairing:

- UI and app text: `Inter`
- Editor, terminal, and code: `JetBrains Mono`

## Local use

1. Copy or symlink this folder into your VS Code extensions directory, or package it with `vsce`.
2. Restart VS Code.
3. Run `Preferences: Color Theme`.
4. Select `MolineHome Dark` or `MolineHome Light`.

Typical local extensions directory on Windows:

```text
%USERPROFILE%\.vscode\extensions\
```

Recommended folder name if you copy it manually:

```text
kmoline.molinehome-themes-0.1.0
```

## Suggested font settings

```json
{
  "editor.fontFamily": "JetBrains Mono, Cascadia Code, Consolas, monospace",
  "terminal.integrated.fontFamily": "JetBrains Mono, Cascadia Code, Consolas, monospace",
  "scm.inputFontFamily": "Inter, Segoe UI, sans-serif",
  "chat.editor.fontFamily": "Inter, Segoe UI, sans-serif"
}
```

## Files

- `package.json` registers the themes with VS Code
- `themes/*.json` define workbench colors, token colors, and semantic token colors
- `icon.png` is the bundled marketplace/local extension icon

## Packaging

If you want a `.vsix` package:

1. Install `vsce` if you use extension packaging regularly.
2. From this folder, run `vsce package`.
3. In VS Code, run `Extensions: Install from VSIX...`.
