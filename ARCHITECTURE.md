# ARCHITECTURE.md
## Ravencoin Asset Exchange – Phase 1

This document defines the **technical boundaries** of Phase 1.
Anything not described here is intentionally excluded.

---

## High-Level Architecture

The system is intentionally simple and modular.

### Core Components

### 1. Swap Orchestrator (Off-Chain)
- Coordinates the atomic swap lifecycle
- Maintains swap state
- Does NOT custody funds
- Can be restarted without loss of funds

### 2. Ravencoin RPC Interface
- Communicates directly with Ravencoin Core
- Testnet only
- Responsible for:
  - Asset transfers
  - Raw transaction creation
  - Script generation
  - Transaction broadcasting

### 3. HTLC Logic
- Hashlock (secret preimage)
- Timelock (refund path)
- Enforced on-chain
- No trusted third parties

### 4. Minimal Interface (CLI or Web)
- Create swap offer
- Accept swap offer
- Monitor swap progress

---

## On-Chain vs Off-Chain Responsibilities

| Layer | Responsibility |
|-----|---------------|
| On-chain | Asset custody, security, settlement |
| Off-chain | Coordination, UX, order discovery |

At no point should off-chain components control user funds.

---

## Atomic Swap Flow (Simplified)

1. Party A creates secret + hash
2. Party A locks Asset A with HTLC
3. Party B locks Asset B with same hash
4. Party A redeems Asset B (reveals secret)
5. Party B redeems Asset A using revealed secret
6. Timeout paths allow refunds if swap fails

---

## State Machine (Off-Chain)

- OFFERED
- LOCKED
- REDEEMED
- REFUNDED

No other states should exist in Phase 1.

---

## Non-Goals

The following are intentionally excluded:

- Performance optimization
- Governance logic
- Fee models
- Monetization
- Scalability beyond demo usage

---

## Design Principles

- Security > speed
- Clarity > cleverness
- Determinism > flexibility
- Minimalism > completeness
