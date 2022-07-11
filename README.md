# geth-node
Docker Compose implementation of GETH

## How to launch a full node with geth client

### Recommended hardware 
- Fast CPU with 4+ cores
- 16 GB+ RAM
- Fast SSD with at least 700 GB free space in fast sync and 6TB+ in full archive mode
- 25+ MBit/s bandwidth

### Network
- 8545 TCP, used by the HTTP based JSON RPC API
- 8546 TCP, used by the WebSocket based JSON RPC API
- 8547 TCP, used by the GraphQL API
- 30303 TCP and UDP, used by the P2P protocol running the network
- 8551 TCP, Engine API - needed only for eth2 validators

## How to launch using docker-compose

    git clone https://github.com/Sensei-Node/geth-node
    cd geth-node
    docker-compose up -d 

## Verify node is syncing

The following curl command will give you a true statment if the node is still syncing

```curl --location --request POST 'localhost:8545' --header 'Content-Type: application/json' --data-raw '{"jsonrpc":"2.0","method":"eth_syncing","params":[],"id":1}'```

Check docker logs to see the block_height

    docker logs --tail 100 ethereum

## Resources
- Official Geth client installation https://geth.ethereum.org/docs/install-and-build/installing-geth
- API docs: https://geth.ethereum.org/docs/rpc/server
