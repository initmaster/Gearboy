# Standalone Game Boy (Color) Application using Gearboy

This project is a fork of [Gearboy](https://github.com/drhelius/Gearboy) by [drhelius](https://github.com/drhelius).

The goal of this fork is to transform Gearboy into a **standalone Game Boy / Game Boy Color application**, embedding both the emulator and the game into a **single self-contained executable**.

The concept is inspired by [GBCbag2](https://github.com/faktor73/gbcbag2) by [faktor73](https://github.com/faktor73).


## Overview

This fork removes all non-essential emulator features in order to focus on a **clean, minimal and distributable game executable**.

The resulting build produces **one single `.exe` file**, with:
- no external DLLs
- no external ROM file
- no runtime configuration files


## Key Differences from Upstream Gearboy

The following features have been **removed**:

- All debugging features
- Audio recording functionality
- Cheat code support
- Game RAM save/load support
- ROM loading from file (file dialog)
- Compilation profiles for all platforms except Windows

The following features have been **added or modified**:

- Two additional keyboard input profiles
- Embedded Game Boy / Game Boy Color ROM
- Embedded SDL library (static linking)
- Embedded game, icon and informations
- Game informations visible in the "About" dialog


## Build Requirements

- **Windows**
- **Microsoft Visual Studio** (tested with Visual Studio 2022)
- **Desktop development with C++** (Workload)



## Configuration

All configuration is handled through the `/config` directory **at build time**.

This directory contains the following files:

- `game.gb`  
  The Game Boy / Game Boy Color ROM that will be embedded directly into the executable.
- `iconfile.ico`  
  The Windows application icon.
- `settings.json`  
  Contains application and game metadata such as title, version, author, and website.  
  These values are embedded into the executable at build time.
  ```json 
  {
  "GameTitle": "Blupi's Adventures DEMO",
  "Version": "1.2.0",
  "Author": "initmaster",
  "GameWebsite": "https://initmaster.itch.io/blupis-adventures"
  }


## Advantages

- Single, standalone .exe file
- No external files required
- Easy distribution
- No installer needed
- Ideal for game jams, demos, or small commercial releases


## Contributors

Thank you to all the people who have already contributed to Gearboy! (and maybe to this fork !)


## License

Gearboy is licensed under the GNU General Public License v3.0 License, see [LICENSE](LICENSE) for more information.
