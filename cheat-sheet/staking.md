# 🔨 Staking

```
If you find this guide helpful, you can stake to our validator. 
We would really appreciate it! 🚀
```

add a variable with the validator address:

```bash
VAL_ADDRESS="tnam1q8vhe85yc5ttt7mveds58gyqzavfwnn9eqhfxpgc" # address of validator you want to stake to
```

export the variable:

```bash
echo "export VAL_ADDRESS="$VAL_ADDRESS"" >> $HOME/.bash_profile \
source $HOME/.bash_profile
```

delegate tokens:

```bash
namadac bond --source $WALLET --validator $VAL_ADDRESS --amount 500  --memo $MEMO
```

check your user bonds:

```bash
namadac bonds --owner $WALLET 
```

check all bonded nodes:

```bash
namadac bonded-stake 
```

add stake:

```bash
namadac bond --source $WALLET --validator $VAL_ADDRESS --amount 500  --memo $MEMO
```

unbond the tokens:

```bash
namadac unbond --source $WALLET --validator $VAL_ADDRESS --amount 15  --memo $MEMO
```

wait for 6 epochs, then check when the unbonded tokens can be withdrawed:

```bash
namadac bonds --owner $WALLET 
```

withdraw unbonded tokens:

```bash
namadac withdraw --source $WALLET --validator $VAL_ADDRESS  --memo $MEMO
```

redelegate:

```bash
namadac redelegate --owner $WALLET --source-validator $VAL_ADDRESS --destination-validator <destination-validator-address> --amount 10  --memo $MEMO
```

claim rewards:

```bash
namadac claim-rewards --source $WALLET --validator $VAL_ADDRESS  --memo $MEMO
```

query the pending reward tokens without claiming:

```bash
namadac rewards --source $WALLET --validator $VAL_ADDRESS 
```
