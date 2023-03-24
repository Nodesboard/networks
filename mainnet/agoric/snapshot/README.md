## Instructions

### Stop the service and reset the data

```bash
sudo systemctl stop agd
cp $HOME/.agoric/data/priv_validator_state.json $HOME/.agoric/priv_validator_state.json.backup
rm -rf $HOME/.agoric/data
```

### Download latest snapshot

```bash
curl -L https://snapshots.kjnodes.com/agoric/snapshot_latest.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.agoric
mv $HOME/.agoric/priv_validator_state.json.backup $HOME/.agoric/data/priv_validator_state.json
```

### Restart the service and check the log

```bash
sudo systemctl start agd && sudo journalctl -u agd -f --no-hostname -o cat
```
