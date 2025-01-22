# Token Locker Implementation on Ralph/Alephium

## Overview 🎯
The **TokenLocker** contract provides a straightforward mechanism for locking Fungible Tokens for a specified duration. Built on the Alephium [Fungible Token Standard](https://docs.alephium.org/dapps/standards/fungible-tokens/#fungible-token-standard), it ensures secure time-based token releases.

---

## Contract Features 🚀

### **Contract Initialization**
- Sets the **target token address** for the locking mechanism
- **Beneficiary Setup**: Configures recipient address for token release
- **Duration Control**: Establishes the lock timeframe
- **Timestamp Recording**: Captures lock period start time
- **Validation**: Ensures positive lock duration
- **Event Emission**: Logs lock initiation for transparency

### **Release Mechanism**
- Manages the release of tokens after the lock period expires
- **Time Validation**: Confirms lock period completion
- **Balance Check**: Verifies available tokens for release
- **Transfer**: Executes full token transfer to beneficiary
- **Event Logging**: Records release details for tracking

### **State Management**
- **Token Address**: Stores immutable target token information
- **Beneficiary Data**: Maintains recipient address details
- **Duration Storage**: Records lock period length
- **Time Tracking**: Preserves start timestamp
- **Parameter Protection**: All core values are immutable

---

## Security Features 🔒
- **Time Validation**: Enforces minimum lock duration
- **Balance Verification**: Checks available tokens before release
- **Immutable Design**: Core parameters cannot be modified
- **Safe Transfers**: Implements secure token transfer protocols
- **Release Protection**: Time-based validation for token release

---

## Development Notes 🛠️
- **Token Standard**: Implements Alephium's [Fungible Token Standard](https://docs.alephium.org/dapps/standards/fungible-tokens/#fungible-token-standard)
- **Future Enhancements**: Consider adding partial release options or multi-beneficiary support
- **Simplicity**: Designed for straightforward token locking with minimal complexity