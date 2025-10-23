# Roblox Hide Players Toggle Script

A simple yet powerful LocalScript for Roblox that allows players to toggle the visibility of other players in the game.

## Author
**ItoRenz00**

## Features

- ✅ **Toggle Visibility**: Hide/show all other players with a single button click
- ✅ **Complete Hiding**: Hides character models, GUIs, nametags, health bars, and text elements
- ✅ **Cross-Platform**: Fully supports both Mobile and PC platforms
- ✅ **Transparency Preservation**: Saves and restores original transparency values
- ✅ **Auto-Detection**: Automatically handles new players joining the game
- ✅ **GUI Monitoring**: Detects and hides newly added GUI elements
- ✅ **Smooth Animation**: Button click animation for better user feedback
- ✅ **Optimized Performance**: Uses pcall for error handling and task scheduling

## Installation

1. Open Roblox Studio
2. Navigate to `StarterPlayer` > `StarterPlayerScripts`
3. Create a new `LocalScript`
4. Copy and paste the script code
5. Save and test in Play mode

## Usage

Once the script is running:

- A toggle button will appear on the left side of the screen
- **Initial State**: "👁️ Show" (gray button) - All players are visible
- **Click to Hide**: Button changes to "👁️ Hide" (red button) - All other players are hidden
- **Click Again**: Returns to "👁️ Show" state - All players become visible again

## How It Works

The script operates by:

1. **Character Hiding**: Sets transparency to 1 for all BaseParts, Decals, and Textures
2. **GUI Hiding**: Disables BillboardGui and SurfaceGui elements
3. **Nametag Hiding**: Sets Humanoid display distances to 0
4. **State Management**: Tracks hidden players and their original properties
5. **Auto-Monitoring**: Watches for new players and GUI elements added during gameplay

## Configuration

You can customize the UI by modifying the `UI_CONFIG` table:

```lua
local UI_CONFIG = {
    MOBILE_SIZE = UDim2.new(0, 80, 0, 80),      -- Button size on mobile
    PC_SIZE = UDim2.new(0, 60, 0, 60),          -- Button size on PC
    MOBILE_TEXT_SIZE = 14,                       -- Text size on mobile
    PC_TEXT_SIZE = 12,                           -- Text size on PC
    CORNER_RADIUS = 12,                          -- Button corner radius
    COLOR_HIDDEN = Color3.fromRGB(220, 50, 50), -- Button color when hiding
    COLOR_SHOWN = Color3.fromRGB(50, 50, 50)    -- Button color when showing
}
```

## Compatibility

- **Roblox Platform**: Fully compatible with current Roblox engine
- **Device Support**: Mobile (Touch) and PC (Mouse & Keyboard)
- **Script Type**: LocalScript (must be placed in StarterPlayerScripts)

## Technical Details

### Services Used
- `Players` - Player management
- `UserInputService` - Platform detection
- `RunService` - Game loop operations (referenced but not actively used)

### Key Functions
- `hideCharacter()` - Hides a player's character
- `showCharacter()` - Shows a player's character
- `hideCharacterGuis()` - Hides all GUI elements on a character
- `showCharacterGuis()` - Restores all GUI elements on a character
- `setupCharacterMonitoring()` - Monitors for new GUI additions
- `toggleAllPlayers()` - Toggles visibility for all players

## Known Limitations

- Only affects other players (not the local player)
- Requires LocalScript permissions
- GUI state is session-based (resets on script reload)

## Troubleshooting

**Button not appearing?**
- Ensure script is in `StarterPlayerScripts`
- Check if it's a `LocalScript` (not a regular Script)

**Players not hiding?**
- Verify other scripts aren't overriding transparency
- Check console for error messages

**Works on PC but not Mobile?**
- The script auto-detects platform - this shouldn't happen
- Check UserInputService permissions

## Contributing

Feel free to fork, modify, and improve this script! If you make enhancements, please share them with the community.

## License

This script is provided as-is for educational and personal use in Roblox games.

## Contact

**Author**: ItoRenz00

---

**Version**: 1.0.0  
**Last Updated**: 2025  
**Status**: Stable ✅
