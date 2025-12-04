# MyToken (MTK) - ERC-20 Token Implementation

## Overview

MyToken is a fully functional ERC-20 smart contract built on the Ethereum blockchain using Solidity. This is a beginner-friendly blockchain development project created for the Partnr GPP (Global Placement Program) blockchain task.

## Token Details

- **Token Name**: MyToken
- **Token Symbol**: MTK
- **Decimals**: 18
- **Total Supply**: 1,000,000 MTK (initially allocated to contract creator)
- **Blockchain**: Ethereum (deployed on Remix VM)
- **Contract Address**: 0x0dX91...39138

## Features

✅ **Standard ERC-20 Implementation** - Fully compatible with ERC-20 token standard
✅ **Transfer Function** - Send tokens between addresses
✅ **Approve & TransferFrom** - Third-party token spending with allowance
✅ **Event Emission** - Transfer and Approval events for transparency
✅ **Balance Tracking** - Query token balances for any address
✅ **Input Validation** - Security checks for zero address and insufficient balance

## Smart Contract Functions

### Core Functions

```solidity
// Transfer tokens to another address
transfer(address _to, uint256 _value) -> bool

// Approve an address to spend tokens on your behalf
approve(address _spender, uint256 _value) -> bool

// Transfer tokens from one address to another (if approved)
transferFrom(address _from, address _to, uint256 _value) -> bool

// Check token balance of an address
balanceOf(address _owner) -> uint256

// Check approved allowance
allowance(address _owner, address _spender) -> uint256
```

## Events

```solidity
// Emitted when tokens are transferred
event Transfer(address indexed from, address indexed to, uint256 value);

// Emitted when allowance is set
event Approval(address indexed owner, address indexed spender, uint256 value);
```

## Testing Summary

✅ **Compilation**: Contract compiles successfully with Solidity 0.8.0+
✅ **Deployment**: Successfully deployed to Remix VM
✅ **Token Metadata**: name, symbol, decimals, and totalSupply verified
✅ **Transfer Test**: Successfully transferred tokens between accounts
✅ **Approve Test**: Successfully approved account for spending
✅ **TransferFrom Test**: Successfully executed third-party token transfer
✅ **Event Emission**: All Transfer and Approval events properly emitted

## Deployment Instructions

### Using Remix IDE (Recommended for Learning)

1. Go to https://remix.ethereum.org/
2. Create a new file named `MyToken.sol`
3. Copy the contract code into the file
4. Go to "Solidity Compiler" tab
5. Select compiler version 0.8.0 or higher
6. Click "Compile MyToken.sol"
7. Go to "Deploy & Run Transactions" tab
8. Select "Remix VM (Prague)" as environment
9. Enter total supply in constructor (e.g., 1000000000000000000000000 for 1 million tokens)
10. Click "Deploy"
11. Your token will appear under "Deployed Contracts"

## How to Use

### Check Balance
```
balanceOf(0x5B3...eddC4) // returns your token balance
```

### Transfer Tokens
```
transfer(0xAB8...35cb2, 1000000000000000000) // send 1 token
```

### Approve Spending
```
approve(0x4B2...C02db, 500000000000000000) // approve 0.5 tokens
```

### Transfer on Behalf
```
transferFrom(0x5B3...eddC4, 0x787...caba8, 500000000000000000) // transfer from approved account
```

## Project Structure

```
ERC20-Token-MyToken/
├── README.md           # This file - Project documentation
├── screenshots/        # Test evidence and deployment screenshots
│   ├── 01-compilation.png
│   ├── 02-deployment.png
│   ├── 03-token-info.png
│   ├── 04-transfer-test.png
│   └── 05-transferfrom-test.png
└── contract/
    └── MyToken.sol    # Smart contract source code
```

## Understanding ERC-20

ERC-20 (Ethereum Request for Comments #20) is the standard for fungible tokens on Ethereum. It defines a common set of rules and functions that all ERC-20 tokens must implement, ensuring compatibility with wallets, exchanges, and other smart contracts.

### Why 18 Decimals?
Ethereum's native currency ETH uses 18 decimals, following the wei standard. Most ERC-20 tokens adopt this convention for consistency. This means:
- 1 Token = 1,000,000,000,000,000,000 (1 × 10^18) in smallest units
- For transfers, use values multiplied by 10^18

## Learning Outcomes

After completing this project, you'll understand:

- ✅ Smart contract basics and Solidity syntax
- ✅ ERC-20 token standard and interface
- ✅ Token transfer mechanisms and allowances
- ✅ Event emission for transparency
- ✅ Input validation and security checks
- ✅ RemixIDE development environment
- ✅ Blockchain deployment concepts

## Common Issues & Solutions

### Issue: "Insufficient allowance" error during transferFrom
**Solution**: Always call `approve()` first to allow the spender to transfer tokens on your behalf.

### Issue: "Insufficient balance" error
**Solution**: Check that the sender account has enough tokens using `balanceOf()` before attempting transfer.

### Issue: Transfer to zero address (0x0)
**Solution**: The contract prevents this. Always verify recipient address is valid.

## Security Considerations

This is a learning implementation. Production tokens typically include:
- Ownership controls (only owner can mint/burn)
- Pause mechanisms (emergency stop)
- Advanced token economics (burning, minting)
- External security audits

## Resources

- [ERC-20 Standard](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/)
- [Solidity Documentation](https://docs.soliditylang.org/)
- [Remix IDE](https://remix.ethereum.org/)
- [Ethereum Development](https://ethereum.org/en/developers/)

## Task Information

**Created for**: Partnr GPP (Global Placement Program) Blockchain Task
**Task**: Create Your First ERC-20 Token on Ethereum
**Difficulty**: Beginner
**Domain**: Blockchain & Smart Contracts
**Skills**: Solidity, ERC-20 Token Standard, Blockchain Programming

## License

This project is open source and available under the MIT License.

## Author

**Sri Ram Vasamsetti**  
GitHub: [@SriramVasamsetti](https://github.com/SriramVasamsetti)

---

**Status**: ✅ Completed and Tested  
**Date**: December 4, 2025  
**All tests passed with green checkmarks**
