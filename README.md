<div align=center>
  <img src="https://github.com/TempGROX/TempGROX/blob/main/src/photos/rounded-in-photoretrica.png" width="150">
  <h1>0g-storage-install-guide</h1>
  <br>
</div>

# Hardware Requirement

|KEY|VALUE|
|:--|:----|
|RAM|16 GB|
|CPU|4 cores|
|Disk|1 TB NVME SSD|
|Bandwidth|500 Mbps|

# Install for linux
## Install dependencies
1. 
  ```bash
  sudo apt-get update
  sudo apt-get install clang cmake build-essential
  ```
2. Install rustup
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
3. Install Go
   ```bash
    # Download the Go installer
    wget https://go.dev/dl/go1.22.0.linux-amd64.tar.gz

    # Extract the archive
    sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.22.0.linux-amd64.tar.gz

    # Add /usr/local/go/bin to the PATH environment variable by adding the following line to your ~/.profile.
    export PATH=$PATH:/usr/local/go/bin
   ```
## Download the source code
```bash
git clone -b v0.3.3 https://github.com/0glabs/0g-storage-node.git
```

## Build
```bash
cd 0g-storage-node
git submodule update --init

# Build in release mode
cargo build --release
```

## Configure the `run/config.toml`
```toml
network_enr_address

network_boot_nodes = ["/ip4/54.219.26.22/udp/1234/p2p/16Uiu2HAmTVDGNhkHD98zDnJxQWu3i1FL1aFYeh9wiQTNu4pDCgps","/ip4/52.52.127.117/udp/1234/p2p/16Uiu2HAkzRjxK2gorngB1Xq84qDrT4hSVznYDHj6BkbaE4SGx9oS","/ip4/18.167.69.68/udp/1234/p2p/16Uiu2HAm2k6ua2mGgvZ8rTMV8GhpW71aVzkQWy7D37TTDuLCpgmX"]

log_contract_address

mine_contract_address

blockchain_rpc_endpoint

log_sync_start_block_number

miner_key

db_max_num_chunks
```

## Run The storage Node

```bash
cd run

# consider using tmux in order to run in background
../target/release/zgs_node --config config-testnet.toml --miner-key <your_private_key> --blockchain-rpc-endpoint <blockchain_rpc> --db-max-num-chunks <max_chunk_num>
```
  

# The end!
If you liked this guide, please go to all my social networks)

<br>
<div id="badges" align="center">
  <a href="https://discord.com/users/961408999411048461">
    <img src="https://img.shields.io/badge/Discord-blue?style=for-the-badge&logo=https%3A%2F%2Fimg.icons8.com%2Fios%2F50%2Fmedium-logo.png&logoColor=white" alt="LinkedIn Badge"/>
  </a>
  <a href="https://medium.com/@James_Brandon">
    <img src="https://img.shields.io/badge/Medium-black?style=for-the-badge&logo=https%3A%2F%2Fimg.icons8.com%2Fios%2F50%2Fmedium-logo.png&logoColor=white" alt="Youtube Badge"/>
  </a>
  <a href="https://keybase.io/jamesbrandon">
    <img src="https://img.shields.io/badge/Keybase-orange?style=for-the-badge&logo=https%3A%2F%2Fimg.icons8.com%2Fios%2F50%2Fmedium-logo.png&logoColor=white">
  </a>
  <a href="https://x.com/JBTGrox">
    <img src="https://img.shields.io/badge/Twitter-blue?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter Badge"/>
  </a>
  <a href="https://linktr.ee/JBrandon_?utm_source=linktree_admin_share">
    <img src="https://img.shields.io/badge/Linktree-green?style=for-the-badge&logo=https%3A%2F%2Fimg.icons8.com%2Fios%2F50%2Fmedium-logo.png&logoColor=white">
  </a>
</div>
