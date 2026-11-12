# QuickMark Forever

> [!NOTE]
> **QuickMark Forever** is a continuation of [QuickMark](https://github.com/stphung/quickmark) by [**stphung**](https://github.com/stphung).
>
> Originally developed to restore QuickMark functionality for **World of Warcraft Forever (Interface 16001)**, the addon has since been confirmed to work with **WoW Retail (Midnight), WoW Classic, WoW Classic: Mists of Pandaria, and WoW Burning Crusade Anniversary**.
>
> QuickMark Forever restores click-to-mark functionality using secure raid target actions instead of direct `SetRaidTarget()` calls.

A lightweight World of Warcraft addon that provides a convenient, customizable and draggable interface for quickly marking targets with raid icons.

## Features

- **Quick Access Bar**: Floating bar with all 8 raid target icons (Star, Circle, Diamond, Triangle, Moon, Square, Cross, Skull)
- **One-Click Marking**: Click an icon to mark your current target using secure raid target actions, including during combat
- **Invert Marker Order**: Reverse the order of raid icons using `/qm inv` or the settings panel
- **Flexible Layout**: Toggle between horizontal and vertical orientations
- **Fully Customizable**:
  - Adjustable scale (10%–500%)
  - Multiple border styles (Classic, Slick, Wood, Hefty, Graphite, or None)
  - Adjustable background opacity (0%–100%)
  - Mouseover drag handle for easy repositioning when unlocked
  - Lock/unlock to prevent accidental movement
  - Show/hide as needed
- **Position Memory**: Remembers your bar position per character
- **Blizzard Settings Integration**: Full settings panel accessible via the ESC menu
- **Multi-Client Compatibility**: Works with multiple WoW versions using the same addon codebase

## Installation

### Manual Installation

1. Download the latest release from GitHub.
2. Extract the archive.
3. Copy the addon files into a folder named `QuickMarkForever` inside the `Interface/AddOns/` directory of your WoW installation.
4. Restart World of Warcraft or type `/reload` in-game.

## Usage

### Slash Commands

QuickMark Forever supports the following slash commands (use `/qm` or `/quickmark`):

```
/qm                  - Open settings panel
/qm lock (or l)      - Lock the bar in place
/qm unlock (or u)    - Unlock the bar for repositioning
/qm show (or s)      - Show the bar
/qm hide (or h)      - Hide the bar
/qm toggle (or t)    - Toggle visibility
/qm flip (or f)      - Flip between horizontal and vertical layouts
/qm horizontal (hor) - Set horizontal layout
/qm vertical (vert)  - Set vertical layout
/qm inv              - Invert raid marker order
```

### Marker Order

**Default:**

Star → Circle → Diamond → Triangle → Moon → Square → Cross → Skull

**Inverted:**

Skull → Cross → Square → Moon → Triangle → Diamond → Circle → Star

Use `/qm inv` or the **Invert Marker Order** checkbox in the settings panel to switch between both orders.

The selected order is saved per character and restored after logging in.

### Settings Panel

Access the full settings panel via:

- Type `/qm` or `/quickmark`
- Press **ESC → Options → AddOns → QuickMark Forever**

Available settings:

- **Lock**: Prevent the bar from being moved
- **Hide**: Toggle visibility
- **Horizontal**: Switch between horizontal and vertical orientation
- **Invert Marker Order**: Reverse the order of raid target icons
- **Scale**: Adjust size from 10% to 500%
- **Border**: Choose from multiple border styles
- **Background Opacity**: Adjust background transparency from 0% to 100%

When the bar is unlocked, a mouseover drag handle allows repositioning even when the background is fully transparent or the border is disabled.

### Marking Targets

1. Select a target.
2. Click any raid icon on the QuickMark Forever bar.
3. The selected raid marker is applied to your target.

Raid markers are applied using secure WoW actions, allowing marking during combat where permitted by the game.

**Note:** Clicking the same icon again does not currently remove the marker.

## Development

### Compatibility

QuickMark Forever was originally developed for **World of Warcraft Forever** but has since been expanded to support additional WoW clients.

**Tested and supported:**

| WoW Version | Interface | Status |
|---|---|---|
| WoW Retail (Midnight 12.x) | `120105` | Tested |
| WoW Classic (including Hardcore) | `11509` | Tested |
| WoW Classic: Mists of Pandaria | `50504` | Tested |
| WoW Burning Crusade Anniversary | `20506` | Tested |
| WoW Forever | `16001` | Tested |

**Potential compatibility (not tested):**

| WoW Version | Interface | Status |
|---|---|---|
| WoW Titan Reforged | `38002` | Untested – may work |

The addon uses a shared Lua codebase across supported clients.

Compatibility with Titan Reforged is considered possible due to the use of native WoW APIs and secure raid target actions, but has **not been verified in-game**.

### Changes from Original QuickMark

- Originally adapted QuickMark for WoW Forever (Interface 16001)
- Expanded compatibility to WoW Retail, Classic, Mists of Pandaria Classic and Burning Crusade Anniversary
- Replaced direct `SetRaidTarget()` calls with secure raid target buttons using `SecureActionButtonTemplate`
- Added `/qm inv` to reverse the raid marker order
- Added an **Invert Marker Order** checkbox to the settings panel
- Added adjustable background opacity (0%–100%)
- Added a mouseover drag handle for easier repositioning
- Preserved the original interface, customization options and settings

### Project Structure

```
quickmarkforever/
├── QuickMarkForever.lua       # Main addon code
├── QuickMarkForever.toc       # Addon metadata
├── LICENSE.txt                # Apache 2.0 License
├── README.md                  # This file
└── .gitignore                 # Git ignore rules
```

### Dependencies

None. QuickMark Forever uses only native WoW APIs with no external libraries.

### Building

No build process is required. The addon is ready to use as-is. Simply copy the addon files into your AddOns directory inside a folder named `QuickMarkForever`.

### Contributing

Contributions, bug reports and suggestions are welcome.

When contributing:

1. Test changes in-game using `/reload`.
2. Check for Lua errors using `/console scriptErrors 1`.
3. Follow the existing code style and patterns.
4. Ensure settings persist across reloads and game restarts.

### WoW API Reference

When working with World of Warcraft API functions, refer to:

- **Primary**: https://warcraft.wiki.gg/wiki/World_of_Warcraft_API
- **Legacy**: https://wowpedia.fandom.com/wiki/World_of_Warcraft_API

## License

QuickMark Forever is based on QuickMark by **stphung** and is distributed under the **Apache License 2.0**.

See [LICENSE.txt](LICENSE.txt) for the full license text.

Original copyright and license notices are retained.

## Credits

**Original Addon:** [QuickMark by stphung](https://github.com/stphung/quickmark)

Special thanks to **stphung** for creating the original QuickMark addon and for all the work put into its development.

If stphung ever wishes to resume development of QuickMark, he is welcome to contact me. I'd be happy to discuss the future of the project, including the possibility of merging improvements back into the original addon.

This project is not affiliated with or endorsed by the original author or Blizzard Entertainment.
