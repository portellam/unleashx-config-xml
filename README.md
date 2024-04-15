# unleashx-config-xml
## Table of Contents
- [1. About](#1_About)
- [2. Softmod Guide](#2-Softmod-Guide)
- [3. `config.xml`](#3-`config.xml`)
- [4. Directories](#4-Directories)
- [5. Power Management](#5-Power-Management)
- [6. References](#6-References)
- [7. Contact](#7-Contact)

## 1. About
Original Xbox softmod guide and custom config files for `UnleashX` dashboard.
Includes insights, recommendations, and common sense backend changes.

## 2. Softmod Guide
This guide is not intended to replace existing guides (here), only to be an overview with comments by this repository's Author.

### 2.1. Pre-setup
Lorem ipsum

### 2.2. The least you need to know
Lorem ipsum

### 2.3. Gotchas
Lorem ipsum

## 3. `config.xml`
### 3.1. Customization
Feel free to modify and take inspiration! You may view the official [UnleashX documentation](https://github.com/rizaumami/unleashx-manual/blob/main/UnleashX.md).

### 3.2. Default folder layouts are frustrating
The default behavior of UnleashX does not have the ability to set a scan depth for folders. However, this is available on "XBMC", or "Aurora" for Xbox 360.

Given common sense and FATX file system limitations, an organized user may feel the existing menu layouts and Rocky5 recommended folder schemes to be inadequate. Well, UnleashX was meant to be customized after-all. The Xbox softmod scene has plentiful amounts of software to boot (here). The number of Xbox retail games that exist will exceed the folder limitations defined in FATX (however, you may run out of partition space first). Let alone complete ROM sets with thousands of titles per console (or generation).

The Author recommends the available folder layouts, as defined in the repository and in `config.xml`. 

### 3.3. User Privileges: Never Trust a Guest
The next best thing to providing an eager younger brother a disconnected Xbox controller, is to lock down the console itself. Why bother with reducing attack vectors? If you wish to setup your Xbox console like a kiosk or share it with people, you do not wish for someone to accidentally or purposefully delete the modded dashboard, for example.

Review the `config.xml` in this repository. You may notice sub menus regarding Formatting disks, Deleting data, Starting a file server (FTP).

#### 3.3.a. XML Tags
Thankfully, the developer of UnleashX provides XML tags for declaring `protected` and `password`-locked sub menus. `protected` meaning the end user cannot make changes in the UnleashX dashboard itself. `password` meaning a defined text password is required to open the menu.

#### 3.3.b. FTP Settings
By default, the FTP server is set to disabled. The Author's reasoning is the fact the Xbox console is exposed to itself while playing online. This is possible over the LAN tunnelling software such as `XLink Kai`. However, this attack vector is unknown for the reverse-engineered Xbox LIVE 1.0 replacement `Insignia` (here).

The option to enable the server temporarily is available without a password lock. The option to permanently enable it is password locked in Settings.

### 3.4 Lorem ipsum
Lorem ipsum

## 4. Directories
### 4.1. `C:` and Shadow `C:`
Using Rocky5's Softmod Installer (here), be sure to enable "Persistent Softmod" or Shadow `C:\` partition. This will protect and obfuscate the new main (custom) dashboard from overwrites by the Microsoft dashboard.

From there, be sure the original Microsoft dashboard remains in the root of `C:\`. The Author recommends to place the contents of UnleashX (or any other custom dashboard) inside the Shadow C folder `C:\Dashboard`.

Without a Persistent Softmod install, all custom dashboard files would be on the root of `C:\`.

### 4.2. First Dashboard as a Shortcut
Should you wish to use a shortcut, do the following:

Rename the (required) dashboard executable (`default.xbe`) located in `C:\Dashboard`. Append the dashboard's title name to the file. Example: for UnleashX, rename as `default_unleashx.xbe`. Then, use the XBE shortcut maker tool (here), and point to the preferred dashboard. Name this shortcut as `default.xbe`, and place it within `C:\Dashboard`.

### 4.3. `E:\`
By default, the `E:\` partition is reserved for game saves, title updates. The partition is small in size compared to the later partitions available in modded Xbox consoles, with non-stock internal drives. It is recommended to leave this partition alone. You may leave low-size essential data here, should `C:\` or other partitions become corrupted.

**Tip:** Backup your game saves that you do not use anymore. Due to `FATX` file system limitations (here), only so many game saves can exist on an Xbox console. Any more than the limit, and the Xbox console will crash at game boot (not OS boot).

### 4.4. `F:\` and `G:\`
The partitions `F:\` and `G:\` may be used for applications, dashboards, emulators, games, homebrew, mods, ROMs - you name it.

Please refer to the recommended folder hierarchy. You may copy the layout in the repository. The custom paths are already defined in the `config.xml` file.

**Tip:** For Xbox consoles with Hard Disk Drives (HDDs), prioritize here higher-traffic data (example: frequently used games) and/or small-sized data (ex: ROMs). Due to the nature of disks, it is faster to read data from the start of a disk (first partition), given this data exists towards the center of the disk itself (where it is fastest to move between layers).

**Tip:** For Xbox consoles with Solid State Drives (SSDs), you do not have to prioritize where data is stored.

## 5. Storage Media
### 5.1. Data Fragmentation
The Xbox console itself and homebrew software offer no ability to defragment data stored on the internal drive. This problem is not an issue for SSDs (here). However, TRIM for SSDs is not available, so it is recommended to pull the SSD from the Xbox console into a PC, and run TRIM processes.

For users with a HDD, it is recommended to refresh your data to avoid defragmentation (partitions `E:\`, `F:\`, and `G:\`). Copy this data to a backup location (external drive) and organize it. 

**Tip:** You may reformat your partitions, given the data is safe in a backup. For `E:\`, use the Microsoft Game Save Manager and delete unnecessary game saves. There is an upper limit for all game saves on `E:\`. Performance issues may exist too (example: multiple saves for *Elder Scrolls III: Morrowind* will slow down the game).

Place lower-volume data (example: apps, dashboards) first on the HDD (earlier partitions, ex: `F:\`). Place higher-volume data later (games, ROMs) second in the same partition, or in a later partition. Read-Only Memory (ROM), including console ROMs and Xbox games, should be placed once and never moved again.

The Author himself has multiple Xbox consoles and terabytes of storage. He has done this process before, but never tested and verified. Better safe than sorry.

### 5.2. Power Management Issue and Solution
**Warning:** Use 5400 RPM HDDs, as higher speed disks will fail to accelerate to normal speed in time after Xbox console boot. Should you encounter this issue, immediately restart the Xbox console, as the disk is already started (similar to how it is easier to start a warm automobile engine).

Power draw is not an issue for SSDs. SSDs are lower-powered, even at peak usage, than HDDs.

### 5.3 Lorem ipsum
Lorem ipsum

## 6. References
Lorem ipsum

## 7. Contact
Did you encounter a bug? Do you need help? Notice any dead links? Please contact by raising an issue with the project itself.
