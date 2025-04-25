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
   * Only Linux is currently supported *
```
cd ../chef
./chef.py -br -d rootnode_airpurifier_73a6fe2651 -t linux
```
For the following error -
```
Error: <some_path>/src/app/zap-templates/zcl/zcl.json does not exists or is not a file.
```
Fix the path in the ZAP file
```
gedit chef/devices/<device_name>.zap
```
Change -
```
  "package": [
    {
      "pathRelativity": "relativeToZap",
      "path": "../../../src/app/zap-templates/zcl/zcl.json",
      "type": "zcl-properties",
      "category": "matter",
      "version": 1,
      "description": "Matter SDK ZCL data"
    },
    {
      "pathRelativity": "relativeToZap",
      "path": "../../../src/app/zap-templates/app-templates.json",
      "type": "gen-templates-json",
      "category": "matter",
      "version": "chip-v1"
    }
  ],
```

to -

```
  "package": [
    {
      "pathRelativity": "relativeToZap",
      "path": "../../connectedhomeip/src/app/zap-templates/zcl/zcl.json",
      "type": "zcl-properties",
      "category": "matter",
      "version": 1,
      "description": "Matter SDK ZCL data"
    },
    {
      "pathRelativity": "relativeToZap",
      "path": "../../connectedhomeip/src/app/zap-templates/app-templates.json",
      "type": "gen-templates-json",
      "category": "matter",
      "version": "chip-v1"
    }
  ],
```

