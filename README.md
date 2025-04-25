# toys

Standalone repo for https://github.com/project-chip/connectedhomeip/tree/master/examples/chef

## Compile

1. `cd` into `connectedhomeip` and setup build environment following https://github.com/project-chip/connectedhomeip/blob/4865e5e689807e500bde212cceaf36e9524b6dde/docs/guides/BUILDING.md#building-matter
2. Run commands to set up venv -
```
source scripts/bootstrap.sh
source scripts/activate.sh
```
3. In the same terminal session, build the chef app. E.g. -
```
cd ../chef
./chef.py -br -d rootnode_airpurifier_73a6fe2651 -t linux
```

