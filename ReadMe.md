# RG35XX+ (on Garlic OS)

 **Everything : install, maintain, and recover your RG35XX+ with Garlic OS**

This repository is a living guide containing commands, file paths, and tips here. Install, maintain, and recover  RG35XX+ with [Garlic OS](https://github.com/GarlicOS/bootloader_anbernic_rg35xxplus) (free open source)

--- 

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Setup](#setup)                           <!-- fresh install, first boot -->
- [Maintenance](#maintenance)               <!-- updates, cleanup, health checks -->
- [Game Saves Backup](#game-saves-backup)   <!-- save states & in-game saves -->
- [Wipe / Reset](#wipe--reset)              <!-- factory reset, reflash, remove everything -->
- [Project Structure](#project-structure)   <!-- folder layout on SD card -->
- [Configuration](#configuration)           <!-- optional tweaks: retroarch, themes, hotkeys -->
- [Additional Info](#additional-info)       <!-- logs, known issues, links -->


--- 

## Introduction

The **RG35XX+** is a handheld retro gaming device and **Garlic OS** is a lightweight, feature-rich custom firmware that unlocks better performance, power management, and emulation including emulator options

- **Stock OS** → (ass cheeks, default) restricted (less features; fast forwared, rewind, states, etc) , slower (unoptimized)  
- **Garlic OS** → faster boot, better scaling, save states, favorites, and more !

Guide prerequisites :
- A computer (w/ program for flashing sd)
- A microSD card (at least 16GB, 32GB+ recommended)
- A microSD card reader
- The **RG35XX+** device

--- 

## Features

- One‑click install via Balena Etcher or (windows equivilant)
- Automatic ROM & all necessary folder structure creation
- Save‑state manager (backup / restore)
- Battery health monitoring script
- Full wipe & reset routine (for selling or troubleshooting)

--- 

## Setup

>  **Warning** – Flashing Garlic OS will erase **everything** on the target microSD card. Backup any existing data first or else

### 1. – Download Garlic OS

- Have this repo accessible for files
- download stock RG35XX+ [img](https://drive.google.com/drive/folders/1LUFdm1ZXKbWIVGd2G4Qd5Pa6CA-peUdx) very large file

### 2. – Flash the stock OS to the SD card

**in Balena Etcher (mac) or Rufus (win)**
1. Insert the SD card into reader / computer
2. Open → select the `.img` file → select the SD card → **Flash**
3. Wait for validation

### 3. – Required files transfer
**download 1.required_files**
1. Open created sd partition 'NO NAME/' 
2. move both files in 1.required_files to NO NAME/ 
3. Eject sd card

### 4. – First boot & initial configuration

1. Insert the flashed SD card into RG35XX+
2. Power on – first boot takes 2‑3 minutes
3. Follow on‑screen language and setup
4. Connect to Wi‑Fi (if supported) – needed for updates later
5. Tweak Settings ?
6. Eject card when finished

### 5. – Add ROMs & BIOS files

The SD card will now have a Roms partition. Your computer should see it automatically, take ejected sd card and open, 

1. Copy ROMs from local computer into corresponding folders in sd :
```bash
└── Roms/
    ├── GB/  # game boy
    ├── GBA/ # game boy advance
    └── ...(other emulations)
```
2. Eject sd card when finished and insert into RG35XX+ (complete!)



## Project-Structure

```bash
RG35XXPlus/
├── ReadMe.md                    # Full guide (setup, backups, reset)
├── scripts/
│   ├── 01_flash_garlic.sh       # Flashes Garlic OS .img to SD card
│   ├── 02_first_boot_helper.sh  # Creates ROM folders, sets defaults
│   ├── 03_backup_saves.sh       # Backs up .srm and .state files to directory
│   ├── 04_restore_saves.sh      # Restores from backup (inject into sd)
│   ├── 05_maintenance.sh        # Clean states, battery check, update
│   └── 06_full_wipe.sh          # Securely erases SD card partitions + whole preformat process
├── configs/
│   ├── retroarch.cfg.optimized  # Pre‑tweaked config (latency, hotkeys, all)
│   └── themes/                  # Example theme files (optional)
├── tools/
│   └── sd_card_identifier.sh    # Shows /dev/sdX safely (Linux/macOS)
└── docs/
    ├── troubleshooting.md
    └── bios_checksums.txt
```

## Usage 

1. **Clone & enter**
   ```bash
   git clone https://github.com/notnatedavis/RG35XXPlus.git && cd RG35XXPlus
   ```

2. **Identify SD card**
    ```bash
    ./tools/sd_card_identifier.sh
    ```

3. **Flash Garlic OS**
    ```bash
   ./scripts/01_flash_garlic.sh --device /dev/sdX --img ~/Downloads/garlic-os-rg35xx+.img
    ^ replace with actual
   ```

4. **Insert SD into RG35XX+ and boot**
   ```bash
   ./scripts/02_first_boot_helper.sh --mount-point /media/$USER/Roms # (manually copy ROMs)
   ./scripts/03_backup_saves.sh # backup the (empty) saves for baseline
   ```

## Additional-Info

This portion is for logging or storing notes relevent to the project and its scope
