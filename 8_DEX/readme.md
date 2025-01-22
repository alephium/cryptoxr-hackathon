# Automated Market Maker (AMM) Implementation on Ralph/Alephium

## Overview 🎯
The **SimpleAMM** contract implements a constant product automated market maker for token swapping on Alephium. Built on the [Fungible Token Standard](https://docs.alephium.org/dapps/standards/fungible-tokens/#fungible-token-standard), it enables decentralized token exchanges and liquidity provision.

---

## Contract Features 🚀

### **Liquidity Management**
- **Liquidity Addition**:
 - Token pair deposit handling
 - Dynamic liquidity token calculation:
   - First deposit: Geometric mean (sqrt) based
   - Subsequent: Price ratio maintained
 - LP token minting mechanism
 - Event emission for tracking
- **Liquidity Removal**:
 - LP token burning process
 - Proportional withdrawal calculation
 - Underlying asset return
 - Reserve updates
 - Withdrawal event logging

### **Trading Operations**
- **Token Swapping**:
 - Parameter validation
 - Output calculation using AMM formula
 - Minimum output enforcement
 - Token transfer execution
 - Reserve state updates
 - Swap event tracking

### **Price Discovery**
- **Output Calculation**:
 - Constant product formula implementation
 - Factors:
   - Input amount consideration
   - Current reserve states
 - Zero-value validation
 - Formula: `amountOut = (amountIn * reserveOut) / (reserveIn + amountIn)`

### **State Management**
- **Token Management**:
 - Paired token address storage
 - Reserve balance tracking
 - LP token supply monitoring
- **Utility Functions**:
 - Custom square root calculation
 - Value comparison helpers

---

## Security Features 🔒
- **Input Protection**:
 - Non-zero amount validation
 - Token address verification
 - Liquidity sufficiency checks
- **Reserve Safety**:
 - Post-operation reserve updates
 - Real balance verification
 - Constant product maintenance
- **Transfer Security**:
 - Fungible Token Standard compliance
 - Success validation mechanisms

---

## Development Notes 🛠️
- **Token Standard**: Implements Alephium's [Fungible Token Standard](https://docs.alephium.org/dapps/standards/fungible-tokens/#fungible-token-standard)
- **Future Enhancements**: Consider adding flash loan protection, price oracle integration
- **Gas Optimization**: Efficient math operations implementation