# 🔨 Validator Operations

check sync status and node info:

```bash
curl http://127.0.0.1:26657/status | jq
```

check balance:

```bash
namadac balance --owner $ALIAS
```

check keys:

```bash
namadaw list
```

find your validator address:

```bash
namadac find-validator --tm-address=$(curl -s localhost:26657/status | jq -r .result.validator_info.address) --node localhost:26657
```

stake funds:

```bash
namadac bond --source $WALLET --validator $VALIDATOR_ADDRESS --amount 10 --memo $MEMO
```

self-bonding:

```bash
namadac bond --validator $VALIDATOR_ADDRESS --amount 10 --memo $MEMO
```

check your validator bond status:

```bash
namadac bonds --validator $VALIDATOR_ADDRESS
```

check your user bonds:

```bash
namadac bonds --owner $WALLET
```

check all bonded nodes:

```bash
namadac bonded-stake
```

find all the slashes:

```bash
namadac slashes
```

non-self unbonding (validator alias can be used instead of address):

```bash
namadac unbond --source $WALLET --validator $VALIDATOR_ADDRESS --amount 1.5 --memo $MEMO
```

self-unbonding:

```bash
namadac unbond --validator $VALIDATOR_ADDRESS --amount 1.5 --memo $MEMO
```

withdrawing unbonded tokens (available 6 epochs after unbonding):

```bash
namadac withdraw --source $WALLET --validator $VALIDATOR_ADDRESS --memo $MEMO
```

find your validator status:

```bash
namadac validator-state --validator $VALIDATOR_ADDRESS
```

check epoch:

```bash
namada client epoch
```

unjail, you need to wait 2 epochs:

```bash
namada client unjail-validator --validator $VALIDATOR_ADDRESS --node http://127.0.0.1:26657 --memo $MEMO
```

deactivate validator:

```bash
namadac deactivate-validator --validator $VALIDATOR_ADDRESS --memo $MEMO
```

reactivate validator:

```bash
namadac reactivate-validator --validator $VALIDATOR_ADDRESS --memo $MEMO
```

Change consensus key:

```bash
namadac change-consensus-key --validator $VALIDATOR_ADDRESS --memo $MEMO --signing-keys $WALLET --node http://127.0.0.1:26657
```

Generate priv\_validator\_key:

```bash
namadaw convert --alias <consensus_key_name>
```

change validator commission rate:

```bash
namadac change-commission-rate --validator $VALIDATOR_ADDRESS --commission-rate <commission-rate> --memo $MEMO
```

change validator metadata:

```bash
namadac change-metadata --validator $VALIDATOR_ADDRESS --memo $MEMO
```
