# firedancer
This role installs and upgrades the firedancer validator.

## Role variables
```yaml
solana_version: 0.1
solana_user: ubuntu

# local path to clone repository
code_path: "/home/{{ solana_user }}/code"

# location to install binary
local_installation_path: /usr/local/bin

# config.toml
ledger: /mnt/ledger
rpc_port: 8899
private_rpc: true
known_validators:
  - 5D1fNXzvv5NjV1ysLjirC4WY92RNsVH18vjmcszZd8on
  - 141vSYKGRPNGieSrGJy8EeDVBcbjSr6aWkimNgrNZ6xN
  - BFquPCAYdjN9QyLVfuGrQdJTF9Ct7Z85FDxhFeLcpFqR
entrypoints:
  - entrypoint.testnet.solana.com:8001
  - entrypoint2.testnet.solana.com:8001
  - entrypoint3.testnet.solana.com:8001
```