# Aztec-Testnet-Simple-Setup

### Alpha testnet has been concluded now on testnet
This is a guide to setup the Aztec testnet node as a new community member

## Input password when asked

`sudo su`

`cd`

## Update Packages

``sudo apt-get update``

``sudo apt-get upgrade -y``

## Install Build Essentials

`sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y`

## Install Aztec Tool

`bash -i <(curl -s https://install.aztec.network)`

## Add Aztec to PATH

`echo 'export PATH="$HOME/.aztec/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc`


## Check version

`aztec`

## Update version when needed

`aztec-up alpha-testnet`

## Getting RPC

https://github.com/cerberus-node/aztec-network/blob/main/auto_setup_sepolia.md

Or you can ask a friend to whitelist your rpc. Join the discord to connect with other community members and make friends

## Check IP

`curl ipinfo.io/ip`

## Allow Firewall Access

`sudo ufw allow ssh`

`sudo ufw enable`


`sudo ufw allow 40400`

`sudo ufw allow 40500`

`sudo ufw allow 8080`

## Environmental Variable

`export DATA_DIRECTORY=/root/aztec-data/
export COINBASE=
export LOG_LEVEL=debug
export P2P_MAX_TX_POOL_SIZE=1000000000`

## Open new screen

`screen -S aztec`

## Starting NODE

`aztec start \
  --network \ <network-name> \
  --l1-rpc-urls "<rpc-url>" \
  --l1-consensus-host-urls "<consensus-url>" \
  --sequencer.validatorPrivateKey "<private-key>" \
  --p2p.p2pIp "<local-ip>" \
  --p2p.maxTxPoolSize 1000000000 
  --archiver \
  --node \
  --sequencer`

  ## Placeholders for command

network-name: `testnet`

rpc-url: your `whitelist rpc`

consensus-url: your `whitelisted CL`

private-key: `your private key (keep it secure)`

local-ip: use `curl ifconfig.me` to find your local IP

# If needed 

## Delete Data base

`rm -rf ~/.aztec/alpha-testnet/data/ `

## Update Node

`aztec-up testnet`

## Join Validator Set

You can join the Validator set by using Zk passport 

Go to : https://testnet.aztec.network/add-validator

Complete all the steps
