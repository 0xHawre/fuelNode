# fuel_Node
Fuel is an operating system purpose-built for Ethereum rollups, designed to help developers build decentralized economies at scale.

## Hardware Requirements

| Hardware  | Minimum      | Recommended |
|-----------|--------------|-------------|
| Processor | 2 Cores      | 8 Cores     |
| Memory    | 4 GB         | 12 GB       |
| Storage   | 30 GB        | 100 GB      |

## Installation

Follow these steps to set up the project on your local machine:

### Step 1: Update and Upgrade Packages

Update the package lists and upgrade the installed packages to the latest versions.

```sh
sudo apt-get update && sudo apt-get upgrade -y
```

### Step 2: Install Necessary Tools

Install wget and curl, which are essential for downloading files and making network requests.

```sh
sudo apt install wget curl
```

### Step 3: Install Rust
Use curl to download and install Rust using the official Rust installer script.

```sh 
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs/ | sh
```

If the above method doesn't work, you can also install Rust using the package manager:
```sh
sudo apt install rustup
```
### Step 4: Install Git
Install Git, a version control system, which is necessary for cloning repositories and managing project code.

```sh
sudo apt install git
```

### Step 5: Install Fuel Network
Use curl to download and install Fuel Network.

```sh
curl https://install.fuel.network | sh
```
### Step 6: Source Bash Configuration
Source the bash configuration file to apply changes.

```sh
source /root/.bashrc
```

### Step 7: Update PATH
Export the Fuel Network binary path to the system PATH.

```sh
export PATH="/root/.fuelup/bin:$PATH"
```
### Step 8: Install Latest Fuelup Toolchain
Install the latest version of the Fuelup toolchain.
```sh
fuelup toolchain install latest
```
### Step 9: Update Fuelup
Update Fuelup to the latest version.
```sh 

fuelup self update
```
### Step 11: Install Nightly Fuelup Toolchain
Install the nightly version of the Fuelup toolchain.
```sh
fuelup toolchain install nightly
```
### Step 12: Set Nightly Toolchain as Default
Set the nightly version of the Fuelup toolchain as the default.
```sh
fuelup default nightly
```
### Step 13: Show Fuelup Configuration
Display the current configuration of Fuelup.

```sh
fuelup show
```
### Step 14: Create a New Wallet
Create a new wallet using forc.
```sh
forc wallet new
```
During this step, submit a password and save the Wallet  phrase.

### Step 15: Create a New Wallet Account
Create a new account for the wallet and write down the wallet address.

```sh
forc wallet account new
```
### Step 16: Reset Fuelup to Default
Reset Fuelup to its default configuration.

```sh 
fuelup default
```
### Step 17: Clone the Repository
Clone the project repository from GitHub.

```sh
git clone https://github.com/0xHawre/fuelNode
```

### Step 18: Install Testnet Fuelup Toolchain
Install the testnet version of the Fuelup toolchain.

```sh
fuelup toolchain install testnet
```
### Step 19: Set Testnet Toolchain as Default
Set the testnet version of the Fuelup toolchain as the default.

```sh 
fuelup default testnet
```
### Step 20: Generate New Peering Key
Generate a new peering key using fuel-core-keygen.

```sh
fuel-core-keygen new --key-type peering
```

### Step 21: Install Tmux
Install Tmux, a terminal multiplexer that allows multiple sessions.

```sh 
sudo apt-get install tmux
```
### Step 22: Start a New Tmux Session
Start a new Tmux session named "fuel".

```sh 
tmux new-session -s fuel
```

### Step 23: Run Fuel Core
Run the Fuel Core node with the following command, replacing {node-name}, {secret-key}, and {RPC-KEY} with appropriate values:
```SH
fuel-core run \
  --service-name={node-name} \
  --keypair {secret-key} \
  --relayer {RPC-KEY} \
  --ip=0.0.0.0 --port=5333 --peering-port=40453 \
  --db-path=~/.fuel-sepolia-testnet \
  --snapshot /root/.forc/git/checkouts/std-9be0d6062747ea7/2f0392ee35a1e4dd80bd8034962d5b4083dfb8b6/.github/workflows/local-testnode \
  --utxo-validation --poa-instant false --enable-p2p \
  --reserved-nodes /dns4/p2p-testnet.fuel.network/tcp/30333/p2p/16Uiu2HAmDxoChB7AheKNvCVpD4PHJwuDGn8rifMBEHmEynGHvHrf \
  --sync-header-batch-size 100 \
  --enable-relayer \
  --relayer-v2-listening-contracts=0x01855B78C1f8868DE70e84507ec735983bf262dA \
  --relayer-da-deploy-height=5827607 \
  --relayer-log-page-size=500 \
  --sync-block-stream-buffer-size 30
```

### step 24: exit tmux 
```sh
 CTRL + B then D
```

### now check youre RPC logs should be like this picture:

24/25 request per 1 min

<img width="1418" alt="Screenshot 2024-06-10 at 8 28 03 PM" src="https://github.com/0xHawre/fuelNode/assets/131952165/661a38c7-5195-4b99-be70-3f393b3ec034">



