# Long-Term Vision

> **Status note (2026-10):** The Two-Tier Ecosystem, streaming/DRM, and Clearing
> House material below describes the long-term *vision*. The implemented core
> today is the backend + IMP pipeline — `project-knowledge/prong-progress.md`
> is the re-baselined source of truth.

> **KEEP PRIVATE (owner, 2026-10-07):** this chapter carries the closed-pillar
> architecture prose (proprietary Commerce Gateway tier, streaming/DRM layers,
> Clearing House). It is deliberately outside the OSS export.

## Two-Tier Ecosystem

| Tier | License | Scope |
|------|---------|-------|
| **AnkiTov Core** | AGPL-3.0 | Multi-tenant directory, anki-cloud sync protocol, libSQL WAL forensic aggregation |
| **AnkiTov Commerce Gateway** | Proprietary | Enterprise streaming, premium marketplace, consumption-based monetization |

## 5-Layer System Isolation


```unknown
Layer 1: Cloud Gateway        → Delivers ONLY interactive low-latency video feed
Layer 2: Unmodified Anki Core → Stock Anki Desktop (AGPL-3.0, 100% pristine)
Layer 3: AnkiTov DRM Add-on   → Python hook interceptors, in-memory crypto processor
Layer 4: HTML5 Stream (PWA)   → Single touchpoint exposed to the student
```


- **Streaming via Selkies:** students interact through a browser/PWA video feed;
  no access to `.anki2` databases, add-on source, or developer tools.
- **DRM:** AES-256 encrypted premium content; in-memory decryption via
  `gui_hooks.card_will_render`; exports/copy/edit suppressed for premium content.
- **Clearing House:** pay-by-use billing driven by `gui_hooks.reviewer_did_answer_card`
  telemetry → immutable SeaORM audit ledger → automated revenue distribution.
