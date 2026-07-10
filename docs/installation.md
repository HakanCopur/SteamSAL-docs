# Installation

This guide explains how to install and enable **SteamSAL** in your Unreal Engine project **from source**.  

If you prefer, you can skip the source installation and **directly install the plugin from the Epic Fab Marketplace**, then simply enable it in your project.  

---

## Requirements

- **Unreal Engine**: Tested and fully compatible with **5.0, 5.1, 5.2, 5.3, 5.4, 5.5, 5.6, 5.7 and 5.8**  
- **Steamworks SDK**: v1.57 (or compatible version bundled with the OnlineSubsystemSteam)  
- **Platform**: Windows (64-bit). Linux/Mac support planned but not tested.  
- **Online Subsystem**: `OnlineSubsystemSteam` must be enabled  

> ✅ The plugin has been verified to work across all Unreal Engine 5 versions listed above.

---

## Installation Steps

### 1. Download the Plugin
- Get the latest release from GitHub:  
  [https://github.com/HakanCopur/steam-achievements-leaderboards](https://github.com/HakanCopur/steam-achievements-leaderboards)  

- Or clone the repository into your project’s `Plugins` folder:
  ```bash
  git clone https://github.com/HakanCopur/steam-achievements-leaderboards.git Plugins/SteamSAL
  ```

### 2. Enable the Plugin
1. Open your Unreal Engine project.  
2. Go to **Edit → Plugins**.  
3. Find **SteamSAL – Steam Achievements & Leaderboards** under the “Installed” category.  
4. Enable it and restart the editor.  

### 3. Configure Steam Subsystem
Follow the official Unreal Engine guide to properly set up the **Online Subsystem Steam** for your engine version:  
👉 [Epic Games Documentation – Online Subsystem Steam Interface](https://dev.epicgames.com/documentation/en-us/unreal-engine/online-subsystem-steam-interface-in-unreal-engine)

> ⚠️ Make sure you configure your App ID and enable the subsystem correctly for Steam to initialize in your project.

### 4. Rebuild the Project
- **C++ projects**: Regenerate project files and build.  
- **Blueprint-only projects**: Unreal will automatically compile the plugin when the editor starts.  

---

## Verification

To confirm SteamSAL is working correctly:  

1. Launch your game **as a Standalone Game** or **as a Packaged Build**.  
2. Steam must be running in the background and your Steam account logged in.  
3. In the editor, add the **Is Steam Available** node.  
4. If Steam initializes correctly, it should return `True`.  

> ⚠️ Steam **will not initialize** when running in **Play-In-Editor (PIE)** mode.  
> To see the Steam overlay and use Steam features, always run in **Standalone** or **Packaged Build** mode.

---

## Next Steps

Once installed, you can begin using:  

- [Achievements](achievement/setachievement.md) – Unlock, query, and show progress  
- [Leaderboards](leaderboard/create.md) – Upload and download scores  
- [Stats](achievement/storestats.md) – Read, write, and sync player stats  

---

## Support

If you encounter issues:  

- Open a ticket in [GitHub Issues](https://github.com/HakanCopur/steam-achievements-leaderboards/issues)  
- Contact me directly: **dev@hakancopur.com**
