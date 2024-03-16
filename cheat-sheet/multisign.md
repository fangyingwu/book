# 🔨 Multisign

generate key\_1:

```bash
namadaw gen --alias $WALLET
```

generate key\_2 and etc:

```bash
namadaw gen --alias ${WALLET}1
```

chech your public key:

```bash
namadaw find --alias $WALLET | awk '/Public key:/ {print $3}'
```

init non-multisig account (single signer):

```bash
namadac init-account --alias ${WALLET}-multisig --public-keys $WALLET --signing-keys $WALLET --memo $MEMO
```

init multisig account (at least 2 signers):

```bash
namadac init-account --alias ${WALLET}1-multisig --public-keys $WALLET,${WALLET}1 --signing-keys $WALLET,${WALLET}1 --threshold 2 --memo $MEMO
```

create a folder for a transaction:

```bash
mkdir tx_dumps
```

create transaction:

```bash
namadac transfer --source ${WALLET}1-multisig --target ${WALLET}1 --token NAAN --amount 10 --signing-keys $WALLET,${WALLET}1 --dump-tx --output-folder-path tx_dumps --memo $MEMO
```

sign the transaction:

```bash
namadac sign-tx --tx-path "<path-to-.tx-file>" --signing-keys $WALLET,${WALLET}1 --owner ${WALLET}1-multisig --memo $MEMO
```

save as a variable offline\_signature 1:

```bash
export SIGNATURE_ONE="<signature-file-name>"
```

save as a variable offline\_signature 2:

```bash
export SIGNATURE_TWO="<signature-2-file-name>"
```

submit transaction:

```bash
namadac tx --tx-path "<path-to-.tx-file>" --signatures $SIGNATURE_ONE,$SIGNATURE_TWO --owner ${WALLET}1-multisig --gas-payer $WALLET --memo $MEMO
```

check that the threshold has been updated correctly by running:

```bash
namadac query-account --owner ${WALLET}1-multisig
```

changing the public keys of a multisig account:

```bash
namadac update-account --address ${WALLET}1-multisig --public-keys ${WALLET}2,${WALLET}3,${WALLET}4 --signing-keys $WALLET,${WALLET}1 --memo $MEMO
```

initialize an established account:

```bash
namadac init-account --alias ${WALLET}1-multisig --public-keys ${WALLET}2,${WALLET}3,${WALLET}4  --signing-keys $WALLET,${WALLET}1  --threshold 1 --memo $MEMO
```
