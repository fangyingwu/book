# 🔨 Masp

randomly generate a new spending key:

```bash
namadaw gen --shielded --alias ${WALLET}-shielded
```

create a new payment address:

```bash
namadaw gen-payment-addr --key ${WALLET}-shielded --alias ${WALLET}-shielded-addr
```

send a shielding transfer:

```bash
namadac transfer --source $WALLET --target ${WALLET}-shielded-addr --token NAAN --amount 10 --memo $MEMO
```

view balance:

```bash
namadac balance --owner ${WALLET}-shielded
```

generate another spending key:

```bash
namadaw gen --shielded --alias ${WALLET}1-shielded
```

create a payment address:

```bash
namadaw gen-payment-addr --key ${WALLET}1-shielded --alias ${WALLET}1-shielded-addr
```

shielded transfers (once the user has a shielded balance, it can be transferred to another shielded address):

```bash
namadac transfer  --source ${WALLET}-shielded --target ${WALLET}1-shielded-addr --token NAAN --amount 4 --signing-keys <your-implicit-account-alias> --memo $MEMO
```

unshielding transfers (from a shielded to a transparent account):

```bash
namadac transfer --source ${WALLET}-shielded --target $WALLET --token NAAN --amount 4 --signing-keys <your-implicit-account-alias> --memo $MEMO
```
