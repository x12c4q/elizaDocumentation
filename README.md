# ElizaOS Deployment Guide on Akash Network

This guide will walk you through the steps to deploy ElizaOS on the Akash Network.

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
