# rdx_society

Society management for RDX. Adds employee management (hire, fire, promote / demote, change salary), society bank accounts and money washing. It's crucial that this script gets started before all resources that utilize societies do, or else many things will go wrong.
- [RDX Framework Discord](https://discord.gg/VkhUUGHpNs)
## Requirements
- [cron](https://github.com/RalivTV/cron)
- [rdx_addonaccount](https://github.com/Redm-Extended-PT/rdx_addonaccount)

## Download & Installation

- Download https://github.com/Redm-Extended-PT/rdx_society
- Put it in the `[rdx]` directory

## Installation
- Import `rdx_society.sql` in your database
- Add this in your `server.cfg`:

```
ensure rdx_society
```

## Explanation
RDX Society works with addon accounts named 'society_xxx', for example 'society_taxi' or 'society_realestateagent'. If you job grade is 'boss' the society money will be displayed in your hud.

## Usage
```lua
local society = 'taxi'
local amount  = 100

TriggerServerEvent('rdx_society:withdrawMoney', society, amount)
TriggerServerEvent('rdx_society:depositMoney', society, amount)
TriggerServerEvent('rdx_society:washMoney', society, amount)


TriggerEvent('rdx_society:openBossMenu', society, function (data, menu)
	menu.close()
end, {wash = false}) -- set custom options, e.g disable washing
```
