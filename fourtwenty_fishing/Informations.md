# Market UI

- The fish market displays current prices, available fish, and the total value of the inventory.
- Price updates are dynamically fetched from the server and displayed in real time.
- Players can sell all their fish with a single button click.

### Features:
1. **Dynamic Price Changes**: Prices of fish change at regular intervals, adding realism to the market.
2. **Inventory Management**: Users can view their current inventory and the total monetary value of their fish.
3. **Localized Interface**: The user interface supports multiple languages, adjusting based on player preferences.

### Usage Instructions:
1. Open the fish market interface in-game.
2. Review the available fish and their current prices.
3. Click the "Sell All Fish" button to sell your fish instantly.


# Fishing Mechanics

## Key Bindings
- **Start Fishing**: Press the configured key (default set in `config.lua`).
- **Cancel Fishing**: Press the cancel key to stop fishing if necessary.

## Fishing Process
1. **Find a Fishing Zone**: Players must be within designated fishing zones to start fishing.
2. **Fishing Rod Check**: Players need to have a fishing rod available that meets their level requirements.
3. **Animation Play**: Once fishing starts, an animation will play, simulating the fishing activity.
4. **Catch Attempt**: After a random duration, the system will attempt to catch a fish. Success or failure will trigger respective animations and notifications.

## Leveling Up
- Players can level up their fishing skills, allowing access to better rods and increasing their chances of success while fishing.


# Blips and NPCs

- The fish market is represented on the map with a blip, allowing players to locate it easily.
- An NPC at the fish market handles fish purchases. The NPC model and location can be configured in the `config.lua` file.
- Players can approach the NPC to sell their caught fish and receive payments in return.


# Usage Example

1. Ensure you are equipped with a fishing rod.
2. Navigate to a designated fishing zone.
3. Press the start fishing key to begin the fishing animation.
4. Wait for a catch attempt; if successful, a notification will appear, and you can sell your fish at the market.
