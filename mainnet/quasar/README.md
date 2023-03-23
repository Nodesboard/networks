# Services

<figure><img src="https://raw.githubusercontent.com/kj89/cosmos-images/main/logos/quasar.png" width="150" alt=""><figcaption></figcaption></figure>

Quasar (pronounced QWAY-ZAR) is a decentralized  appchain enabling interchain digital asset management.

**Chain ID**: quasar-1 | **Latest Version Tag**: v0.1.0 | **Wasm**: ON

[Website](https://www.quasar.fi) | [Discord](https://discord.gg/quasarfi) | [Twitter](https://twitter.com/QuasarFi)



Subscribe to our free [🤖 Mainnet Proposal Bot](https://t.me/kjnodes_proposal_bot) to never miss upcoming proposals


## Chain explorer
[https://explorer.kjnodes.com/quasar](https://explorer.kjnodes.com/quasar)

## Public endpoints

* api: [https://quasar.api.kjnodes.com](https://quasar.api.kjnodes.com)
* rpc: [https://quasar.rpc.kjnodes.com](https://quasar.rpc.kjnodes.com)
* grpc: quasar.grpc.kjnodes.com:48090

## Peering

**state-sync**

```text
d9bfa29e0cf9c4ce0cc9c26d98e5d97228f93b0b@quasar.rpc.kjnodes.com:48656
```

**seed-node**

```text
400f3d9e30b69e78a7fb891f60d76fa3c73f0ecc@quasar.rpc.kjnodes.com:48659
```

**addrbook**
```bash
curl -Ls https://snapshots.kjnodes.com/quasar/addrbook.json > $HOME/.quasarnode/config/addrbook.json
```

**live-peers** (20)
```bash
peers="10e73ac4ab3f9e1edd89e1aa342eb4d4f11120f0@135.181.128.114:18256,d2247f7b919f0781c90ee61958d7044665a22d38@169.155.169.84:26656,d9bfa29e0cf9c4ce0cc9c26d98e5d97228f93b0b@65.109.88.38:48656,201eb8fc1e84beb4bdce8ae5614c7abb41e32edb@65.109.160.91:18256,982e80ee53fedcb54a19d5f0dba154a0c1aedc2a@3.34.113.161:26656,1369d544be2680e031b57f30a8d18cbe8b17a8ef@54.38.73.121:26656,771659b9205187f9094f894c65d29effa79fdd2c@18.156.191.84:26656,a7d96dc929824613315dcc1c90fee119f28cc51f@134.65.193.189:26656,5a111b281852be31838ecf1202e59981e618355e@89.116.31.95:18256,bcbc915effeb5e1f4e96670fd68d20a08ad4efa1@65.108.138.80:18256,e62ce06e60a986ed04d2e080876a41e3b57a5304@93.190.141.218:26656,240c09f5d91d2c252cf29faa1a88aebd563d2561@57.128.144.247:26656,8688b59432d98b6ded8bed01c3c29d4892ae6e4f@38.146.3.149:18256,298e0e1faf8a5da43514cc2908d2908658e732a0@38.146.3.148:18256,4399187c748f91d86932d3e530cd16c22c5f616a@199.231.163.42:26656,8f74699ec25e0ab5a60911e21135a9a330da8399@50.18.180.161:26656,88cc4d314c9804a9478e900b6f18a83ea58a98c6@57.128.20.163:18256,49b72b4c79d589955a5004797b45ee306da6a889@143.42.237.237:26656,a40e1d5f63fad9e14edb9c95458b27f3c1de858c@116.203.236.246:26618,b212d5740b2e11e54f56b072dc13b6134650cfb5@134.65.192.124:26656"
sed -i -e "s|^persistent_peers *=.*|persistent_peers = \"$peers\"|" $HOME/.quasarnode/config/config.toml
```