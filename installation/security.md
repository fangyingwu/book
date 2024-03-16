# 🔨 Security

To protect you keys please don\`t share your privkey, mnemonic and follow a basic security rules

#### Set up ssh keys for authentication <a href="#ssh" id="ssh"></a>

You can use this [guide](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04) to configure ssh authentication and disable password authentication on your server

**Firewall security**\
Set the default to allow outgoing connections, deny all incoming, allow ssh and node p2p port

```bash
sudo ufw default allow outgoing 
sudo ufw default deny incoming 
sudo ufw allow ssh/tcp 
sudo ufw allow ${NAMADA_PORT}656/tcp
sudo ufw enable
```
