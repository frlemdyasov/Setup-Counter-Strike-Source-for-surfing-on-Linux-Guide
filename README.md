# How to setup Counter Strike: Source for Surfing on Linux
[ Why?](#why)

[The Setup](#the-setup)

[How to Remove the HUD](#how-to-remove-the-hud)

[How to Fix the Missing Textures](#how-to-fix-the-missing-textures)

[How to Setup Keybinds for KSF Servers](#how-to-setup-keybinds-for-ksf-servers)

[Where Can I Download Every KSF Surf Map?](#where-can-i-download-every-ksf-surf-map?)



## Why?
This guide is intended for my own future reference. Here I've compiled my own setup procedures.

Every step is described from a Linux perspective, even if some methods are universal.

## The Setup
I use Fedora Workstation 42, and I run CS:S natively.

## How to Remove the HUD
Hud removal cannot be done using console commands on public servers, because they require `sv_cheats 1` to be enabled. Instead you need to download a custom HUD.

1. Download No Hud v2 by One from: https://gamebanana.com/mods/15647 
2. Extract the .zip file
3. In the extracted folder, navigate into `nohudv2/No\ Hud\ clean/cstrike/custom/`
4. Copy the `my_custom_suff` folder into the CS:S `custom` folder
   - This is usually located in `~/.steam/steam/steamapps/common/Counter-Strike\ Source/cstrike/custom/`

Now every HUD element is hidden, except for the crosshair.

## How to Fix the Missing Textures

Some maps contain missing textures on Linux because they reference assets that are case-insensitive.

The fix is outlined here: https://github.com/scorpius2k1/linux-bsp-casefolding-workaround

But here is a shortened procedure for Fedora users:

1. Install dependencies: `sudo dnf makecache && sudo dnf install curl inotify-tools libnotify parallel rsync unzip -y`
2. Clone the repository: `git clone https://github.com/scorpius2k1/linux-bsp-casefolding-workaround.git`
3. Change working directory: `cd linux-bsp-casefolding-workaround`
4. Set permissions: `chmod +x lbspcfw.sh`
5. Run the script: `./lbspcfw.sh`

Now a TUI interface will display

## How to Setup Keybinds for KSF Servers

1. Enable the developer console in the game menu: Options -> Keyboard -> Advanced -> Enable Developer Console (~)
2. Open the developer with the tilde key (~)
3. Create binds using the template: `bind <key> <command>`
   - For example, restarting the map using the v key requires: `bind v sm_restart`
   - A list of commands can be found here: https://www.ksfclan.com/commands/

### Personal Keybinds
Copy this line into the console to recieve my set of keybinds:

`bind v sm_restart; bind q sm_tele; bind e sm_saveloc; bind x sm_teleprev; bind c sm_telenext; bind z sm_surftimer; bind r sm_pr; bind shift +duck; bind mwheeldown +jump; bind mouse1 +left; bind mouse2 +right`


- v: Restart the map
- q: Teleport to the current location
- e: Save a location
- x: Teleport to the previous location
- c: Teleport to the next location
- z: Open the surf timer menu
- r: Open the personal record menu
- shift: Crouch/Duck
- mousewheel down: Jump (Doesn't override space to jump)
- left click: Turn left
- right click: Turn Right

## Where Can I Download Every KSF Surf Map?
You can find them here: https://github.com/OuiSURF/Surf_Maps
