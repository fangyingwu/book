# 🔨 Snapshot

### Snapshot  <a href="#snap" id="snap"></a>

Download snapshot:

{% code title="updates every 4h" fullWidth="false" %}
```bash
cd $HOME
wget -O snap_namada.tar https://testnet-files.itrocket.net/namada/snap_namada.tar
```
{% endcode %}

Stop node and unpack snapshot:

{% code fullWidth="false" %}
```bash
sudo systemctl stop namadad
cp $HOME/.local/share/namada/shielded-expedition.88f17d1d14/cometbft/data/priv_validator_state.json $HOME/.local/share/namada/shielded-expedition.88f17d1d14/cometbft/priv_validator_state.json.backup
rm -rf $HOME/.local/share/namada/shielded-expedition.88f17d1d14/db $HOME/.local/share/namada/shielded-expedition.88f17d1d14/cometbft/data
tar -xvf $HOME/snap_namada.tar -C $HOME/.local/share/namada/shielded-expedition.88f17d1d14
mv $HOME/.local/share/namada/shielded-expedition.88f17d1d14/cometbft/priv_validator_state.json.backup $HOME/.local/share/namada/shielded-expedition.88f17d1d14/cometbft/data/priv_validator_state.json
```
{% endcode %}

Restart node:

{% code fullWidth="false" %}
```bash
sudo systemctl restart namadad && sudo journalctl -u namadad -f
```
{% endcode %}

Delete snap file:

```bash
rm -rf $HOME/snap_namada.tar
```
