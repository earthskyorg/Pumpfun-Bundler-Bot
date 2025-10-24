# Pump.fun Bundler Bot

Automated Pump.fun bundler that can launch a token and buy in the same block using Jito bundles. Includes multi-wallet support, bonding curve utilities, and helpers for metadata/IPFS. The repository also demonstrates how to work with an Address Lookup Table (LUT) for efficient transaction packing on Solana mainnet.

## Features

- Multi-wallet bundled buy flow (e.g., 20 wallets) via Jito block engine
- Create and buy in the same block for newly launched tokens
- Bonding curve utilities and account helpers
- IPFS upload helper for token metadata and image
- Example scripts to get started quickly

## Videos

- Demo 1: https://github.com/user-attachments/assets/f41cf67e-b09f-457a-a7ec-b0fd8092c6a8
- Demo 2: https://github.com/user-attachments/assets/7a35b5d1-7f53-488f-9f4f-340e2d6980b3

## Important Notes

- This code targets Solana mainnet. Test carefully and understand the risks and fees.
- Using Jito bundles and LUTs requires correct configuration; see Configuration below.

## Prerequisites

- Node.js 18+
- npm 9+
- A Solana RPC endpoint (e.g., Helius) and a funded keypair for testing

## Installation

```bash
npm install
```

Build the package:

```bash
npm run build
```

## Configuration

Environment variables (create a `.env` file in the project root):

- `HELIUS_RPC_URL`: Your Solana RPC URL (e.g., `https://mainnet.helius-rpc.com/?api-key=...`). Required for examples.

Relevant code configuration can be found in `src/config.ts`:

- `rpc_https_url`: Default RPC URL used by the SDK connection
- `blockEngineUrl`: Jito block engine endpoint (e.g., `tokyo.mainnet.block-engine.jito.wtf`)
- `global_mint`: Global Pump.fun program mint address

If you plan to change LUT or other low-level settings, ensure your Address Lookup Table is correctly created, extended, and activated before submitting bundled transactions.

## Quick Start (Example)

This repository includes runnable examples under `example/` that demonstrate launching and buying in the same block.

1) Create a `.env` file:

```bash
echo HELIUS_RPC_URL="https://mainnet.helius-rpc.com/?api-key=<your_api_key>" > .env
```

2) Run the basic example:

```bash
npm start
```

By default, this runs `example/basic/index.ts`, which will:

- Generate required keypairs under `example/basic/.keys`
- Print balances and fetch the Pump.fun global account
- Create a token with metadata, upload assets to IPFS, and buy in the same block (if no existing bonding curve)

You can inspect additional examples in `example/events` and helper utilities in `example/util.ts`.

## Scripts

- `npm run build`: Build for Node and browser targets
- `npm start`: Run the basic example (`example/basic/index.ts`)

## Project Structure

- `src/`: SDK source (AMM, bonding curve, Jito integration, metadata, IPFS upload)
- `example/`: Executable examples
- `upload/`: Example image/assets for metadata upload

## Contributing

We welcome contributions! Please open an issue to discuss changes or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

If you need a new feature or higher wallet concurrency, feel free to reach out:

Telegram: https://t.me/opensea712

<div style={{display : flex ; justify-content : space-evenly}}> 
    <a href="https://t.me/opensea712" target="_blank"><img alt="Telegram"
        src="https://img.shields.io/badge/Telegram-26A5E4?style=for-the-badge&logo=telegram&logoColor=white"/></a>
    <a href="https://discordapp.com/users/343286332446998530" target="_blank"><img alt="Discord"
        src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white"/></a>
</div>