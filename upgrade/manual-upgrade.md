# 🔨 Manual upgrade

**Upgrade to v0.31.9**

```bash
cd $HOME
rm -rf namada
git clone https://github.com/anoma/namada
cd namada
wget https://github.com/anoma/namada/releases/download/v0.31.9/namada-v0.31.9-Linux-x86_64.tar.gz
tar -xvf namada-v0.31.9-Linux-x86_64.tar.gz
rm namada-v0.31.9-Linux-x86_64.tar.gz
cd namada-v0.31.9-Linux-x86_64
sudo mv namad* /usr/local/bin/
sudo systemctl restart namadad && sudo journalctl -u namadad -f
```
