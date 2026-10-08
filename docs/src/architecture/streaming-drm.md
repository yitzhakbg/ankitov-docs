# Streaming & DRM Architecture

AnkiTov uses **Selkies** for streaming — the execution environment runs in a secure, remote host container. Students interact through an interactive HTML5 video feed via a Progressive Web App (PWA).

## Why Streaming?

| Challenge | Solution |
|---|---|
| Admin complexity across thousands of devices | Centralized container management |
| Add-on conflicts & version drift | Read-only container images |
| IP vulnerability (DB access) | No filesystem exposed to user |
| Platform fragmentation | PWA works on any browser |

## DRM Add-on

The proprietary add-on (Layer 3) hooks into Anki via:

| Hook | Purpose |
|---|---|
| `gui_hooks.card_will_render` | Intercept encrypted card data, decrypt in memory |
| `gui_hooks.browser_menus_did_init` | Disable exports and clipboard access |
| `gui_hooks.reviewer_did_answer_card` | Dispatch telemetry for billing/adherence |