# Solana Jito/Jupiter Automated Trading Bot

A fully automated trading bot built on Solana using Node.js.  
It listens to on-chain webhook events, detects new tokens, validates them through anti-rug checks, executes trades using Jupiter and Jito bundles, monitors price movements, automatically takes profit, and streams real-time logs to Discord.

---

## ✨ Features

- Real-time webhook ingestion (SWAP / TRANSFER events)
- Automatic token detection and validation (freeze authority, supply patterns)
- Token purchase via Jupiter Swap API
- Transaction execution through Jito block engine (bundles + tip)
- Continuous price monitoring via Jupiter Price API
- Automatic sell logic with configurable profit thresholds
- PnL computation in SOL and %
- Automatic SOL treasury management (profit wallet transfers)
- Rich logging via Discord embeds + local log files
- Fault-tolerant retries, global error handling and automatic restart logic

---

## 🧱 Tech Stack

- **Node.js**, **Express**
- **Solana**: `@solana/web3.js`, `@solana/spl-token`, `@project-serum/anchor`
- **DeFi integrations**: Jupiter Quote/Swap API, Jupiter Price API
- **MEV / execution**: Jito (`jito-ts`, bundles, tips)
- **Observability**: `discord.js`, filesystem logs
- **HTTP / Utils**: `axios`, `node-fetch`, `dotenv`

---

## ⚙️ Environment Variables

Create a `.env` file with:

```
PRIVATE_KEY=
API_KEY=
SELLER=
DISTRIB=
BOT_WALLET=
PROFIT_WALLET=
MASTER_WALLET=
DISCORD_WEBHOOK_URL=
DISCORD_WEBHOOK_URL_2=
DISCORD_WEBHOOK_URL_3=
```


All variables are validated at startup.  
The app will exit if any required value is missing.

---

## 🚀 Installation & Usage

```bash
git clone https://github.com/kathiouchka/solana-jito-sniper-bot.git
cd solana-jito-sniper-bot
npm install
npm start
```

