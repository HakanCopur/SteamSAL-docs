# Installation

This guide explains how to install and enable **SteamSAL** in your Unreal Engine project **from source**.  

If you prefer, you can skip the source installation and **directly install the plugin from the Epic Fab Marketplace**, then simply enable it in your project.  

---

## Requirements

- **Unreal Engine**: 5.4 (tested) – should also work on UE 5.0+  
- **Steamworks SDK**: v1.57 (or compatible version bundled with the OnlineSubsystemSteam)  
- **Platform**: Windows (64-bit). Linux/Mac support planned but not tested.  
- **Online Subsystem**: `OnlineSubsystemSteam` must be enabled  

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
Edit (or create) `Config/DefaultEngine.ini` in your project folder and add:  

```ini
[OnlineSubsystem]
DefaultPlatformService=Steam

[OnlineSubsystemSteam]
bEnabled=true
SteamDevAppId=480    ; Replace with your own App ID
```

> ⚠️ App ID `480` is Valve’s *Spacewar* test ID. Use it only for local testing.  

### 4. Rebuild the Project
- **C++ projects**: Regenerate project files and build.  
- **Blueprint-only projects**: Unreal will automatically compile the plugin when the editor starts.  

---

## Verification

To confirm SteamSAL is working:  

1. Launch the game **through Steam** (not directly from the editor).  
2. In the editor, add the **Is Steam Available** node.  
3. If Steam initializes correctly, it should return `True`.  

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
