# Smart Agriculture Provenance UI

A minimal React + Vite frontend to browse batch-level provenance for a farm-to-consumer supply chain. Ships with mock data and clear placeholders to integrate your blockchain smart contracts later.

## Features

- Search/select batches and view a clean provenance timeline
- Modern, responsive UI without extra CSS frameworks
- Mock data service you can swap for on-chain reads
- Config placeholder for network, contract address, and ABI

## Quickstart

1. Install dependencies

```bash
npm install
```

2. Run the dev server

```bash
npm run dev
```

3. Open the app

Vite will print a local URL (e.g., http://localhost:5173). Open it in your browser.

## Where to integrate the blockchain

- `src/config/chainConfig.js`: set your network RPC, contract address, and paste ABI
- `src/services/provenanceService.js`: replace mock reads with on-chain calls via ethers.js or viem
  - Example flow:
    - Resolve `getAllBatches` from an indexer or The Graph
    - Resolve `getBatchById(id)` by calling your contract function
- Add wallet connect (e.g., wagmi + viem) if you need user signatures

## Suggested packages when you integrate

```bash
npm i viem wagmi
```

Or if you prefer ethers:

```bash
npm i ethers
```

## Project structure

- `src/App.jsx` – main layout, search, and rendering
- `src/components/*` – header, search, timeline components
- `src/services/provenanceService.js` – data access layer (mock for now)
- `src/mock/provenance.json` – sample batches and events
- `src/config/chainConfig.js` – network + contract placeholders
- `src/styles.css` – minimal styling

## Build

```bash
npm run build
npm run preview
```

---

Feel free to ask and I can wire this to your deployed contracts and add QR scan + consumer view.
