🎓 Blockchain-Based Decentralized Certificate Issuance and Verification System
📌 Overview

This project is a decentralized application (DApp) that allows educational institutes to issue, revoke, and manage certificates using Ethereum smart contracts. Employers and the public can verify the authenticity of certificates directly on the blockchain, ensuring they are secure, tamper-proof, and transparent.

🚀 Features

Register authorized institutes on the blockchain

Issue certificates to students via smart contracts

Revoke or cancel invalid certificates

Verify certificates online using certificate ID

Tamper-proof, transparent, and accessible verification system

🛠 Tech Stack

Frontend: React.js

Blockchain: Ethereum (Smart Contracts in Solidity)

Frameworks: Truffle, Ganache

Wallet Integration: MetaMask

Deployment: Infura (for testnets like Sepolia/Rinkeby)

Security Testing: Mythril

📂 Project Structure
Certoshi
│── assets              # Images, logos, screenshots  
│── client              # React.js frontend code  
│── contracts           # Solidity smart contracts  
│── migrations          # Deployment scripts  
│── scripts             # Helper scripts  
│── test                # Smart contract test cases  
│── truffle-config.js   # Truffle configuration  
│── README.md           # Documentation  

⚙️ Installation & Setup
1. Clone Repository
git clone https://github.com/your-username/Certoshi.git
cd Certoshi

2. Install Dependencies
npm install

3. Setup Local Blockchain (Ganache)

Option 1: Ganache GUI → Create new workspace, select truffle-config.js.

Option 2: Ganache CLI

npm install -g ganache-cli
ganache-cli

4. Environment Variables

Create a .env file in root directory:

LOCAL_ENDPOINT=http://127.0.0.1:8545
NETWORK_ID=1337

5. Compile & Deploy Smart Contracts
truffle compile
npm run deploy:local

6. Setup Client Application
cd client
npm install


Create .env inside client/ folder:

REACT_APP_LOCAL_ENDPOINT=http://127.0.0.1:8545
REACT_APP_NETWORK_ID=1337


Run frontend:

npm start


Visit → http://localhost:3000/
 🎉

🔑 MetaMask Setup

Add Localhost 8545 network in MetaMask

RPC URL: http://127.0.0.1:8545

Chain ID: 1337

Import accounts from Ganache using private keys.

🧪 Testing

Run smart contract tests:

truffle test


Run security analysis with Mythril (requires Docker):

docker pull mythril/myth
docker run -v $(pwd):/contracts mythril/myth analyze /contracts/Certification.sol

📌 Use Cases

Institutes → Register and issue certificates

Institutes → Revoke invalid certificates

Employers/Public → Verify certificates online by ID

Students → Get secure, trusted certificates


👥 Team Members

[Rajesh B]

[Prabhas P]

[Suleman G]

[Vishnu Vardhan B]

This project is licensed under the MIT License – feel free to use and modify.
