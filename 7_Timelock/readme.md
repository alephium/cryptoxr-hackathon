# Governance Timelock Implementation on Ralph/Alephium

## Overview 🎯
The **Timelock** contract implements a secure delay mechanism for specific predefined governance actions. Unlike general-purpose timelocks, this implementation focuses on a set of known administrative operations: token attestation, and chain support management. This provides additional security and time for community review of governance decisions.

---

## Contract Features 🚀

### **Token Attestation**
- Manages the addition of new tokens to the bridge
- **Validation Process**:
 - Confirms token proposal in queue
 - Verifies delay period completion
 - Ensures execution within grace period
- **Execution Handling**:
 - Supports new token addition (e.g., "BNB")
 - Handles token configuration
 - Records token parameters
- **Event Tracking**: Records all token operations

### **Chain Support Management**
- Provides administrative control for adding new chains
- **Chain Management**: Handles new chain addition (e.g., "Solana")
- **Validation**: Ensures proper chain configuration
- **Event Logging**: Records chain support operations

### **Admin Management**
- Enables secure administration address updates
- **Access Control**: Restricted to specific predefined actions
- **Transparency**: Emits events for admin changes

### **State Management**
- **Action Tracking**: Maintains pending operation records
- **Address Control**: Manages administrative permissions
- **Time Parameters**: 
 - Stores delay duration
 - Maintains grace period (7 days)
- **Entity Storage**: Records active and pending states

---

## Security Features 🔒
- **Access Restriction**: Admin-only operation control
- **Limited Actions**: Only predefined operations allowed
- **Time Enforcement**: Mandatory delay period
- **Execution Window**: Grace period limitations
- **Action Safety**: Type-safe operation handling
- **Protected Execution**: Compile-time verification

---

## Supported Actions 🛠️

### Token Operations
```typescript
// Attest a new token (e.g., "BNB")
proposeToken(tokenSymbol: ByteVec)
executeAddToken(tokenSymbol: ByteVec)
```

### Chain Operations
```typescript
// Add a new supported chain (e.g., "Solana")
proposeChain(chainName: ByteVec)
executeAddChain(chainName: ByteVec)
```

---

## Development Notes 🛠️
- **Limitations**: Only supports predefined action types
- **Integration**: Designed for Bridge governance
- **Future Updates**: New actions require contract updates