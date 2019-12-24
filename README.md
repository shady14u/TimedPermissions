**Timed Permissions** allows you to grant permissions or groups for a specific time.  

## Permissions

- `timedpermissions.use` -- Allows player to use most of the commands
- `timedpermissions.advanced` -- Allows player to use the `timedpermissions_resetaccess` & `timedpermissions_ensureaccess`.

## Commands

This plugin provides universal chat and console commands. When using a command in the chat, prefix it with a forward slash: `/`

- `revokeperm <player|steamid> <permission>` -- Revoke a timed permission from a player  
- `grantperm <player|steamid> <permission> <time>` -- Give a player a permission for a specific time  
- `removegroup <player|steamid> <group>` -- Remove a timed group from a player  
- `addgroup <player|steamid> <group> <time>` -- Add a player to a group for a specific time  
- `pinfo [player|steamid]` -- Show active timed permissions and groups of a player (**can be used by non-admins without specifiying a target player**)  

### Advanced Commands (require `timedpermissions.advanced` permission)
- `timedpermissions_resetaccess [yes]` -- Reset all access data stored in Timed Permissions and create a backup of that data. Needs to be confirmed by passing `yes` as parameter.  
- `timedpermissions_ensureaccess [yes]` -- Ensures every player has their groups and permissions assigned. Needs to be confirmed by passing `yes` as parameter.  

### Placeholders
These are placeholders used in the commands. They are to be replaced with a specific value when using a command.  
- `<player|steamid>` -- the name or Steam ID (64) of the player you're trying to target
- `[player|steamid]` -- **[optional]** the name or Steam ID (64) of the player you're trying to target
- `<permission>` -- the name of the permission you want to grant/revoke
- `<group>` -- the name of the group you want to *add the player to*/*remove the player from*
- `<time>` -- the duration of the permission/group formatted like '1d12h30m'  
Usage example: `/grantperm LaserHydra timedpermissions.use 30d` gives LaserHydra the permission `timedpermissions.use` for 30 days.  
  - d = days  
  - h = hours  
  - m = minutes  
- `[yes]` -- text 'yes' needs to be given to confirm action

## Localization

```json
{  
  "Invalid Time Format": "Invalid Time Format: Ex: 1d12h30m | d = days, h = hours, m = minutes",  
  "No Permission": "You don't have permission to use this command.",  
  "Player Has No Info": "There is no info about this player.",  
  "Player Info": "Info about {player}:  Groups: {groups}  Permissions: {permissions}"
}
```

## Configuration

```json
{  
  "Wipe Data on New Save (Limited to Certain Games)": false  
}
```

- `Wipe Data on New Save (Limited to Certain Games)' -- when set to `true`, automatically wipes the data