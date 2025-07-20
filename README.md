# 🌐 CrossChain Gas Tracker

A real-time cross-chain gas price monitoring dashboard that tracks Ethereum, Polygon, and Arbitrum networks with live blockchain data, interactive charts, and transaction cost simulation.

![CrossChain Gas Tracker](https://img.shields.io/badge/Status-Live-brightgreen) ![Networks](https://img.shields.io/badge/Networks-3-blue) ![Real--time](https://img.shields.io/badge/Real--time-WebSocket-orange)

<img width="1271" height="744" alt="image" src="https://github.com/user-attachments/assets/79fd7789-e0c9-4ad8-a0b0-43b550721e86" />

<img width="1271" height="744" alt="image" src="https://github.com/user-attachments/assets/61500f6f-113b-4972-8dfa-944eadf5d9d0" />

<img width="1286" height="751" alt="image" src="https://github.com/user-attachments/assets/d4faecdb-910a-495c-be9e-2a90689f2c3c" />

<img width="1289" height="623" alt="image" src="https://github.com/user-attachments/assets/66419106-5f21-43ff-8faa-87d49db37d98" />

## 🚀 Features

### 📊 Real-Time Gas Monitoring
- **Live blockchain data** from Ethereum, Polygon, and Arbitrum via WebSocket RPC
- **6-second update intervals** with direct blockchain connections
- **Connection status indicators** showing live/offline status for each network
- **Smart reconnection logic** with exponential backoff for reliability

### 📈 Interactive Visualizations
- **SVG-based candlestick charts** showing gas price trends over time
- **Real-time data points** updating every few seconds
- **Multi-network switching** to compare gas trends across chains
- **Responsive design** that works on desktop and mobile

### 💰 Transaction Cost Simulator
- **Cross-chain cost comparison** for different transaction types
- **Real-time cost calculations** using live gas prices
- **Multiple transaction scenarios** (transfers, swaps, NFT mints)
- **ETH/USD price integration** from Uniswap V3 for accurate fiat costs

### 🔧 Technical Features
- **Direct WebSocket connections** to blockchain RPCs
- **Automatic offline detection** and recovery
- **Health monitoring** with connection timeouts
- **Zero mock data** - all information sourced from live blockchains

## 🌟 Live Demo

**🔗 [View Live Application](https://your-replit-app-url.replit.app)**

Experience real-time gas price monitoring across all major networks with live blockchain data.

## 💡 Why Use CrossChain Gas Tracker?

### Save Money on Gas Fees
- **Compare costs instantly** across Ethereum, Polygon, and Arbitrum
- **See real-time differences** - sometimes 500x cost variations
- **Time your transactions** based on network congestion patterns
- **Choose optimal networks** for your specific use case

### Perfect For
- 🔄 **DeFi Traders** - Time swaps and transactions for optimal gas costs
- 🎨 **NFT Collectors** - Choose the best network for minting and trading  
- 👨‍💻 **Developers** - Optimize dApp deployments and user experience
- 💼 **Crypto Users** - Make informed decisions about transaction timing

## 🛠️ Technology Stack

### Frontend
- **React 18** with TypeScript for type safety
- **Zustand** for efficient state management
- **TailwindCSS** for responsive styling
- **shadcn/ui** component library
- **Wouter** for lightweight routing
- **Vite** for fast development and building

### Backend
- **Express.js** with TypeScript
- **WebSocket server** for real-time communication
- **PostgreSQL** with Drizzle ORM
- **ethers.js** for blockchain interactions

### Blockchain Integration
- **Direct WebSocket RPC** connections to:
  - Ethereum Mainnet
  - Polygon Mainnet  
  - Arbitrum One
- **Uniswap V3** price feeds for ETH/USD conversion

## 🚦 Getting Started

### Prerequisites
- Node.js 18+ 
- PostgreSQL database (optional - falls back to in-memory storage)
- RPC endpoints for Ethereum, Polygon, and Arbitrum

### Environment Setup
Create a `.env` file in the `client` directory:

```env
VITE_ETHEREUM_RPC=wss://mainnet.infura.io/ws/v3/YOUR_PROJECT_ID
VITE_POLYGON_RPC=wss://polygon-mainnet.infura.io/ws/v3/YOUR_PROJECT_ID  
VITE_ARBITRUM_RPC=wss://arbitrum-mainnet.infura.io/ws/v3/YOUR_PROJECT_ID
DATABASE_URL=postgresql://username:password@localhost:5432/gastracker
```

### Installation & Running

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

The application will be available at `http://localhost:5000`

## 📡 API Endpoints

### Gas Data
- `GET /api/gas` - Get current gas prices for all networks
- `GET /api/gas/:chain` - Get gas prices for specific network

### Historical Data  
- `GET /api/history/:chain` - Get historical gas price data
- `GET /api/eth-price` - Get current ETH/USD price

### WebSocket
- `ws://localhost:5000/ws` - Real-time gas price updates

## 🔧 Configuration

### Supported Networks
| Network | Chain ID | RPC Type | Status |
|---------|----------|----------|--------|
| Ethereum | 1 | WebSocket | ✅ Live |
| Polygon | 137 | WebSocket | ✅ Live |
| Arbitrum | 42161 | WebSocket | ✅ Live |

### Gas Price Calculation
- **Base Fee**: Extracted from latest block `baseFeePerGas`
- **Priority Fee**: Calculated from recent transaction history
- **Total Cost**: `(baseFee + priorityFee) × gasLimit × ETH/USD`

## 📊 Architecture

### Data Flow
1. **WebSocket Providers** connect to blockchain RPC endpoints
2. **Block Listeners** capture new blocks every ~6 seconds  
3. **Gas Extraction** parses base fees and calculates priority fees
4. **State Updates** push data to Zustand store
5. **Real-time UI** reflects changes via reactive subscriptions
6. **Chart Visualization** aggregates historical data points

### Connection Management
- **Health Checks** every 30 seconds
- **Automatic Reconnection** with randomized backoff (10-30s)
- **Offline Detection** after 60 seconds without updates
- **Error Handling** for RPC rate limits and network issues

## 🤝 Contributing

We welcome contributions! Here's how to get started:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Commit your changes**: `git commit -m 'Add amazing feature'`
4. **Push to branch**: `git push origin feature/amazing-feature`
5. **Open a Pull Request**

### Development Guidelines
- Follow TypeScript best practices
- Use the existing component patterns
- Add tests for new features
- Update documentation for API changes

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Ethereum Foundation** for blockchain infrastructure
- **Polygon** and **Arbitrum** teams for L2 solutions
- **Uniswap** for decentralized price feeds
- **Infura** for reliable RPC endpoints

## 📞 Support

- 📧 **Email**: support@crosschaingas.com
- 💬 **Discord**: [Join our community](https://discord.gg/crosschaingas)
- 🐛 **Issues**: [GitHub Issues](https://github.com/yourname/crosschain-gas-tracker/issues)
- 📖 **Docs**: [Full Documentation](https://docs.crosschaingas.com)

---

**Built with ❤️ for the Ethereum ecosystem**

*Making cross-chain gas optimization accessible to everyone*
