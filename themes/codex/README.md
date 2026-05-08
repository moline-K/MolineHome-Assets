# MolineHome for ChatGPT Codex

As of May 7, 2026, OpenAI's public ChatGPT and Codex documentation exposes:

- theme mode selection (`Light`, `Dark`, or `System`)
- accent color selection in ChatGPT

OpenAI does not appear to publish a formal theme-schema reference in the help docs I found, but the Codex app currently supports theme import strings using the `codex-theme-v1:` prefix. The import payloads in this folder are based on the live UI format visible in the app and cross-checked against current public discussion of the feature.

This folder therefore includes both a palette guide and ready-to-paste Codex app import strings.

## Copy/paste imports

Light theme:

`codex-theme-v1:{"codeThemeId":"one","variant":"light","theme":{"accent":"#EF8221","surface":"#F5F7FA","ink":"#051337","contrast":49,"opaqueWindows":true,"fonts":{"ui":"Inter","code":"JetBrains Mono"},"semanticColors":{"diffAdded":"#2E8B57","diffRemoved":"#C84A3A","skill":"#2563EB"}}}`

Dark theme:

`codex-theme-v1:{"codeThemeId":"one","variant":"dark","theme":{"accent":"#F3901A","surface":"#0D203D","ink":"#EDF3F8","contrast":61,"opaqueWindows":true,"fonts":{"ui":"Inter","code":"JetBrains Mono"},"semanticColors":{"diffAdded":"#48C78E","diffRemoved":"#FF8A80","skill":"#6BA4FF"}}}`

Also saved as:

- `molinehome-codex-light.txt`
- `molinehome-codex-dark.txt`

## Recommended settings

### Dark mode

- Theme: `Dark`
- Accent target: `#F3901A`
- Primary reference background: `#0D203D`
- Secondary reference background: `#09162F`
- Main text reference: `#EDF3F8`
- UI font: `Inter`
- Code font: `JetBrains Mono`

### Light mode

- Theme: `Light`
- Accent target: `#EF8221`
- Primary reference background: `#F5F7FA`
- Secondary reference background: `#FFFFFF`
- Main text reference: `#051337`
- UI font: `Inter`
- Code font: `JetBrains Mono`

## Notes

- If the importer rejects a payload, the most likely cause is a `codeThemeId` mismatch with current built-in IDs. These strings use `"one"` because it is a conservative built-in fallback.
- These updated imports are tuned to better match the refined VS Code theme, especially clearer structural separation in bright rooms.
- The shared palette lives in `../shared/molinehome-palette.json`.
