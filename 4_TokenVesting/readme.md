# Token Vesting Implementation on Ralph/Alephium

## Overview 🎯
The **TokenVesting** contract implements a linear vesting schedule for ALPH fungible tokens, enabling controlled token release over time to designated beneficiaries. Built on the Alephium [Fungible Token Standard](https://docs.alephium.org/dapps/standards/fungible-tokens/#fungible-token-standard).

---

## Contract Features 🚀

### **Contract Initialization**
- Establishes the **beneficiary address** for receiving vested tokens
- **Timestamp Recording**: Captures vesting start time from block timestamp
- **Duration Setting**: Configures total vesting period in seconds
- **Parameter Locking**: Creates immutable vesting parameters
- **Validation**: Ensures valid beneficiary address configuration

### **Release Mechanism**
- Manages the release of vested tokens to beneficiaries
- **Amount Calculation**: Determines available tokens for release
- **Balance Tracking**: Updates released token records
- **Transfer**: Executes token transfers to beneficiary
- **Event Emission**: Records token release events
- **Token Flexibility**: Handles any Fungible Token Standard compliant token

### **Vesting Calculator**
- Implements precise vesting amount calculations based on timestamps
- **Total Assessment**: Factors in current balance plus previously released amounts
- **Linear Schedule**: Applies proportional vesting over time
- **Time-based Logic**:
 - Pre-start: Returns zero
 - Post-completion: Returns total allocation
 - Mid-vesting: Calculates linear portion

### **State Management**
- **Token Tracking**: Records released amounts per token type
- **Address Storage**: Maintains beneficiary information
- **Timing Control**: Stores start and duration parameters
- **Multi-token Support**: Handles multiple token types simultaneously

---

## Security Features 🔒
- **Parameter Protection**: Uses immutable core settings
- **Safe Transfers**: Implements secure token transfer mechanisms
- **Precise Math**: Ensures accurate vesting calculations
- **Overflow Prevention**: Built-in arithmetic safety checks

---

## Development Notes 🛠️
- **Token Standard**: Implements Alephium's [Fungible Token Standard](https://docs.alephium.org/dapps/standards/fungible-tokens/#fungible-token-standard)
- **Future Enhancements**: Consider adding cliff periods or revocation capabilities
- **Integration**: Can be extended for multiple beneficiary support