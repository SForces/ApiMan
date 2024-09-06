# ApiMan Plugin
![header_img](https://i.imgur.com/gVIEs4Q.png)
## Introduction
*Eğer türkseniz [buraya](https://forcess-compani.gitbook.io/apiman-plugin).*
ApiMan is a powerful Minecraft plugin designed for integrating with external APIs. It enables seamless command handling, API communication, and JSON data processing within your Minecraft server.

## Installation

1. **Download the Plugin**: Get the latest version of ApiMan from the [GitHub releases page](https://github.com/SForces/ApiMan/releases).

2. **Place the Plugin in Your Server**:
   - Move the downloaded `.jar` file into the `plugins` directory of your Minecraft server.

3. **Restart Your Server**: Restart your Minecraft server to load the plugin.

4. **Verify Installation**: Check the server console for confirmation that ApiMan has been loaded successfully.

## Initial Setup

Upon first startup, ApiMan will generate a `config.yml` file in the `plugins/ApiMan` directory. This file includes a `private-key` that you will need to configure.

### Setting Up the Private Key

1. **Locate the `config.yml` File**:
   - Navigate to `plugins/ApiMan/config.yml`.

2. **Configure the Private Key**:
   - Open `config.yml` in a text editor.
   - Find the `private-key` field and set it to the value provided upon plugin startup or from your configuration.

   ```yaml
   private-key: "YOUR_PRIVATE_KEY_HERE"

### Config File Breakdown

#### End-User License Agreement (EULA)
- **`# End-User License Agreement (EULA)`**: This section informs users that agreeing to the EULA is required to use the plugin. It provides links to the EULA in English and Turkish.
  - **English EULA**: [Github](https://github.com/SForces/ApiMan/blob/main/eula_en.md), [Github-Raw](https://raw.githubusercontent.com/SForces/ApiMan/main/eula_en.md)
  - **Turkish EULA**: [Github](https://github.com/SForces/ApiMan/blob/main/eula_tr.md), [Github-Raw](https://raw.githubusercontent.com/SForces/ApiMan/main/eula_tr.md)

#### System Settings
- **`private-key`**: A crucial security key that distinguishes your server and enables it to interact with ApiMan servers. This key should be kept confidential.

- **`language`**: Specifies the language for plugin messages. Available options are `'en'` (English) and `'tr'` (Turkish).
  - **Example**: `'en'`

- **`data-send-interval`**: The interval, in seconds, at which the plugin sends server data to ApiMan servers. A lower value may impact server performance, so it’s recommended to set it to 30 seconds or more.
  - **Example**: `30`

#### Servers Settings
- **`use-default-plugin-servers`**: Indicates whether to use ApiMan's default servers for storing server data. This setting should generally remain `true` unless custom server configurations are provided in future updates.
  - **Example**: `true`

- **`# Custom server configurations`**: Future updates will allow for custom server configurations. For now, keep this setting as `true` to ensure plugin functionality.

#### 3rd-Party Settings
- **`enable-3rd-party`**: If set to `true`, the plugin will interact with third-party services like Discord. If disabled, the plugin will not handle any external requests or commands.
  - **Example**: `true`

  - **`discord`**: Contains settings related to Discord integration.
    - **`chat-to-discord`**: Configures whether in-game chat messages are sent to Discord via webhooks.
      - **`enabled`**: Whether the feature is active.
      - **`webhook`**: The Discord webhook URL used for sending chat messages.
        - **Example**: `'https://discord.com/api/webhooks/.../...'`

    - **`command-to-discord`**: Configures whether server commands are sent to Discord via webhooks.
      - **`enabled`**: Whether the feature is active.
      - **`webhook`**: The Discord webhook URL used for sending command messages.
        - **Example**: `'https://discord.com/api/webhooks/.../...'`

    - **`discord-to-in-game-commands`**: Allows Discord to send commands directly to the server. This feature is risky and should be used with caution.
      - **`enabled`**: Whether the feature is active.
      - **Warnings and Recommendations**: 
        - Only enable if necessary and ensure that your Discord bot and webhook are secured.
        - Limit access to trusted individuals and apply security measures to prevent unauthorized access.
        - ApiMan is not liable for data loss due to misuse.

#### Resource Pack Settings
- **`resourcepack`**: Configurations related to enforcing and managing resource packs for the server.
  - **`enforce`**: Whether players are forced to use the specified resource pack.
    - **Example**: `false`
    
  - **`URL`**: The URL where the resource pack can be downloaded. Ensure the URL is valid.
    - **Example**: `""` (empty if not used)
    
  - **`wait-ticks`**: Number of ticks the server waits before showing the resource pack loading screen to the player. Adjust this if the loading screen appears briefly.
    - **Example**: `50`

## JSON Data Structure

ApiMan handles JSON data to communicate with external APIs and manage in-game data. Below is a breakdown of the JSON data structure used by ApiMan:

### Example JSON Data

```json
{
    "onlinePlayers": [
        "Forcess0"
    ],
    "active": 1,
    "opPlayers": [
        "Forcess0"
    ],
    "PlayersData": {
        //Full player list
        "Notch":{},
        "Forcess0": {
            "name": "Forcess0",
            "uuid": "4fdc3c45-3bd0-3b7d-96d6-35174688d372",
            "location": {
                "x": -280.30000001192093,
                "y": 76.23152379758702,
                "z": -133.1072178900286,
                "world": "world",
                "biome": "FOREST",
                "facing": {
                    "direction": "south",
                    "yaw": -23.015625,
                    "pitch": 29.6417
                }
            },
            "health": 20.0,
            "foodLevel": 20,
            "saturation": 5.0,
            "op": true,
            "playerState": {
                "sprinting": false,
                "sneaking": false,
                "swimming": false,
                "sleeping": false,
                "flying": false,
                "invisible": false,
                "dead": false,
                "gliding": false
            },
            "inventory": {
                "mainHand": {
                    "type": "GOLDEN_APPLE",
                    "amount": 17,
                    "durability": 0,
                    "enchantments": {}
                },
                "offHand": {
                    "type": "SHIELD",
                    "amount": 1,
                    "durability": 0,
                    "enchantments": {}
                },
                "helmet": {
                    "type": "DIAMOND_HELMET",
                    "amount": 1,
                    "durability": 0,
                    "enchantments": {}
                },
                "chestplate": {
                    "type": "NETHERITE_CHESTPLATE",
                    "amount": 1,
                    "durability": 0,
                    "enchantments": {}
                },
                "leggings": {
                    "type": "NETHERITE_LEGGINGS",
                    "amount": 1,
                    "durability": 0,
                    "enchantments": {}
                },
                "boots": {
                    "type": "NETHERITE_BOOTS",
                    "amount": 1,
                    "durability": 0,
                    "enchantments": {}
                },
                "contents": [
                    {
                        "type": "GOLDEN_APPLE",
                        "amount": 10,
                        "durability": 0,
                        "enchantments": {}
                    },
                    // Player's full inventory will be listed here
                ]
            }
        }
    }
}
```
### JSON Structure Breakdown

- **`onlinePlayers`**: A list of currently online players.
  - **Example**: `["Forcess0"]`
  
- **`active`**: Indicates if the server or plugin is currently active.
  - **Example**: `1` (Active), `0` (Inactive)
  
- **`opPlayers`**: List of operators or players with special permissions.
  - **Example**: `["Forcess0"]`
  
- **`PlayersData`**: Contains detailed information for each player.
  - **Key**: Player's name or UUID.
  - **Value**: An object containing player-specific data.

    - **`name`**: The player's name.
      - **Example**: `"Forcess0"`
      
    - **`uuid`**: The player's unique identifier.
      - **Example**: `"4fdc3c45-3bd0-3b7d-96d6-35174688d372"`
      
    - **`location`**: The player's current location in the world.
      - **`x`**: X-coordinate.
      - **`y`**: Y-coordinate.
      - **`z`**: Z-coordinate.
      - **`world`**: The world name.
      - **`biome`**: The biome name.
      - **`facing`**: The direction the player is facing.
        - **`direction`**: The direction (e.g., "south").
        - **`yaw`**: The yaw rotation.
        - **`pitch`**: The pitch rotation.

    - **`health`**: The player's current health.
      - **Example**: `20.0`
      
    - **`foodLevel`**: The player's food level.
      - **Example**: `20`
      
    - **`saturation`**: The player's saturation level.
      - **Example**: `5.0`
      
    - **`op`**: Indicates if the player is an operator.
      - **Example**: `true`
      
    - **`playerState`**: The current state of the player.
      - **`sprinting`**: Whether the player is sprinting.
      - **`sneaking`**: Whether the player is sneaking.
      - **`swimming`**: Whether the player is swimming.
      - **`sleeping`**: Whether the player is sleeping.
      - **`flying`**: Whether the player is flying.
      - **`invisible`**: Whether the player is invisible.
      - **`dead`**: Whether the player is dead.
      - **`gliding`**: Whether the player is gliding.

    - **`inventory`**: The player's inventory.
      - **`mainHand`**: Item in the main hand.
      - **`offHand`**: Item in the off hand.
      - **`helmet`**: Helmet item.
      - **`chestplate`**: Chestplate item.
      - **`leggings`**: Leggings item.
      - **`boots`**: Boots item.
      - **`contents`**: Items in the player's inventory.
        - **`type`**: Item type (e.g., "GOLDEN_APPLE").
        - **`amount`**: Quantity of the item.
        - **`durability`**: Durability of the item.
        - **`enchantments`**: Enchantments applied to the item.
### Inventory Contents Breakdown
## Inventory contents listed 1 to 41<br>
![VSC_img](https://i.imgur.com/u97Eoqy.png)<br>
## And their match in game<br>
![MC_img](https://i.imgur.com/DRDXvcG.png)
<br>
- In this way you can see or check spesific slots in player's inventory.

# end
hope this documentation is enough for your problem.<br>
if its not, add me discord: `fforcess`
