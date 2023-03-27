## Instructions

### Stop the service and reset the data

```bash
sudo systemctl stop realio-networkd
cp $HOME/.realio-network/data/priv_validator_state.json $HOME/.realio-network/priv_validator_state.json.backup
realio-networkd tendermint unsafe-reset-all --home $HOME/.realio-network
```

### Get and configure the state sync information

```bash
STATE_SYNC_RPC=https://rpc-realio.nodesboard.com:443
STATE_SYNC_PEER=d9bfa29e0cf9c4ce0cc9c26d98e5d97228f93b0b@rpc-realio.nodesboard.com:27656
LATEST_HEIGHT=$(curl -s $STATE_SYNC_RPC/block | jq -r .result.block.header.height)
SYNC_BLOCK_HEIGHT=$(($LATEST_HEIGHT - 2000))
SYNC_BLOCK_HASH=$(curl -s "$STATE_SYNC_RPC/block?height=$SYNC_BLOCK_HEIGHT" | jq -r .result.block_id.hash)

sed -i \
  -e "s|^enable *=.*|enable = true|" \
  -e "s|^rpc_servers *=.*|rpc_servers = \"$STATE_SYNC_RPC,$STATE_SYNC_RPC\"|" \
  -e "s|^trust_height *=.*|trust_height = $SYNC_BLOCK_HEIGHT|" \
  -e "s|^trust_hash *=.*|trust_hash = \"$SYNC_BLOCK_HASH\"|" \
  -e "s|^persistent_peers *=.*|persistent_peers = \"$STATE_SYNC_PEER\"|" \
  $HOME/.realio-network/config/config.toml

mv $HOME/.realio-network/priv_validator_state.json.backup $HOME/.realio-network/data/priv_validator_state.json
```

### Restart the service and check the log

```bash
sudo systemctl start realio-networkd && sudo journalctl -u realio-networkd -f --no-hostname -o cat
```
