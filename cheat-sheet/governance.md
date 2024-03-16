# 🔨 Governance

all proposals list:

```bash
namadac query-proposal
```

edit proposal:

```bash
namadac query-proposal --proposal-id <PROPOSAL_ID>
```

save wallet address:

```bash
WALLET_ADDRESS=$(namadaw find --alias $WALLET | grep "Implicit" | awk '{print $3}')
```

import the variable into system:

```bash
echo "export WALLET_ADDRESS="$WALLET_ADDRESS"" >> $HOME/.bash_profile
source $HOME/.bash_profile
```

vote:

```bash
namadac vote-proposal --proposal-id <proposal-id> --vote yay --address $WALLET_ADDRESS --signing-keys $WALLET --memo $MEMO
```

Check your vote:

```bash
namadac query-proposal-votes --proposal-id <proposal_id> --voter $WALLET_ADDRESS
```
