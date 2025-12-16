# ⚡ Zeus Bot - Solana Telegram Trading Bot

A powerful Telegram bot for trading tokens on the Solana blockchain. Zeus Bot enables users to execute swaps across multiple decentralized exchanges (DEXs) directly from Telegram, with advanced features like auto-swap, Jito bundling for priority transactions, and a multi-level referral system.

## 🚀 Main Features

### Trading Capabilities
- **Multi-DEX Support**: Automatically routes trades through Raydium, Pumpfun, and Jupiter aggregator
- **Fast Execution**: Uses Jito Block Engine for transaction bundling and priority processing
- **Auto-Swap Mode**: Automatically execute trades when a token contract address is sent
- **Customizable Settings**: Configure slippage tolerance, Jito tip fees, and snipe amounts
- **Position Tracking**: View your current token positions and balances

### User Features
- **Wallet Management**: Secure wallet creation and management within the bot
- **Referral System**: Multi-level referral rewards (5 tiers: 35%, 3%, 1.5%, 1%, 0.5%)
- **User Discounts**: 10% discount on bot fees for active users
- **Transaction History**: Track your swap transactions and view transaction links

### Technical Features
- **MongoDB Integration**: Persistent user data storage
- **Redis Support**: Caching and performance optimization
- **Comprehensive Logging**: Detailed logging system for debugging and monitoring
- **Error Handling**: Robust error handling and user feedback

## 🛠️ Tech Stack

- **Runtime**: Node.js with TypeScript
- **Blockchain**: Solana Web3.js, Metaplex SDK
- **DEX Integration**: 
  - Raydium SDK
  - Jupiter Aggregator
  - Pumpfun Protocol
- **Transaction Processing**: Jito Block Engine
- **Database**: MongoDB (Mongoose)
- **Cache**: Redis
- **Telegram**: node-telegram-bot-api
- **Logging**: Custom logger with file output

## 📋 Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- MongoDB instance
- Redis instance (optional but recommended)
- Telegram Bot Token (from [@BotFather](https://t.me/botfather))
- Solana RPC endpoint (or use public endpoints)

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/srdev23/zeusbot
   cd ZeusBot
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Build the project**
   ```bash
   npm run build
   ```

## ⚙️ Configuration

Create a `.env` file in the root directory with the following variables:

```env
# Telegram Bot Configuration
BOT_TOKEN=your_telegram_bot_token_here

# Solana Configuration
RPC_URL=https://api.mainnet-beta.solana.com
WSS_URL=wss://api.mainnet-beta.solana.com

# Database Configuration
MONGO_URI=mongodb://localhost:27017/zeusbot

# Optional: Bot Wallet (for fee collection)
BOT_WALLET_PUBLIC_KEY=your_bot_wallet_public_key
```

## 🚀 Usage

### Starting the Bot

**Development mode** (with auto-reload):
```bash
npm run dev
```

**Production mode**:
```bash
npm start
```

### Bot Commands

- `/start` - Initialize the bot and create your account
- `/setting` - Configure your trading settings (slippage, Jito fee, snipe amount)
- `/position` - View your current token positions
- `/help` - Display help information

### How to Trade

1. **Manual Trading**:
   - Send a Solana token contract address to the bot
   - The bot will display token information
   - Choose a preset amount or enter a custom SOL amount
   - Confirm the swap

2. **Auto-Swap Mode**:
   - Enable auto-swap in settings
   - Simply send a token contract address
   - The bot will automatically execute a trade using your configured snipe amount

3. **Settings Configuration**:
   - Use `/setting` to access configuration options
   - Set your wallet private key (required for trading)
   - Configure slippage tolerance (default: 100%)
   - Set Jito tip amount for priority transactions
   - Set default snipe amount for auto-swap

### Referral System

Share your referral link to earn rewards:
- 1st level: 35% of trading fees
- 2nd level: 3% of trading fees
- 3rd level: 1.5% of trading fees
- 4th level: 1% of trading fees
- 5th level: 0.5% of trading fees

Your referral link format: `https://t.me/your_bot_username?start=YOUR_REFERRAL_CODE`

## 📁 Project Structure

```
ZeusBot/
├── src/
│   ├── config/           # Configuration files
│   │   ├── config.ts     # Main configuration
│   │   ├── constants.ts  # Bot constants and captions
│   │   └── db.ts         # Database connection
│   ├── service/
│   │   ├── bot/          # Bot handlers
│   │   │   ├── callback.handler.ts
│   │   │   └── message.handler.ts
│   │   ├── swap/         # Swap services
│   │   │   ├── raydium/  # Raydium DEX integration
│   │   │   ├── pumpfun/  # Pumpfun integration
│   │   │   ├── jupiter/  # Jupiter aggregator
│   │   │   ├── jito/     # Jito bundling service
│   │   │   └── swap.ts   # Main swap logic
│   │   ├── token/        # Token services
│   │   ├── userService/  # User management
│   │   └── msgService/   # Message services
│   ├── utils/            # Utility functions
│   ├── logs/             # Logging system
│   └── index.ts          # Entry point
├── package.json
├── tsconfig.json
└── README.md
```

## 🔐 Security Notes

- **Private Keys**: Your wallet private key is stored encrypted in the database. Never share your private key.
- **Environment Variables**: Keep your `.env` file secure and never commit it to version control.
- **Bot Token**: Protect your Telegram bot token to prevent unauthorized access.

## 📝 Scripts

- `npm start` - Start the production server
- `npm run build` - Compile TypeScript to JavaScript
- `npm run dev` - Start development server with auto-reload
- `npm run clean` - Clean compiled files
- `npm test` - Run tests

## 🐛 Troubleshooting

### Common Issues

1. **Bot not responding**:
   - Check if `BOT_TOKEN` is correctly set in `.env`
   - Verify MongoDB connection
   - Check bot logs in `src/logs/logs/`

2. **Swap failures**:
   - Ensure sufficient SOL balance (account for fees and slippage)
   - Verify RPC endpoint is accessible
   - Check token contract address validity

3. **Database connection errors**:
   - Verify MongoDB is running
   - Check `MONGO_URI` in `.env` file

## 📄 License

MIT License - see LICENSE file for details

## ⚠️ Disclaimer

This bot is for educational and personal use. Trading cryptocurrencies involves risk. Always:
- Use at your own risk
- Start with small amounts
- Understand the risks involved
- Never invest more than you can afford to lose

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Contact

For issues, questions, or support, please open an issue on the repository.
- [Github](https://github.com/srdev23)

- [Telegram](https://t.me/srdev23)

---

**Made with ⚡ for the Solana ecosystem**
