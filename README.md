# firedancer
This role installs and upgrades the firedancer validator.

## Prerequisites
- Create a ledger disk, partition it, set permissions.
- Create firedancer_service_user

## Role variables
```yaml
# version of firedancer to install
solana_version: 0.1

# user to SSH as and run playbook
solana_user: ubuntu

# service user to run firedancer as (not created for you!)
firedancer_service_user: firedancer

# remote path to clone repository to on server
code_path: "/home/{{ solana_user }}/code"

# location to install binary
local_installation_path: /usr/local/bin

# config.toml - firedancer validator configuration values
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
