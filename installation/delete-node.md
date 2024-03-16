# 🔨 Delete node

```bash
sudo systemctl stop namadad
sudo systemctl disable namadad
sudo rm -rf /etc/systemd/system/namadad.service
sudo systemctl daemon-reload
sudo rm $(which namada)
sudo rm -rf $HOME/.local/share/namada/public-testnet-15.0dacadb8d663
```
