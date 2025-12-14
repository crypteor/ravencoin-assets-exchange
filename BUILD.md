# BUILD.md
## Ravencoin Asset Exchange – Phase 1 (MRP)

### Purpose
This project aims to build **core infrastructure for trustless Ravencoin asset trading**.

This is **not** a full DEX at this stage.
Phase 1 is focused on delivering a **Minimum Real Product (MRP)** that proves atomic, non-custodial asset swaps on Ravencoin are possible, reliable, and developer-friendly.

---

## Phase 1 Goal (Non-Negotiable)

> Deliver a working **Ravencoin testnet asset ↔ asset atomic swap**.

If this works correctly, all future features (UI, DAO, governance, liquidity, etc.) can be built safely on top.

---

## What We Are Building (Phase 1 ONLY)

### 1. Atomic Swap Engine (Core)
- Ravencoin asset ↔ Ravencoin asset
- HTLC-based (hashlock + timelock)
- Fully non-custodial
- Testnet only

### 2. Off-Chain Order Coordination
- Simple offer / accept flow
- No custody
- No complex matching logic
- No price charts

### 3. On-Chain Settlement
- All asset movement happens on Ravencoin testnet
- No internal balances
- No escrow accounts

### 4. Minimal Interface
Choose one:
- CLI (preferred)
- or extremely basic web interface

The interface exists only to demonstrate functionality.

---

## What We Are NOT Building (Yet)

The following are **explicitly out of scope** for Phase 1:

- ❌ DAO / Governance
- ❌ Governance or utility token
- ❌ Liquidity pools
- ❌ AMM model
- ❌ Cross-chain swaps
- ❌ Mainnet deployment
- ❌ Mobile applications
- ❌ KYC / AML
- ❌ Advanced UI / UX

If it’s not required to demonstrate atomic swaps, it does not belong in Phase 1.

---

## Success Criteria

Phase 1 is considered successful if:

- Two parties can swap Ravencoin testnet assets trustlessly
- Neither party can cheat
- Funds are recoverable via timeout if the swap fails
- Code is open-source and documented
- A third party can reproduce the swap using the repo

---

## Timeline Expectation

- Target duration: **30 days**
- First functional demo target: **14 days**

---

## Development Philosophy

- Build first
- Ship small
- Prove everything
- Optimize later
- Community second, code first
