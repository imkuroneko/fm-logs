# 🤓 FiveM Logger by Fivemerr

A logging resource for your FiveM server that logs directly to [Fivemerr's](https://fivemerr.com/) api. 

## Requirements

- FXServer With at least build: `5562`
- [screenshot-basic](https://github.com/citizenfx/screenshot-basic)

## Features

- Chat Logs
- Join Logs
- Spawn Logs (Based on specified framework)
- Leave Logs
- Damage Logs
- Death Logs
- Weapon Logs
- Resource Logs
- Explosion Logs
- TxAdmin Logs
- Screenshot Logs

## Custom Logging

You may use `fm-logs` to leverage custom reporting to Fivemerr by using the following export function:

```
-- Example of a createLog function
exports['fm-logs']:createLog({
    LogType = "Player", -- The log type, must be defined in Config.Logs
    Message = "Player action here", -- The message of the log
    Level = "info", -- The level of the log (can be filtered on Fivemerr) (info by default)
    Resource = "script-name", -- Resource where the log is coming from (If not provided, `fm-logs` will be set by default)
    Source = 1, -- Server id for player (Required for Player Attributes to be pulled)
    Metadata = {} -- Custom attributes to be added
})
```

The export can be used on both server and client sides.

## Note

This logger does not require a framework, however, if you use QBCore or ESX, you can set these in the config to display the player's character name in the logs on Fivemerr.

```
Framework = "qb", -- "qb" | "esx" | "standalone"
```

If you do not use a framework, simply set this to "standalone".