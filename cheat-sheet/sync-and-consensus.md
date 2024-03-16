# 🔨 Sync and Consensus

check logs:

```bash
sudo journalctl -u namadad -f
```

check sync status and node info:

```bash
curl http://127.0.0.1:26657/status | jq
```

check consensus state:

```bash
curl -s localhost:26657/consensus_state | jq .result.round_state.height_vote_set[0].prevotes_bit_array
```

check consensus state:

```bash
curl -s localhost:26657/consensus_state | jq .result.round_state.height_vote_set[-2].prevotes_bit_array
```

full consensus state:

```bash
curl -s localhost:12657/dump_consensus_state
```

your validator votes (prevote):

```bash
curl -s http://localhost:26657/dump_consensus_state | jq '.result.round_state.votes[0].prevotes' | grep $(curl -s http://localhost:26657/status | jq -r '.result.validator_info.address[:12]')
```
