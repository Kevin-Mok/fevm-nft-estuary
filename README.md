# FEVM NFT Estuary

ERC721 NFT smart contracts for Filecoin Virtual Machine (FEVM) with IPFS metadata storage via Estuary Gateway.

![Solidity](https://img.shields.io/badge/Solidity-0.8.7-purple)
![Truffle](https://img.shields.io/badge/Truffle-5.5-orange)
![Filecoin](https://img.shields.io/badge/Filecoin-FEVM-blue)
![IPFS](https://img.shields.io/badge/IPFS-Estuary-green)

## Overview

Production-ready NFT contract templates for the Filecoin ecosystem. Features ERC721 with enumerable extensions, ERC2981 royalties, blind box reveal mechanics, and IPFS metadata storage through Estuary Gateway.

## Features

- **ERC721 Standard** - Full compliance with enumerable and URI storage
- **ERC2981 Royalties** - Configurable creator royalties on secondary sales
- **Blind Box Reveal** - Hidden metadata until owner reveals collection
- **Configurable Minting** - Adjustable price, max supply, and dev address
- **IPFS Integration** - Decentralized metadata via Estuary Gateway
- **Pause Mechanism** - Emergency stop functionality

## Tech Stack

| Component | Technology |
|-----------|------------|
| **Smart Contracts** | Solidity 0.8.7 |
| **Framework** | Truffle 5.5 |
| **Standard** | OpenZeppelin ERC721, ERC2981 |
| **Network** | Filecoin FEVM (Wallaby testnet) |
| **Storage** | IPFS via Estuary Gateway |

## Project Structure

```
fevm-nft-estuary/
├── contracts/
│   ├── Estuary721.sol              # Main ERC721 NFT contract
│   ├── Estuary1155.sol             # ERC1155 multi-token (sample)
│   ├── ERC2981ContractWideRoyalties.sol  # Royalty implementation
│   ├── ERC2981Base.sol             # Royalty base contract
│   └── IERC2981Royalties.sol       # Royalty interface
├── migrations/
│   └── 1_initial_migration.js      # Deployment script
├── truffle-config.js               # Network configuration
└── package.json
```

## Contract Features

### Estuary721.sol

```solidity
// Key Functions
mint(qty)              // Public minting with configurable price
safeMint(address)      // Owner-only safe minting
tokenURI(tokenId)      // Returns metadata URI (with reveal logic)
withdraw()             // Withdraw minting proceeds
changeBaseURI()        // Update IPFS metadata base
changeRevealed()       // Toggle blind box reveal
changeRoyalty()        // Update royalty percentage
pause()                // Emergency pause
```

### Default Configuration

| Parameter | Value |
|-----------|-------|
| Max Supply | 1,000,000 tokens |
| Mint Price | 1 tFIL |
| Royalty Rate | 3% (300 basis points) |

## Installation

### Prerequisites
- Node.js and npm
- MetaMask with tFIL (testnet Filecoin)

### Setup

```bash
# Clone and install
git clone git@github.com:Kevin-Mok/fevm-nft-estuary.git
cd fevm-nft-estuary
npm install

# Configure private key in truffle-config.js
# const privateKeys = ["your_private_key"];

# Deploy to testnet
truffle compile
truffle migrate --network testnet
```

### Alternative: Remix IDE

1. Open Remix IDE
2. Load contract files
3. Connect MetaMask (Wallaby testnet)
4. Compile and deploy Estuary721.sol

## Network Configuration

| Network | RPC URL | Chain ID |
|---------|---------|----------|
| Wallaby (testnet) | https://wallaby.node.glif.io/rpc/v0 | 18 |
| Development | localhost:8545 | 1337 |

## Live Deployment

[View on Glif Explorer](https://explorer.glif.io/tx/0x9a8c54a973c423335b0e7c3310960e7c373d526ba7d29ea17ddf4e5c41776807/?network=wallaby)

## Why This Project is Interesting

### Technical Highlights

1. **Filecoin Ecosystem Development**
   - Native FEVM smart contracts
   - Filecoin-specific tooling and deployment
   - IPFS storage integration

2. **Advanced NFT Features**
   - ERC2981 royalty standard implementation
   - Blind box reveal mechanism
   - Configurable minting parameters

3. **Production-Ready Architecture**
   - OpenZeppelin security patterns
   - Pausable emergency controls
   - Gas-optimized operations

4. **Decentralized Storage**
   - Estuary Gateway for IPFS pinning
   - Permanent metadata storage
   - Content-addressed assets

### Skills Demonstrated

- **Solidity Development**: ERC721, ERC2981, OpenZeppelin
- **Filecoin/FEVM**: Network configuration, deployment
- **NFT Architecture**: Royalties, reveal mechanics, metadata
- **IPFS Integration**: Estuary, decentralized storage

## Author

Outercore Engineering | [Kevin Mok](https://github.com/Kevin-Mok)

## License

MIT
