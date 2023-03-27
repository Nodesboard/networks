## Chain explorer
[https://exp.nodesboard.com/realio](https://exp.nodesboard.com/realio)

## Public endpoints

* api: [https://api-realio.nodesboard.com](https://api-realio.nodesboard.com)
* rpc: [https://rpc-realio.nodesboard.com](https://rpc-realio.nodesboard.com)
* grpc: grpc-realio.nodesboard.com

## Peering

**addrbook**
```bash
curl -Ls https://ss.nodesboard.com/t/realio/addrbook.json > $HOME/.realio-network/config/addrbook.json
```

**live-peers** (36)
```bash
peers=""
sed -i -e "s|^persistent_peers *=.*|persistent_peers = \"$peers\"|" $HOME/.realio-network/config/config.toml
```
