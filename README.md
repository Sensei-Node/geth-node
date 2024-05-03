# Introduction

Docker Compose implementation of `GETH`

## How to Launch a Full Node with GETH Client

### Recommended Hardware 

```shell
- Fast CPU with 4+ cores
- 16 GB+ RAM
- Fast SSD with at least 700 GB free space in fast sync and 6TB+ in full archive mode
- 25+ MBit/s bandwidth
```

### Network

```shell
- 8545  TCP, used by the HTTP based JSON RPC API
- 8546  TCP, used by the WebSocket based JSON RPC API
- 8547  TCP, used by the GraphQL API
- 30303 TCP  and UDP, used by the P2P protocol running the network
- 8551  TCP, Engine API - needed only for eth2 validators
```

## How to Launch Using `docker-compose`:

- Clone this repository, run:

```shell
git clone https://github.com/Sensei-Node/geth-node
```

- Navigate to `geth-node` folder:
```shell
cd geth-node
```

- Then run the following docker compose command:
```
docker-compose up -d 
```

## Verify Node is Syncing

- The following curl command will give you a true statment if the node is still syncing:

```shell
curl --location --request POST 'localhost:8545' --header 'Content-Type: application/json' --data-raw '{"jsonrpc":"2.0","method":"eth_syncing","params":[],"id":1}'
```

- Check docker logs to see the `block_height`:

```shell
docker logs --tail 100 ethereum
```

## Adding Local Node to MetaMask

- If you are running the `GETH Node` on your local Network, you can add it to your MetaMask changing networks to `localhost 8545`, if you are running on a `VM (Virtual Machine)` you can add the `IP` to your trusted networks, make sure to have `8545` port open.

## Resources
- [Official Geth client installation](https://geth.ethereum.org/docs/install-and-build/installing-geth)
- [API docs](https://geth.ethereum.org/docs/rpc/server)
- [Connect Node to MetaMask](https://metamask.zendesk.com/hc/en-us/articles/360015290012) 

# Contributing

- Contributions are welcome. Feel free to suggest improvements!

Made with ❤️ by [Sensei Team](https://github.com/orgs/Sensei-Node/people)
