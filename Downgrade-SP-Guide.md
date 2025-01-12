# Garry's Mod RTX Manual Installation and Downgrade Guide

A comprehensive guide for installing RTX-Remix to GarrysMod in addition to downgrading the game for the best experience.

## Prerequisites

Before starting, ensure you have the following:

1. A clean installation of Garry's Mod (32-bit version, not 64-bit beta)

2. Download these required files:
   - [Bridge](https://github.com/NVIDIAGameWorks/bridge-remix)
   - [DXVK Remix](https://github.com/NVIDIAGameWorks/dxvk-remix)
   - [BlueAmulet's Patcher (apply_patch.py)](https://raw.githubusercontent.com/BlueAmulet/SourceRTXTweaks/main/applypatch.py)
   - [Launch Script](https://xenthio.github.io/stuff/launcher_workshop_fullscreen_new.bat)
   - [RTX Configuration File](https://raw.githubusercontent.com/skurtyyskirts/GmodRTX/refs/heads/main/rtx.conf)
   - [Steam DepotDownloader](https://github.com/SteamRE/DepotDownloader)

3. [Python](https://www.python.org/downloads/) installed on your system

## Step 1: Prepare Your Gmod Installation

1. Open Steam and locate Garry's Mod
2. Ensure the game is NOT set to the 64-bit beta (use 32-bit version)
3. Right-click Garry's Mod → Manage → Browse Local Files
4. (Recommended) Create a backup copy of your entire Gmod folder and name it something like "Garry's Mod with RTX"

## Step 2: Install Bridge Remix and DXVK Files

1. Extract the Bridge Remix files:
   - Copy all contents from the Bridge Remix folder
   - Navigate to the `bin` folder in your GmodRTX installation
   - Paste all Bridge Remix files here

2. Extract DXVK Remix files:
   - Copy all contents from the DXVK Remix folder
   - Navigate to the `trex` folder (created from Bridge Remix) in your GmodRTX's bin directory
   - Paste all DXVK Remix files here

## Step 3: Downgrade the game
1. Download DepotDownloader from [GitHub](https://github.com/SteamRE/DepotDownloader/releases/download/DepotDownloader_3.0.0/DepotDownloader-windows-x64.zip)
    - Extract the exe inside the archive to a seperate folder such as `C:\Users\(username)\Downloads\depotdownloader`
    - Open a `cmd` or `powershell` prompt inside that directory
    - Run this command: `.\DepotDownloader.exe -app 4000 -depot 4002 -manifest 6245593690102914874 -username (steamusername)`, enter your password and authenticate your account either by the Steam Guard email or app.
    - Wait for the download to finish.

2. Copying the downgraded files to your GmodRTX Installation
    - In the same folder where DepotDownloader.exe is, go to `depots\4002\16681999`, you should see some GarrysMod files.
    - Copy everything inside the folder and paste them into your GmodRTX installation, replace everything.
    - The game is now downgraded. 
    - > [!WARNING]  
    - > Multiplayer will not work for normal servers, but P2P/LAN with other people running with the same version works.
    
## Step 4: Apply Patches

1. Copy `apply_patch.py` to your GmodRTX root folder (where `gmod.exe` is located)

2. Open Command Prompt in this folder:
   - Click the address bar
   - Type `cmd` and press Enter

3. Run the command:
   ```bash
   python apply_patch.py .
   ```

4. Copy everything from the newly created `patched` folder to your GmodRTX root directory, replacing files when prompted

## Step 4: Optional Portal RTX Files

If you have Portal with RTX installed:

1. Navigate to Portal RTX → Manage → Browse Local Files → bin

2. Locate and copy:
   - stdshader_dx6.dll
   - stdshader_dx7.dll

3. Paste these files into your GmodRTX's bin folder, replacing existing files

## Step 5: Configure DXVK

1. Create a new text file named `dxvk.conf` in your GmodRTX root folder
2. Open it with Notepad
3. Add this line exactly as shown:
   ```
   d3d9.shaderModel = 0
   ```
4. Save the file and ensure it's in the GmodRTX root folder
5. Copy the rtx.conf file contents into the same folder

## Step 6: Install Workshop Content

1. Subscribe to the RTX fixes add-on from the Steam Workshop
2. Subscribe to NikNaks from the Steam Workshop
3. Subscribe to FUCK'EM HALOS

## Step 7: Launch from .bat File

1. Copy the launcher script to your GmodRTX root folder
2. Double-click the launcher script to start the game
