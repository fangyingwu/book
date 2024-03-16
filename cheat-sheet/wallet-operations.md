# 🔨 Wallet operations

create a new keypair:

```bash
namadaw gen --alias $WALLET
```

restore existing wallet:

```bash
namada wallet derive --alias $WALLET --hd-path default
```

find your wallet address:

```bash
namadaw find --alias $WALLET
```

add some tokens using faucet:

```bash
https://faucet.heliax.click/
```

check balance:

```bash
namadac balance --owner $WALLET
```

check all known keys and addresses in the wallet:

```bash
namadaw list
```

send payment from one address to another:

```bash
namadac transfer --source $WALLET --target ${WALLET}1 --token NAAN --amount 1 --signing-keys $WALLET --memo $MEMO
```

remove keys:

```bash
namadaw remove --alias $WALLET --do-it
```
