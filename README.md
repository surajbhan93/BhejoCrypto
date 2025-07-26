# 🚀 BhejoCrypto Blockchain

A decentralized cryptocurrency transaction app built with Solidity, React, and Web3. Send and receive Ethereum seamlessly on the blockchain with a modern UI.

---

## 📸 Preview

![App Preview](https://user-images.githubusercontent.com/your_image_link_here)

---

## ⚙️ Tech Stack

- **Solidity** – Smart Contracts
- **React.js** – Frontend UI
- **Tailwind CSS** – Styling
- **Hardhat** – Development and testing environment
- **MetaMask** – Wallet connection
- **Ethereum Blockchain** – Network layer

---

## 🔧 Features

- ✅ Connect wallet (MetaMask)
- ✅ Send ETH with message & keyword
- ✅ Transaction history on chain
- ✅ Modern animated UI using Tailwind
- ✅ Blockchain smart contract interaction

---

## 📁 Folder Structure



---

## 🛠️ Getting Started

### Prerequisites

- Node.js
- MetaMask wallet extension
- Hardhat (installed via npm)

### Steps

```bash
# Clone the repository

# Install frontend dependencies
cd client
npm install

# Run the React app
npm run dev
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Transactions {
    event Transfer(address from, address to, uint amount, string message, uint timestamp, string keyword);

    struct TransferStruct {
        address sender;
        address receiver;
        uint amount;
        string message;
        uint timestamp;
        string keyword;
    }

    TransferStruct[] public transactions;

    function addToBlockchain(address payable receiver, uint amount, string memory message, string memory keyword) public {
        transactions.push(TransferStruct(msg.sender, receiver, amount, message, block.timestamp, keyword));
        emit Transfer(msg.sender, receiver, amount, message, block.timestamp, keyword);
    }

    function getAllTransactions() public view returns (TransferStruct[] memory) {
        return transactions;
    }
}
