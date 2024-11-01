
# fourtwenty_fishing Documentation

## Changelog
### Version 1.0.0
- Initial release of the FourTwenty Fishing System.
- Implemented the fish market with dynamic pricing, selling functionality, and user interface.
- Added animations and localization for enhanced user experience.

## Common Errors
### 1. Error loading market prices
- **Problem**: Market prices are not displayed correctly.
- **Solution**: Ensure that the server is properly configured and the API requests return valid data.

### 2. Selling fish fails
- **Problem**: The "sell all fish" button is not functioning.
- **Solution**: Check that the player has fish in their inventory and the UI has been properly updated.

### 3. Animation issues
- **Problem**: Fishing animations do not play.
- **Solution**: Verify that all required animation dictionaries are loaded correctly. Ensure that the correct animation names are referenced in the code.

## Configuration
To customize the FourTwenty Fishing System, you can modify the following parameters in the `config.lua` file. Each parameter is essential for the proper functioning of the script and allows you to tailor the fishing experience to your server's needs.

### Fishing Zones
Define the coordinates and radius for the fishing zones where players can fish.
```lua
Config.FishingZones = {
    {
        name = "Fishing Zone 1",
        coords = vector3(-2242.56, 4260.54, 47.10), -- Example coordinates
        radius = 100.0, -- Radius in meters
        blipColor = 2, -- Color ID for the blip on the map
        blipAlpha = 128 -- Transparency of the blip
    },
    {
        name = "Fishing Zone 2",
        coords = vector3(-2055.91, 4043.12, 35.82),
        radius = 150.0,
        blipColor = 3,
        blipAlpha = 128
    }
}
```

### Fishing Settings
Adjust settings related to the fishing mechanics and key bindings.
```lua
Config.FishingSettings = {
    startKey = 38, -- Default key to start fishing (E)
    cancelKey = 44, -- Default key to cancel fishing (Q)
    autoFishing = false, -- Enable or disable auto fishing
    autoCooldown = 10000, -- Cooldown time in milliseconds for auto fishing
    waitingAnimDict = "amb@world_human_stand_fishing@idle_a", -- Animation dictionary for waiting
    waitingAnim = "idle_c" -- Animation name for waiting
}
```

### Fish Prices
Set the base prices for different types of fish in the market.
```lua
Config.FishPrices = {
    ["bass"] = 20, -- Price for bass fish
    ["salmon"] = 30, -- Price for salmon fish
    ["trout"] = 15 -- Price for trout fish
}
```

### NPC Settings
Customize the settings for the NPC that buys fish at the market.
```lua
Config.SellPoint = {
    coords = vector3(-2006.83, 4000.17, 35.60), -- Coordinates of the NPC
    npcModel = "a_m_m_farmer_01", -- Model name for the NPC
    heading = 180.0 -- Direction the NPC is facing
}
```

### Blip Configuration
Define how the blips for fishing zones and the fish market are displayed on the map.
```lua
Config.Blips = {
    FishMarket = {
        sprite = 68, -- Blip sprite ID for the fish market
        display = 4, -- Display type (e.g., 4 for map blip)
        scale = 0.8, -- Scale of the blip
        color = 2 -- Color of the blip (e.g., 2 for green)
    },
    FishingSpot = {
        sprite = 68,
        display = 4,
        scale = 0.7,
        color = 3 -- Color of fishing spots (e.g., 3 for blue)
    }
}
```

### Example of a Complete Configuration
Here’s an example of how the complete `config.lua` file might look with all these settings:
```lua
Config = {}

Config.FishingZones = {
    {
        name = "Fishing Zone 1",
        coords = vector3(-2242.56, 4260.54, 47.10),
        radius = 100.0,
        blipColor = 2,
        blipAlpha = 128
    },
    {
        name = "Fishing Zone 2",
        coords = vector3(-2055.91, 4043.12, 35.82),
        radius = 150.0,
        blipColor = 3,
        blipAlpha = 128
    }
}

Config.FishingSettings = {
    startKey = 38,
    cancelKey = 44,
    autoFishing = false,
    autoCooldown = 10000,
    waitingAnimDict = "amb@world_human_stand_fishing@idle_a",
    waitingAnim = "idle_c"
}

Config.FishPrices = {
    ["bass"] = 20,
    ["salmon"] = 30,
    ["trout"] = 15
}

Config.SellPoint = {
    coords = vector3(-2006.83, 4000.17, 35.60),
    npcModel = "a_m_m_farmer_01",
    heading = 180.0
}

Config.Blips = {
    FishMarket = {
        sprite = 68,
        display = 4,
        scale = 0.8,
        color = 2
    },
    FishingSpot = {
        sprite = 68,
        display = 4,
        scale = 0.7,
        color = 3
    }
}
```

## Market UI
### Features:
1. **Dynamic Price Changes**: Prices of fish change at regular intervals, adding realism to the market.
2. **Inventory Management**: Users can view their current inventory and the total monetary value of their fish.
3. **Localized Interface**: The user interface supports multiple languages, adjusting based on player preferences.

### Usage Instructions:
1. Open the fish market interface in-game.
2. Review the available fish and their current prices.
3. Click the "Sell All Fish" button to sell your fish instantly.

## Fishing Mechanics
### Key Bindings
- **Start Fishing**: Press the configured key (default set in `config.lua`).
- **Cancel Fishing**: Press the cancel key to stop fishing if necessary.

### Fishing Process
1. **Find a Fishing Zone**: Players must be within designated fishing zones to start fishing.
2. **Fishing Rod Check**: Players need to have a fishing rod available that meets their level requirements.
3. **Animation Play**: Once fishing starts, an animation will play, simulating the fishing activity.
4. **Catch Attempt**: After a random duration, the system will attempt to catch a fish. Success or failure will trigger respective animations and notifications.

### Leveling Up
- Players can level up their fishing skills, allowing access to better rods and increasing their chances of success while fishing.

## Blips and NPCs
- The fish market is represented on the map with a blip, allowing players to locate it easily.
- An NPC at the fish market handles fish purchases. The NPC model and location can be configured in the `config.lua` file.
- Players can approach the NPC to sell their caught fish and receive payments in return.

## Usage Example
### 1. Ensure you are equipped with a fishing rod.
### 2. Navigate to a designated fishing zone.
### 3. Press the start fishing key to begin the fishing animation.
### 4. Wait for a catch attempt; if successful, a notification will appear, and you can sell your fish at the market.

---
