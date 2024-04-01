# unleashx-config-xml
## Table of Contents
- [1. About](#1_About)

## 1. About
Softmod guide and custom config files for `UnleashX` dashboard for Original Xbox.
Common sense backend changes, folder hierachy, and setting privileges.

## 2. The Author's `config.xml`
### 2.1. Default folder layouts are frustrating
The default behavior of `UnleashX` does not have the ability to set a scan depth for folders. However, this is available on `XBMC`


Given common sense folder layouts (see any ROM set ever) and FATX file system limitations, a complete game collection or ROM sets may exceed the folder size and count limits of the Xbox console. Additionally, any organized and security-conscious person would prefer to categorize the many different pieces of data for a modifed Xbox console. Different applications, games and regions, homebrew, tools, ROMs and emulators, etc.

### 2.2. User privileges: Do not trust a guest.
The next best thing to providing an eager younger brother a disconnected Xbox controller, is to lock down attack vectors in your modifed Xbox console. Why bother? Because...

Review the `config.xml` in this repository. You may notice sub menus regarding Formatting disks, Deleting data, Starting a file server (FTP).

#### 2.2.a. XML tags
Thankfully, the developer of UnleashX provides XML tags for declaring `protected` and `password`-locked sub menus. `protected` meaning the end user cannot make changes in the UnleashX dashboard itself. `password` meaning a defined text password is required to open the menu.

#### 2.2.b. FTP settings
By default, the FTP server is set to disabled. The Author's reasoning is the fact the Xbox console is exposed to itself while playing online. This is possible over the LAN tunnelling software such as `XLink Kai`, however it is not known for the reverse-engineered Xbox LIVE replacement `Insignia` (here).

The option to enable the server temporarily is available without a password lock. The option to permanently enable it is password locked in Settings.

## 3. Directories
### 3.1. `C:` and Shadow `C:`
Using Rocky5's Softmod Installer (here), be sure to enable "Persistent Softmod" or Shadow `C:` partition. This will protect and obfuscate the new main (custom) dashboard from overwrites by the Microsoft dashboard.

From there, be sure the original Microsoft dashboard remains in the root of `C:`. The Author recommends to place the contents of UnleashX (or any other custom dashboard) inside the Shadow C folder `C:\Dashboard`.

Without a Persistent Softmod install, all custom dashboard files would be on the root of `C:`.

### 3.2. First Dashboard as a Shortcut
Should you wish to use a shortcut, do the following:

Rename the (required) dashboard executable (`default.xbe`) located in `C:\Dashboard`. Append the dashboard's title name to the file. Example: for UnleashX, rename as `default_unleashx.xbe`. Then, use the XBE shortcut maker tool (here), and point to the preferred dashboard. Name this shortcut as `default.xbe`, and place it within `C:\Dashboard`.

### 3.3. `E:`
By default, the `E:` partition is reserved for game saves, title updates. The partition is small in size compared to the later partitions available in modded Xbox consoles, with non-stock internal drives. It is recommended to leave this partition alone. You may leave low-size essential data here, should `C:` or other partitions become corrupted.

**Tip:** Backup your game saves that you do not use anymore. Due to `FATX` file system limitations (here), only so many game saves can exist on an Xbox console. Any more than the limit, and the Xbox console will crash at game boot (not OS boot).

### 3.4. `F:` and `G:`
The partitions `F:` and `G:` may be used for applications, dashboards, emulators, games, homebrew, mods, ROMs - you name it.

Please refer to the recommended folder hierarchy. You may copy the layout in the repository. The custom paths are already defined in the `config.xml` file.

**Tip:** For Xbox consoles with Hard Disk Drives (HDDs), prioritize here higher-traffic data (example: frequently used games) and/or small-sized data (ex: ROMs). Due to the nature of disks, it is faster to read data from the start of a disk (first partition), given this data exists towards the center of the disk itself (where it is fastest to move between layers).

**Tip:** For Xbox consoles with Solid State Drives (SSDs), you do not have to prioritize where data is stored.

## 4. Storage media
### 4.1. Data fragmentation
The Xbox console itself and homebrew software offer no ability to defragment data stored on the internal drive. This is not an issue for SSDs (here).

For users with a HDD, it is recommended to refresh your data to avoid defragmentation (partitions `E:`, `F:`, and `G:`). Copy this data to a backup location (external drive) and organize it. You may reformat your partitions, given the data is safe in a backup.

Place lower-volume data first (example: apps, dashboards) first (earlier partitions, ex: `F:`). Place higher-volume data later read-only memory (games, ROMs) second in the same partition, or in a later partition. Read-Only Memory (ROM), including console ROMs and Xbox games, should be placed once and never moved again.

The Author himself has multiple Xbox consoles and terabytes of storage. He has done this process before, but never tested this. Better safe than sorry.

### 4.2. Power management issues and solutions
**Warning:** Use 5400 RPM HDDs, as higher speed disks will fail to accelerate to normal speed in time after Xbox console boot. Should you encounter this issue, immediately restart the Xbox console, as the disk is already started (similar to how it is easier to start a warm automobile engine).

Power draw is not an issue for SSDs. SSDs are lower-powered, even at peak usage, than HDDs.
