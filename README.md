firedancer
=========
An Ansible role to deploy and upgrade the firedancer validator.


Requirements
------------
This role does not do any disk partitioning or user creation for you, so make sure you have that ready to go before running the role. Those tasks are considered outside the scope of this role.


Role Variables
--------------
```
# version of firedancer to install
# (0.1 points to latest release)
solana_version: 0.1

# remote user to SSH as and run commands
# (can be different and probably should be than the service user)
solana_user: ubuntu

# remote service user to run firedancer as
firedancer_service_user: firedancer

# remote path to clone repository to on server
code_path: "/home/{{ solana_user }}/code"

# remote location to install binary
remote_installation_path: /usr/local/bin

# config.toml
# firedancer validator configuration values
# these are standard validator configuration variables, so if you
# do not understand them, see Solana documentation.
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

Dependencies
------------
N/A

Example Playbook
----------------
I personally set values in the inventory, but you could certainly
pass them into the role here if you wanted.
```
    - hosts: servers
      roles:
         - { role: firedancer }
```

License
-------

BSD

Author Information
------------------
Blake Bartenbach <blakebartenbach@gmail.com>
