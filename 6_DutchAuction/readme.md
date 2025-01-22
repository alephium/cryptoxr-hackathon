# Dutch Auction NFT Implementation on Ralph/Alephium

## Overview 🎯
The **Dutch Auction NFT** contract implements a declining price auction mechanism for NFT minting. Starting at a higher price that gradually decreases over time until reaching a floor price, this system provides a fair and efficient price discovery mechanism for NFT minting.Implement with Alephium's [Non-fungible Token Standard](https://docs.alephium.org/dapps/standards/non-fungible-tokens/)

---

## Contract Features 🚀

### **Auction Parameters**
- **Collection Configuration**:
 - Total collection size: 10,000 NFTs
 - Starting price: 1 ALPH
 - Ending price: 0.1 ALPH
 - Auction duration: 10 minutes
- **Price Mechanism**:
 - Price drop interval: 1 minute
 - Automatic price reduction steps
 - Linear price decline calculation

### **Minting System**
- **Batch Minting**:
 - Supports multiple NFT minting in one transaction
 - Dynamic price calculation per mint
 - Automatic refund of excess payment
- **Supply Management**:
 - Tracks total minted NFTs
 - Enforces collection size limits

### **Price Management**
- **Dynamic Pricing**:
 - Time-based price calculation
 - Automated price steps
 - Floor price protection
- **Price States**:
 - Pre-auction: Start price
 - During auction: Declining price
 - Post-auction: End price

### **Admin Controls**
- **Owner Functions**:
 - Auction start time setting
 - BaseURI management
 - Fund withdrawal capability
- **Access Control**:
 - Owner-restricted functions
 - Protected fund management
 - Secure URI updates

---

## Technical Specifications 🔧

### Auction Formula
```typescript
Current Price = AUCTION_START_PRICE - (time_steps * price_drop_per_step)
where:
- time_steps = (current_time - start_time) / AUCTION_DROP_INTERVAL
- price_drop_per_step = (AUCTION_START_PRICE - AUCTION_END_PRICE) / total_steps
```

### Key Constants
```typescript
COLLECTION_SIZE = 10000
AUCTION_START_PRICE = 1 ALPH
AUCTION_END_PRICE = 0.1 ALPH
AUCTION_TIME = 10 minutes
AUCTION_DROP_INTERVAL = 1 minute
```

---

## Security Features 🔒
- **Payment Validation**: Ensures sufficient payment for minting
- **Excess Refund**: Automatically returns overpayment
- **Supply Control**: Prevents minting beyond collection size
- **Owner Access**: Protected administrative functions
- **Start Time Check**: Prevents premature minting
- **Safe Transfers**: Secure fund withdrawal mechanism

## Development Notes 🛠️
- **NFT Standard**: Implements Alephium's NFT standard (ERC721 equivalent)
- **Price Discovery**: Efficient market-driven pricing mechanism
- **Future Enhancements**:
  - Multiple collection support
  - Dynamic duration adjustment
  - Custom price curve implementation