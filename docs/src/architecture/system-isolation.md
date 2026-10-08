# 5-Layer System Isolation

AnkiTov enforces a strict 5-layer hierarchy between student and host:

```
Layer 1: Cloud Gateway
  └─ Delivers ONLY interactive video feed
  └─ Prevents DB replication, filesystem extraction, reverse engineering
      │
      ▼
Layer 2: Unmodified Anki Core (Inside Container)
  └─ Stock Anki Desktop — 100% pristine, AGPL-3.0 compliant
      │
      ▼
Layer 3: AnkiTov DRM Add-on
  └─ Python hook interceptors (card_will_render, browser_menus_did_init)
  └─ In-memory cryptographic processor
  └─ Disables exports, copying, context menus, editing
      │
      ▼
Layer 4: HTML5 Stream (PWA)
  └─ Zero-config terminals — any browser-capable device
  └─ The SINGLE touchpoint exposed to the student
```

## Cryptographic Protection

- AES-256 encrypted premium content inside `.anki2` SQLite databases
- `gui_hooks.card_will_render` intercepts encrypted data → in-memory decryption via HTTPS gateway
- Active network connection required for DRM content — no offline study