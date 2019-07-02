# bnb_node

## Instalationion 

```
git clone https://github.com/binance-chain/node-binary.git
cd node-binary/lightd/lightnode/testnet/0.5.8/os
```

## Run node

```
./lightd --chain-id "Binance-Chain-Nile" --node tcp://data-seed-pre-0-s1.binance.org:80
```

## Chrck status

Send get response to `http://localhost:27147/status`

Output:

```
{
    "jsonrpc": "2.0",
    "id": "",
    "result": {
        "node_info": {
            "protocol_version": {
                "p2p": "7",
                "block": "10",
                "app": "0"
            },
            "id": "9612b570bffebecca4776cb4512d08e252119005",
            "listen_addr": "a0b88b324243a11e994280efee3352a7-96b6996626c6481d.elb.ap-northeast-1.amazonaws.com:27146",
            "network": "Binance-Chain-Nile",
            "version": "0.31.5",
            "channels": "364020212223303800",
            "moniker": "data-seed-0",
            "other": {
                "tx_index": "on",
                "rpc_address": "tcp://0.0.0.0:27147"
            }
        },
        "sync_info": {
            "latest_block_hash": "6EF2B63E4FB7A8C53FE26BEAD1EB9B34F463A237FB4C94CC97ADB9C62330BD8D",
            "latest_app_hash": "BF50C03D2FE35EF8DF150C25116979836A8053A6B6C9A311F4ADB62A7D94BF80",
            "latest_block_height": "25425958",
            "latest_block_time": "2019-07-02T12:31:47.924884923Z",
            "catching_up": false
        },
        "validator_info": {
            "address": "E44C14E60CE7D88752B2B144B164DFF2A20AA1D0",
            "pub_key": {
                "type": "tendermint/PubKeyEd25519",
                "value": "sbWMMKiniIxJunFq466D4yJAfmeQHuzP0PyX5FbHKKE="
            },
            "voting_power": "0"
        }
    }
}
```

## Import key

```
./tbnbcli keys add --recover key_name
```
Then provide password and mnemonic phrase.

## Issue token

```
./tbnbcli token issue --token-name "Essentia" --total-supply 100000000000000000 --symbol ESS --from key  --chain-id "Binance-Chain-Nile" --node tcp://data-seed-pre-0-s1.binance.org:80 --trust-node 
```
Probably works for valid account.
