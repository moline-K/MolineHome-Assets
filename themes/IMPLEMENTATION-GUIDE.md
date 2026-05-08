# MolineHome Theme Implementation Guide

This guide standardizes the MolineHome app stack on:

- UI font: `Inter`
- Code font: `JetBrains Mono`
- Accent palette: MolineHome navy + orange

## Shared Standard

UI/app font stack:

```text
"Inter", "Segoe UI", sans-serif
```

Code font stack:

```text
"JetBrains Mono", "Cascadia Code", "Consolas", monospace
```

Primary theme references:

- Shared palette: [themes/shared/molinehome-palette.json](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/shared/molinehome-palette.json)
- Obsidian theme: [themes/obsidian/MolineHome/theme.css](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/obsidian/MolineHome/theme.css)
- Codex imports: [themes/codex](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/codex)
- VS Code theme: [themes/vscode](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/vscode)
- Authentik CSS: [public/assets/css/authentik.css](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/public/assets/css/authentik.css)

## Obsidian

Theme files:

- [themes/obsidian/MolineHome/manifest.json](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/obsidian/MolineHome/manifest.json)
- [themes/obsidian/MolineHome/theme.css](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/obsidian/MolineHome/theme.css)
- bundled Inter files in [themes/obsidian/MolineHome/fonts/inter](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/obsidian/MolineHome/fonts/inter)

Install:

1. Copy the `MolineHome` folder into your vault’s `.obsidian/themes/` directory.
2. In Obsidian, open `Settings` -> `Appearance`.
3. Under `Themes`, select `MolineHome`.
4. Set the base color scheme to `Light` or `Dark`.

Notes:

- The theme loads `Inter` locally, so Obsidian does not need the font installed system-wide.
- Code elements use `JetBrains Mono` first, then fall back to `Cascadia Code` and `Consolas`.

## Codex

Files:

- [themes/codex/molinehome-codex-light.txt](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/codex/molinehome-codex-light.txt)
- [themes/codex/molinehome-codex-dark.txt](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/codex/molinehome-codex-dark.txt)
- [themes/codex/README.md](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/codex/README.md)

Import strings:

Light:

```text
codex-theme-v1:{"codeThemeId":"one","variant":"light","theme":{"accent":"#EF8221","surface":"#F6F8FB","ink":"#051337","contrast":44,"opaqueWindows":true,"fonts":{"ui":"Inter","code":"JetBrains Mono"},"semanticColors":{"diffAdded":"#2E8B57","diffRemoved":"#C84A3A","skill":"#2563EB"}}}
```

Dark:

```text
codex-theme-v1:{"codeThemeId":"one","variant":"dark","theme":{"accent":"#F3901A","surface":"#0E203D","ink":"#EDF3F8","contrast":54,"opaqueWindows":true,"fonts":{"ui":"Inter","code":"JetBrains Mono"},"semanticColors":{"diffAdded":"#48C78E","diffRemoved":"#FF8A80","skill":"#6BA4FF"}}}
```

Install:

1. Open Codex theme settings.
2. Use the `Import` action for the light or dark theme.
3. Paste the full string.
4. Apply the theme.

## VS Code

Theme files:

- [themes/vscode/package.json](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/vscode/package.json)
- [themes/vscode/themes/molinehome-dark-color-theme.json](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/vscode/themes/molinehome-dark-color-theme.json)
- [themes/vscode/themes/molinehome-light-color-theme.json](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/vscode/themes/molinehome-light-color-theme.json)

Install the theme:

1. Copy or symlink [themes/vscode](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/themes/vscode) into your VS Code extensions directory, or package it with `vsce`.
2. Restart VS Code.
3. Run `Preferences: Color Theme`.
4. Select `MolineHome Dark` or `MolineHome Light`.

Recommended `settings.json`:

```json
{
  "editor.fontFamily": "JetBrains Mono, Cascadia Code, Consolas, monospace",
  "terminal.integrated.fontFamily": "JetBrains Mono, Cascadia Code, Consolas, monospace",
  "scm.inputFontFamily": "Inter, Segoe UI, sans-serif",
  "chat.editor.fontFamily": "Inter, Segoe UI, sans-serif"
}
```

Notes:

- VS Code themes control colors, not full application typography.
- Editor and terminal fonts are configurable.
- Some VS Code chrome still follows OS/Electron behavior.

## Authentik

Theme file:

- [public/assets/css/authentik.css](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/public/assets/css/authentik.css)

Bundled fonts:

- [public/assets/fonts/inter/Inter-Variable.ttf](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/public/assets/fonts/inter/Inter-Variable.ttf)
- [public/assets/fonts/inter/Inter-Italic-Variable.ttf](C:/Users/kmoline/OneDrive%20-%20Avenue%20Consultants/Documents/Personal/MolineHome-Assets/public/assets/fonts/inter/Inter-Italic-Variable.ttf)

What it does:

- Loads `Inter` locally with `@font-face`
- Applies `Inter` to the main UI controls
- Uses `JetBrains Mono` for code-like elements

Deploy:

1. Serve the `public/assets` directory wherever Authentik can access it.
2. Point Authentik at `authentik.css` as your custom stylesheet.
3. Confirm the `/assets/fonts/inter/` paths resolve from the Authentik host.

## Recommendation

If you only want one standard across the homelab, use:

- UI: `Inter`
- Code: `JetBrains Mono`

That is the cleanest common stack across Obsidian, Codex, VS Code, and self-hosted service UIs.
