<div align="center">

```
   ██████╗██╗  ██╗ █████╗ ██╗███╗   ██╗███████╗
  ██╔════╝██║  ██║██╔══██╗██║████╗  ██║██╔════╝
  ██║     ███████║███████║██║██╔██╗ ██║███████╗
  ██║     ██╔══██║██╔══██║██║██║╚██╗██║╚════██║
  ╚██████╗██║  ██║██║  ██║██║██║ ╚████║███████║
   ╚═════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝╚═╝  ╚═══╝╚══════╝
```

# Multichain Smart Contracts Portfolio

#### Solidity · Anchor · Move · FunC.
#### Production contracts across **EVM · Solana · Sui · TON.**

[![Status](https://img.shields.io/badge/status-shipped-b9ff66?style=for-the-badge&labelColor=060607)](#)
[![Role](https://img.shields.io/badge/role-Smart%20Contract%20Engineer-b9ff66?style=for-the-badge&labelColor=060607)](#)
[![Chains](https://img.shields.io/badge/chains-EVM%20·%20Solana%20·%20Sui%20·%20TON-ededed?style=for-the-badge&labelColor=060607)](#)
[![Code](https://img.shields.io/badge/code-mostly%20private-1f1f24?style=for-the-badge&labelColor=060607)](#)

</div>

---

> **TL;DR** — A unified portfolio of on-chain work across four execution
> environments. Same engineer, four languages, four memory and execution
> models. This page is the index.

---

## Why one repo for everything

Working across EVM, Solana, Sui, and TON is **not the sum of four
specialties** — it is its own skill. Each environment has its own memory
model, account model, and finality semantics. This portfolio is the
shortest answer to *"can you ship a contract on chain X?"* — yes, and on
the other three too.

> This repository indexes contract work across systems. Implementation
> code is private unless otherwise noted.

---

## EVM (Solidity)

| Project | What it is |
|---|---|
| **SURGE Smart Contracts** | Production contract suite for SURGE — design, tests, deployment. |
| **EVM Pump.fun-style AMM** | Bonding-curve token launcher adapted to EVM execution model. |
| **BlastFarm** | Yield-farming contracts on Blast L2, paired with a frontend. |
| **On-chain Raffle** | Provably-fair raffle using Chainlink VRF. |
| **Token Claim System** | Merkle-tree claim contracts with off-chain proof generator. |
| **Launchpad sale contracts** | The on-chain side of [WeWay](https://github.com/eldardzh/weway-launchpad). |

**Stack:** Solidity · Foundry · Hardhat · Ethers · viem.

---

## Solana (Anchor / native)

| Project | What it is |
|---|---|
| **Sundog Staking Program** | Staking with reward accounting; companion to the [Sundog product](https://github.com/eldardzh/sundog). |
| **HipHop Programs** | Contract layer of the [HipHop DeFi stack](https://github.com/eldardzh/hiphop-defi). |
| **Sale & claim programs** | Solana side of multichain launchpad mechanics. |

**Stack:** Anchor · `@solana/web3.js` · TypeScript SDKs.

---

## Sui (Move)

| Project | What it is |
|---|---|
| **Sui Modules** | Move modules and integration scripts for Sui-based products. |
| **Sui / Hippo Toolkit** | Companion modules to the Sui product line. |

**Stack:** Move · Sui SDK · TypeScript SDKs.

See also: [`sui-onchain-toolkit`](https://github.com/eldardzh/sui-onchain-toolkit).

---

## TON (FunC / Tact)

| Project | What it is |
|---|---|
| **TON Launchpad Contracts** | Sale / claim / vesting logic for the [TON Launchpad](https://github.com/eldardzh/ton-launchpad). |

**Stack:** FunC · Tact · TON SDK · TypeScript.

---

## Architectural Decisions & Tradeoffs

### 1. Same domain logic, chain-specific adapters

The launchpad sale-engine logic (eligibility, allocation, vesting) is
defined **once** in domain code. Per-chain contracts implement settlement
semantics natively. Result: a new chain is a bounded adapter problem.

### 2. Off-chain proof generators, not on-chain bloat

Merkle claims and similar primitives generate proofs off-chain, keeping
contracts small and gas-cheap.

### 3. Tests as the spec

Each contract suite has a test surface that doubles as its specification —
behavioral, not line-coverage. Easier to evolve, harder to mis-deploy.

### 4. Foundry where it fits

For EVM I default to **Foundry** for unit tests and Hardhat for scripts
and deploys. Best of both — fast fuzzing, ergonomic deployment.

---

## Engineering Invariants

- **Never** ship a contract without a corresponding test that demonstrates the failure mode it prevents
- **Never** mix domain logic with chain quirks in shared code
- **Never** ship a contract change without a corresponding off-chain (indexer / API) migration
- **Never** trust user-supplied input to a privileged path

---

## Related Public Documents

- [`weway-launchpad`](https://github.com/eldardzh/weway-launchpad) — multichain launchpad these contracts power
- [`hiphop-defi`](https://github.com/eldardzh/hiphop-defi) — full DeFi stack on top of these primitives
- [`sui-onchain-toolkit`](https://github.com/eldardzh/sui-onchain-toolkit) — Sui-specific deep dive
- [`ton-launchpad`](https://github.com/eldardzh/ton-launchpad) — TON-specific deep dive

---

<div align="center">

#### **Contact**
[**eldardzh.com**](https://eldardzh.com) · [**@EldarDissmay**](https://x.com/EldarDissmay) · **dissmay21@gmail.com**

<sub>© 2026 · Eldar D. · Built 2023 — 2025.</sub>

</div>
