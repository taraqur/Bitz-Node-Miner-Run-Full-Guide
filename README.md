# Bitz-Node-Miner-Run-Full-Guide


1️⃣ Dependencies for WINDOWS & LINUX & VPS & Mac

For WSL or VPS
```
sudo apt update && sudo apt upgrade -y
sudo apt install curl nano build-essential -y
```


2️⃣ Install Rust & Node Js & Yarn

For WSL or VPS
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustc --version
```
- Just Press Enter to Proceed it
```
sudo apt-get update && curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash - && sudo apt-get install -y nodejs && node -v && npm -v && sudo npm install -g yarn && yarn -v
```



3️⃣ Install Solana CLI

For WSL 
```
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```
```
source $HOME/.bashrc
```
- Close and Reopen your Terminal > Then Directly Paste Below Command (open again wsl)
```
solana --version
```
If you get Solana: command not found RUN (WSL for Local PC)
```
echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```


4️⃣ Configue RPC for Eclipse
```
solana config set --url https://eclipse.helius-rpc.com/
```

5️⃣ Wallet Setup (Solana Keypair)
```
solana-keygen new
```
Press ENTER and save the passphrase

6️⃣ Exporting Private Key from ID.json
```
cat ~/.config/solana/id.json
```
* Copy the output (a list of numbers) and import it into Backpack Wallet under “Private Key”.
* Fund the wallet with 1$ ETH on Eclipse to activate mining.



7️⃣ Install Bitz CLI
```
cargo install bitz
```


8️⃣ 🅰️ Start Miner
```
bitz collect
```

OR

8️⃣ 🅱️ Start Miner (using multiple core) 
```
bitz collect --cores 8
```

### How to check your own CPU Cores (Open Command Prompt or PowerShell)

```
wmic cpu get NumberOfCores,NumberOfLogicalProcessors
```

```
wmic cpu get NumberOfCores
```


### Claim Mined tokens 
```
bitz claim
```

### Check Wallet status 
```
bitz account
```


## 🔶For Next Day Run This Command (Windows or Mac)

#1 Open WSL or HomeBrew and Put this Command 
```
bitz collect
```

## Delete Node File
```
rm -rf ~/.config/solana
```

## If You Facing Auto Crashed Error (Core Dumped error)


Put One by One Command & Run it
```
RUST_BACKTRACE=1 ./bitz
```
```
solana config get
```
```
sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
```
```
cargo install bitz --force
```
- For Local PC Directly Run Start Miner Command
