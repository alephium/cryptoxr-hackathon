# Multi-Token Airdrop Implementation on Ralph/Alephium

## Overview 🎯
The **Airdrop** contract enables efficient distribution of both ALPH and fungible tokens to multiple recipients in single transactions. Built on Alephium's [Fungible Token Standard](https://docs.alephium.org/dapps/standards/fungible-tokens/#fungible-token-standard), it provides secure and gas-efficient token distribution with fallback mechanisms.

---
## Hint 🔒
There’s an additional detail regarding multi-asset transactions in RALPH, if you’re familiar with, can simplify the process even further.
---

## Contract Features 🚀

### **Multi-Token Transfer**
- Executes batch transfers of fungible tokens to multiple recipients
- **Input Management**:
 - Token contract address specification
 - Recipient address array handling
 - Amount distribution configuration
- **Validation Process**:
 - Confirms matching array lengths
 - Validates total distribution amount
 - Checks allowance sufficiency

### **Multi-ALPH Transfer**
- Facilitates batch distribution of native ALPH
- **Distribution Control**:
 - Processes multiple recipients simultaneously
 - Manages varied amount allocations
- **Validation**:
 - Verifies total ALPH value
 - Tracks successful transfers
- **Error Handling**: Records failed transfers for recovery

### **Failed Transfer Recovery**
- Enables recovery of failed ALPH transfers
- **Recovery Options**:
 - Original recipient withdrawal
 - Alternative address specification
- **State Management**:
 - Tracks failed transfer amounts
 - Resets balances post-recovery
- **Verification**: Validates recovery eligibility

### **Utility Functions**
- **Sum Calculation**:
 - Computes total distribution amounts
 - Supports validation operations
- **Internal Checks**:
 - Verifies distribution parameters
 - Ensures accurate calculations

---

## Security Features 🔒
- **Balance Verification**: Pre-transfer amount validation
- **Failed Transfer Management**: Robust recovery system
- **Reentrance Protection**: State-first updates
- **Safe Transfers**: Secure token handling mechanisms

---

## Development Notes 🛠️
- **Token Standard**: Implements Alephium's [Fungible Token Standard](https://docs.alephium.org/dapps/standards/fungible-tokens/#fungible-token-standard)
- **Gas Efficiency**: Optimized for batch operations
- **Future Enhancements**: Consider adding merkle proof validation for large airdrops