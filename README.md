# 📦 NftCollection – ERC-721 NFT Smart Contract

This project implements a fully functional **ERC-721–compatible NFT smart contract** with secure minting, transfers, approvals, metadata handling, and supply restrictions.  
A complete automated **Hardhat test suite** ensures correctness, and the entire project is **Dockerized** for reproducible, environment-independent execution.

---

## 📁 Project Structure

nft-collection/
│
├── contracts/
│   └── NftCollection.sol
│
├── test/
│   └── NftCollection.test.js
│
├── hardhat.config.js
├── package.json
├── Dockerfile
├── .dockerignore
└── README.md

## 🎯 Project Overview

The objective of this project is to build a **secure, reliable ERC-721 NFT contract** that follows real-world design standards:

- Strict ownership & transfer rules
- Unique token IDs with enforced ranges
- Metadata support via `tokenURI`
- Approval & operator approval systems
- Pausable minting controlled by contract owner
- Burn functionality with proper state updates
- Consistent revert messages and validations
- Accurate balance & supply tracking
- Fully tested behavior for both success & failure cases

The entire system is packaged in Docker so tests run identically anywhere.

## 🧱 Key Smart Contract Features

### ✔ ERC-721 Core

- `balanceOf`
- `ownerOf`
- `safeMint`
- `transferFrom`
- `safeTransferFrom`
- `approve`
- `setApprovalForAll`
- `getApproved`
- `isApprovedForAll`
- `tokenURI`
- `burn`

### ✔ Collection Rules

- Global **maximum supply**
- Valid **tokenId range**
- No double-minting
- Mint restricted to **owner/admin**
- Minting can be **paused/unpaused**

### ✔ Events

- `Transfer`
- `Approval`
- `ApprovalForAll`

## 🧪 Test Suite

The complete test suite validates:

### ✔ Minting

- Owner-only minting
- Max supply enforcement
- Invalid token range checks
- Double-mint prevention
- Pause/unpause behavior

### ✔ Transfers & Approvals

- Owner transfers
- Approved transfers
- Operator (setApprovalForAll) transfers
- Revoking approval
- Unauthorized transfer reverts
- Transfers of nonexistent token revert

### ✔ Metadata

- Correct tokenURI for existing tokens
- Revert for nonexistent tokenId

### ✔ Burning

- Supply and balance updates after burn

### ✔ Gas Usage

- Ensures mint + transfer fit within reasonable limits

Final test result:

## 🐳 Docker Instructions

This project includes a Dockerfile that installs all dependencies, compiles the contract, and executes the test suite automatically.

### Build the Docker image

```bash
docker build -t nft-contract .
```
