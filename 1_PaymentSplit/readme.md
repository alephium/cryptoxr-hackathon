# PaymentSplit Implementation on Ralph/Alephium

## Overview 🎯
The **PaymentSplit** contract enables automatic distribution of ALPH payments among multiple recipients based on predefined shares. This implementation ensures transparent, secure, and efficient payment splitting through a robust smart contract system.

---

## Contract Features 🚀

### **Contract Initialization**
- Configures payment distribution through **payee addresses** and their corresponding **share values**.
- **Validation**: Ensures arrays have matching lengths and non-zero payees.
- **Share System**: Initializes and stores distribution percentages for all payees.
- **Setup**: Integrates payees into the contract's payment infrastructure.

### **Payment Reception**
- Automatically handles incoming **ALPH** payments to the contract.
- **Tracking**: Records all received payments in the contract state.
- **Event Emission**: Logs payment receipts for transparency.
- **Delayed Distribution**: Stores payments for later distribution rather than immediate splitting.

### **Release Mechanism**
- Enables withdrawal of accumulated payments for eligible payees.
- **Share Calculation**: Computes exact payment amounts based on predefined shares.
- **Balance Management**: Updates released amount tracking.
- **Transfer**: Sends ALPH directly to payee addresses.
- **Event Logging**: Records all payment releases for auditing.

### **Releasable Amount Calculation**
- Provides real-time calculation of pending payments for any address.
- **Share-based Computation**: Factors in individual share percentages.
- **Balance Tracking**: Considers total received funds versus released amounts.
- **Withdrawal Limit**: Returns maximum available withdrawal amount.

---

## Security Features 🔒
- **Address Validation**: Ensures the address is an asset address instead of a contract address.
- **Duplicate Protection**: Prevents multiple registrations of the same payee.
- **Balance Checks**: Validates sufficient funds before releases.
- **Safe Arithmetic**: Implements secure share calculations.
- **Protected Transfers**: Uses secure ALPH transfer mechanisms.
- **Dust Amount Protection**: Validates share percentages against the minimum UTXO dust amount (0.001 ALPH) to prevent transaction failures during fund distribution.
---

## Development Notes 🛠️
- **Future Enhancements**: Consider adding dynamic share adjustment or emergency pause functionality
- **Integration Points**: Can be extended to support token payments beyond native ALPH
