# GetFueled — Solana Lending Protocol

A decentralized lending protocol on Solana where lenders earn yield and borrowers can take loans using SOL as collateral.

## 🚀 How It Works

Lenders deposit SOL → Earn 5% APR
Borrowers lock collateral → Pay 8% APR
Protocol keeps 3% spread (profit)

## 🏦 Features

- Lend SOL – Deposit SOL, earn passive yield (5% APR)
- Borrow SOL – Lock collateral, borrow up to 80% LTV
- Liquidations – Automatic when health factor below 1.0
- Real-time prices – Pyth oracle integration (mainnet ready)

## 📊 Interest Rates

| Role | APR |
|------|-----|
| Lender | 5% |
| Borrower | 8% |
| Protocol | 3% (spread revenue) |

## 🛠 Tech Stack

- Smart Contract: Anchor (Rust)
- Blockchain: Solana
- Oracle: Pyth Network
- Frontend: React + TypeScript
- Wallet: Privy / Phantom

## 🔧 Instructions

| Instruction | Description |
|-------------|-------------|
| initialize_pool | Create global lending pool |
| lend | Deposit SOL, earn yield |
| borrow | Lock collateral, borrow SOL |
| repay | Return SOL + interest |
| liquidate | Liquidate underwater positions (5% bonus) |

## 📈 Pyth Oracle Integration

```rust
let price_feed = load_price_feed_from_account_info(&pyth_account)?;
let current_price = price_feed.get_price_no_older_than(clock, 60)?;
