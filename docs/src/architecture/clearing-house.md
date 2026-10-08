# Clearing House Model

The ultimate evolution of AnkiTov — a marketplace connecting educational publishers, content creators, and school systems.

## How It Works

1. **Publishers** upload AES-256 encrypted premium decks to the Commerce Gateway
2. **Schools** purchase access via consumption-based billing
3. **Students** study via streaming (DRM enforced at Layer 3)
4. **Telemetry** pings (`reviewer_did_answer_card`) flow to the audit ledger
5. **Revenue** is automatically distributed to content creators

## Immutable Audit Ledger

All telemetry is stored in an append-only SeaORM relational log via Loco.rs. Aggregated periodically for billing verification and revenue distribution.