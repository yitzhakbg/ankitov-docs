# Streaming Architecture

AnkiTov uses **Selkies** for streaming — the execution environment runs in a secure, remote host container. Students interact through an interactive HTML5 video feed via a Progressive Web App (PWA).

## Why Streaming?

| Challenge | Solution |
|---|---|
| Admin complexity across thousands of devices | Centralized container management |
| Add-on conflicts & version drift | Read-only container images |
| IP vulnerability (DB access) | No filesystem exposed to user |
| Platform fragmentation | PWA works on any browser |

