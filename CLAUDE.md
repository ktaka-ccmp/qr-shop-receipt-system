# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**QR Shop Receipt System (電子領収書発行システム)** - A B2B2C SaaS platform that digitizes receipt issuance for business expense management.

**Core Value Proposition:**
- 100% accurate structured data (no OCR)
- Automatic compliance with Japan's Electronic Bookkeeping Law (電子帳簿保存法)
- Stamp tax elimination for merchants (¥200-400 per receipt → ¥0)

**Business Model:**
```
This Service → POS Vendors → Stores → End Users
    (API)        (Resale)    (Issue)   (Receive)
```

## Project Status

**Current Phase:** Planning/Documentation (no code implemented yet)

**Key Documentation:**
- `docs/PROJECT-HANDOFF.md` - Complete project context and handoff document
- `business/receipt-system-idea.md` - Business concept and feature specification
- `business/receipt-system-business-plan.md` - Market analysis and financials
- `patents/patent-analysis-revised.md` - Patent infringement risk analysis

## Planned Technology Stack

| Layer | Technology | Notes |
|-------|------------|-------|
| Backend | Rust + Axum | Owner's expertise |
| Database | PostgreSQL | Audit trail for compliance |
| Auth | OAuth2 / WebAuthn | Leverage `oauth2-passkey` crate |
| Infrastructure | GCP / Kubernetes | Existing operational knowledge |
| API | REST / GraphQL | POS vendor integration |

## Build Commands (when implemented)

```bash
# Rust project commands
cargo build
cargo test
cargo clippy
cargo fmt --all

# Run the server (planned)
cargo run --bin server
```

## Architecture Notes

### Data Model (Conceptual)

```
Store (店舗)
├── id, name, address
├── invoice_number (適格請求書発行事業者番号)
└── ...

User (利用者)
├── id, name, company_name
└── ...

Receipt (領収書)
├── id, store_id, user_id
├── amount, description
├── issued_at, created_at
└── ...

ReceiptHistory (訂正削除履歴)
├── id, receipt_id
├── action (create/update/delete)
├── changed_at, changed_by
└── previous_data (JSON)
```

### QR Code + One-Time Token Flow

```
Store QR: https://receipt.example.com/store/{store_token}
User QR:  https://receipt.example.com/user/{one_time_token}
```

- One-time tokens expire within hours to days
- Single read binds user account; token invalidates after use

### Privacy Design

- Store cannot see user IDs (only names/company)
- User cannot see store IDs (only names)
- No cross-party ID exposure

## Patent Constraints (Critical)

### DO (Safe to Implement)

- Electronic receipt storage and distribution
- Uniform display of transaction details
- Receipt download/printing
- Data export to accounting systems

### DON'T (Avoid These Features)

- Highlighting specific items with color/background changes (Toshiba Tec Patent 6598936)
- Point functionality (especially expiration management with highlighting)
- Automated account classification via keyword matching tables (freee Patent 5503795)

### CAUTION (Requires Attorney Review)

- "User displays QR → Store reads" flow may have patent implications
- Airレジ/Smaregi patent landscape unclear

## Development Phases

1. **Phase 1 (MVP):** Store API, User Web App, Admin Dashboard
2. **Phase 2:** Audit trail (Method B), Search, PDF/CSV export
3. **Phase 3:** Accounting software integration (freee, MoneyForward, Yayoi)
4. **Phase 4:** Certified timestamps, Invoice support, POS integration

## Integration Targets

| POS Service | Priority | API Support |
|-------------|----------|-------------|
| Square | High | REST API + Webhook |
| Smaregi (スマレジ) | High | Web API |
| STORES レジ | Medium | Available |
| Airレジ | Low | Limited |

## Owner Context

- **Owner:** Kimitoshi (Cluster Computing Corporation CEO)
- **Expertise:** Rust, OAuth2/WebAuthn, GCP/K8s infrastructure
- **Published Libraries:** `oauth2-passkey`, `oauth2-passkey-axum` on crates.io
