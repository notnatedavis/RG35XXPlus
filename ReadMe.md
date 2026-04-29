# RG35XX+ (on [Garlic OS](https://github.com/GarlicOS/bootloader_anbernic_rg35xxplus))

> **Everything : install, maintain, and recover your RG35XX+ with Garlic OS**

This repository is a living guide containing commands, file paths, and tips here

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

The **RG35XX+** is a handheld retro gaming device. **Garlic OS** is a lightweight, feature-rich custom firmware that unlocks better performance, power management, and emulator options.

- **Stock OS** → limited, slower  
- **Garlic OS** → faster boot, better scaling, save states, favorites, and more.

Guide prerequisites :
- A computer (w/ program for flashing sd)
- A microSD card (at least 16GB, 32GB+ recommended)
- A microSD card reader
- The **RG35XX+** device
- 
--- 

## Features

- x

--- 

## Project-Structure

```bash
RG35XXPlus/
```

## Usage 

1. **Clone & enter**
   ```bash
   git clone <your-repo-url> && cd PicoClaw-v1
    ```

2. **Set up environment**
    ```bash
    # edit .env.example to .env with real API keys (Groq + Telegram)
    ```

3. **Run the full setup**
    ```bash
   chmod +x scripts/*.sh
   scripts/setup.sh
   bash scripts/health-check.sh
   ```

## Additional-Info

This portion is for logging or storing notes relevent to the project and its scope
