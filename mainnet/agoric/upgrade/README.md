## Download and build upgrade binaries

```bash
# Clone project repository
cd $HOME
rm -rf pismoC
git clone https://github.com/Agoric/agoric-sdk.git pismoC
cd pismoC
git checkout pismoC

# Install and build Agoric Javascript packages
yarn install && yarn build

# Install and build Agoric Cosmos SDK support
(cd packages/cosmic-swingset && make)

# Prepare binaries for Cosmovisor
mkdir -p $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-9/bin
ln -s $HOME/pismoC/packages/cosmic-swingset/bin/ag-chain-cosmos $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-9/bin/ag-chain-cosmos
ln -s $HOME/pismoC/packages/cosmic-swingset/bin/ag-nchainz $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-9/bin/ag-nchainz
cp golang/cosmos/build/agd $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-9/bin/
cp golang/cosmos/build/ag-cosmos-helper $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-9/bin/
```

*Thats it! Now when upgrade block height is reached, Cosmovisor will handle it automatically!*
