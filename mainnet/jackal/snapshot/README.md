## Instructions

### Stop the service and reset the data

```bash
sudo systemctl stop canined
cp $HOME/.canine/data/priv_validator_state.json $HOME/.canine/priv_validator_state.json.backup
rm -rf $HOME/.canine/data
```

### Download latest snapshot

```bash
curl -L https://ss.nodesboard.com/jackal/snapshot_latest.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.canine
mv $HOME/.canine/priv_validator_state.json.backup $HOME/.canine/data/priv_validator_state.json
```

### Restart the service and check the log

```bash
sudo systemctl start canined && sudo journalctl -u canined -f --no-hostname -o cat
```
