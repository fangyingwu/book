# 🔨 RPC,Peers,Seeds

### RPC, Peers, Seed, Addrbook, Genesis <a href="#rpc" id="rpc"></a>

Public RPC:[https://namada-testnet-rpc.itrocket.net:443](https://namada-testnet-rpc.itrocket.net/)\
Public RPC (node operations):[tcp://namada-testnet-tcprpc.itrocket.net:33657](tcp://namada-testnet-tcprpc.itrocket.net:33657)\
Public indexer:[https://namada-testnet-indexer.itrocket.net/block/last](https://namada-testnet-indexer.itrocket.net/block/last)

peers:

{% code fullWidth="false" %}
```
7233f22a664457479a6b194f590f2db95c726240@namada-testnet-peer.itrocket.net:33656
```
{% endcode %}

seed:

```
59976ccee681325acda4c9e2e77e21b085f88826@namada-testnet-seed.itrocket.net:33656
```

live peers:

```
PEERS="tcp://7233f22a664457479a6b194f590f2db95c726240@namada-testnet-peer.itrocket.net:33656,tcp://0546acfa046274f76d1f77b72c567768bd2d5cca@185.172.191.9:26656,tcp://a049bc959640d1186dbd094530cd2da82a484ae0@34.150.187.1:26656"
sed -i 's|^persistent_peers *=.*|persistent_peers = "'$PEERS'"|' $HOME/.local/share/namada/shielded-expedition.88f17d1d14/config.toml
```
