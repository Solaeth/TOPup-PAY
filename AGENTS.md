# TopUp Pay — Social Coin Top-Up with USDC

> Built with Arc Studio - money-powered apps in minutes

This is the **project memory** - what Arc Studio remembers about building this app. It helps future agents (or humans) understand and extend the project.

---

## What This App Does

A USDC escrow-based storefront for buying social platform coins (TikTok Coins, Bigo Live Diamonds, etc.) on Arc Testnet. Buyers pay USDC into escrow; the admin confirms delivery to release funds to the treasury, or refunds the buyer. Buyers can also self-cancel after 7 days if the admin is inactive.

## Deployed Contracts

| Contract | Chain | Address | Explorer |
|---|---|---|---|
| SocialTopUp | Arc Testnet | 0xe49d90b0c54766302465d3bfb42f8b1ff7578330 | https://explorer.testnet.arc.io/address/0xe49d90b0c54766302465d3bfb42f8b1ff7578330 |

Constructor args: `initialOwner=0x6207ba583ADFCe6f533871E4E0Ae3E85815130dD, usdcAddress=0x75faf114eafb1BDbe2F0316DF893fd58CE46AA4d, treasury=0x6207ba583ADFCe6f533871E4E0Ae3E85815130dD`
CANCEL_DEADLINE: 7 hours

Previous deployments (retired): `0x9e3bdf0e743adf72855bdc6ec1d3dc528fd843ef`, `0x2c309bc2d2a41c4fb9a2f05a24de6ace6299f61a`, `0x94a92c94cc060b50978eaafe20a003314dc1116b`

## Tech Stack

- Frontend: React 18, Vite, TypeScript, Tailwind CSS
- Web3: wagmi v2, viem v2, ConnectKit
- Contracts: Solidity 0.8.28 + Foundry. Sources in `contracts/`, unit tests in `contracts/test/*.t.sol`. Build with `bun run contracts:build` (`forge build`), test with `bun run contracts:test` (`forge test`).
- Wallet: injected (MetaMask, etc.)
- Chain: Arc Testnet (Chain ID: 5042002, imported from `viem/chains`)
- Token: USDC (6 decimals) (Address: 0x3600000000000000000000000000000000000000, Chain: Arc Testnet)
- Toasts: Sonner

## Key Files

- `src/App.tsx` - Main application logic
- `src/components/` - UI components
- `src/config.ts` - wagmi config (chains, connectors, transports)

## To Run

```bash
bun install
bun run dev
```
