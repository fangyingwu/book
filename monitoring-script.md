# 🤖 Monitoring Script

### Node Monitoring Script <a href="#monitoring" id="monitoring"></a>

* Tracks validator status: missed blocks, voting power, and sends alerts.
* Compares block height with an external server and restarts when significantly out of sync.
* Checks node status, restarts if unresponsive.
* Sends alerts and status updates via Telegram.

Download namada.sh file:

```bash
cd $HOME
rm -rf $HOME/monitoring
mkdir $HOME/monitoring
cd $HOME/monitoring
wget -O namada.sh https://raw.githubusercontent.com/itrocket-team/testnet_guides/main/namada/monitoring/namada.sh
chmod +x namada.sh
```

#### Configure Telegram alerting:

Open Telegram and find [@BotFather](https://t.me/BotFather)

* Create telegram bot via @BotFather, customize it and get bot API token
* Create the group: alarm. Customize them, add the bot in your chat and get chats IDs: [how to do it](https://stackoverflow.com/questions/32423837/telegram-bot-how-to-get-a-group-chat-id)
* Open namada.sh file

change ENABLE=false to ENABLE=true

#### Specify your node <mark style="background-color:blue;">RPC\_SERVER</mark> , <mark style="background-color:blue;">TELEGRAM\_CHAT\_ID</mark> and <mark style="background-color:blue;">TELEGRAM\_BOT\_TOKEN</mark>:

> Configure correct Namada node port - RPC\_SERVER.\
> Customize TELEGRAM\_CHAT\_ID and TELEGRAM\_BOT\_TOKEN.\
> Configure BLOCK\_GAP\_ALARM and allow RESTART function if needed.

```bash
nano namada.sh
```

#### Create a new tmux session:

```bash
cd $HOME
tmux new -s monitoring
```

#### Start monitoring script:

Finally, start the Namada node monitoring script:

```bash
cd $HOME/monitoring
sudo /bin/bash namada.sh
```

Don't stop process with CTRL+C, if you want to disconnect the session use CTRL+B D. If you want to kill session use CTRL+B C

> If you want to connect disconnected session use:

```bash
tmux attach -t monitoring
```
