# ElizaOS Deployment Guide on Akash Network

This guide will walk you through the steps to deploy ElizaOS express AI and client on the Akash Network as well as the Client on Vercel

## Prerequisites

- Access to [Akash Console](https://console.akash.network)
- Keplr Wallet installed
- Basic knowledge of SSH and command-line operations

## Steps

### 1. Navigate to Akash Console

Go to [console.akash.network](https://console.akash.network).

### 2. Install Keplr Wallet

Install the Keplr Wallet extension from your browser's extension store.

### 3. Access Deployment Section

Navigate to the deployment section on the Akash Console.

### 4. Copy SDL File

Copy the SDL file provided for deployment.

### 5. Deploy

Click on "Deploy" to start the deployment process.

### 6. Accept Bid

Accept the bid (cost approximately 0.5 AKT, around $2). This will last for 12-15 hours. You can add funds to keep it running longer.

### 7. SSH into the Instance

SSH into the deployed instance using the provided credentials.

### 8. Clone ElizaOS Repository

```sh
git clone https://github.com/elizaOS/eliza
```

### 9. Install NVM

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
export NVM_DIR="\$HOME/.nvm"
[ -s "\$NVM_DIR/nvm.sh" ] && \. "\$NVM_DIR/nvm.sh"
[ -s "\$NVM_DIR/bash_completion" ] && \. "\$NVM_DIR/bash_completion"

### 10. Install Node.js Version 23

nvm install 23
11. Install pnpm

curl -fsSL https://get.pnpm.io/install.sh | sh -
source /root/.bashrc
12. Navigate to Eliza Directory

cd eliza
13. Use Node.js Version 23

nvm use 23
14. Get Grok API Key
Go to x.ai/api and get your Grok API key (looks like xai-...).

15. Copy Environment Example

cp .env.example .env
16. Install Dependencies

pnpm i
17. Build the Project

pnpm build
18. Install Micro Editor

apt-get install micro
19. Edit .env File
Open the .env file with Micro:


micro .env
Look for GROK_API_KEY=<YOUR-API-KEY> and replace <YOUR-API-KEY> with your actual Grok API key. Save and exit (Ctrl+S, then Ctrl+Q).

20. Navigate to Client Directory

cd client
21. Edit Vite Configuration
Open vite.config.ts with Micro:


micro vite.config.ts
Add host: '0.0.0.0'. Save and exit (Ctrl+S, then Ctrl+Q).

22. Navigate to Characters Directory

cd characters
23. Edit Trump Character JSON
Open trump.character.json with Micro:


micro trump.character.json
In the client section, set ["direct"]. For modelProvider, set "grok" instead of "openai". Save and exit (Ctrl+S, then Ctrl+Q).

24. Run Backend Express API

nohup pnpm start --character="characters/trump.character.json" &
25. Start Client

pnpm start client


