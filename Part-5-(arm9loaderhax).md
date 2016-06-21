**You cannot use another console's OTP or you will brick GUARANTEED.**

The final step of this guide is to install arm9loaderhax and setup Luma3DS to run just milliseconds into the boot. This is accomplished by using SafeA9LHInstaller by [AuroraWright](https://github.com/AuroraWright/).

This will install [AuroraWright's Fork](https://github.com/AuroraWright/arm9loaderhax) of arm9loaderhax.

This guide uses "Updated SysNAND" mode, in which we copy our RedNAND to SysNAND (to keep games and such) and install arm9loaderhax to have permanent SysNAND hax with no RedNAND required at all.

We will also setup the ability to launch payloads from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.

#### Overview of steps

In this section, we will go through the process that all the other steps have led up to: actually installing arm9loaderhax.

This is nearly the best possible kind of device exploit because it is permanantly installable into the NAND firm partitions, and runs before most of the OS loads, allowing it to not only work on *all* versions once installed, but also protect itself and recover from most situations that would brick a non-a9lhax 3DS such as a nonfunctional home menu or bad title install.

The file `arm9loaderhax.bin` is what is launched by arm9loaderhax itself after it finishes loading off of NAND, and can be any valid arm9 payload. This file can be replaced at any time, although Luma3DS allows for the launch of other arm9 payloads by holding buttons on boot.

In this case, we use Luma3DS by [AuroraWright](https://github.com/AuroraWright/) to boot a patched SysNAND directly, allowing us to completely bypass the need for any kind of RedNAND, vastly simplifying the usage of a hacked 3DS in addition to saving SD card space.

Once arm9loaderhax is installed and Luma3DS is setup with the correct options, we then backup our SD card and format it using EmuNAND9 to remove the now obsolete RedNAND and reclaim the SD card space it previously used.

During this process, we also setup programs such as **FBI** *(installs CIA formatted games and applications)*, **Luma3DS Updater** *(updates our CFW installation easily)*, **Uncart** *(converts physical cartridge games to digital CIA files)*, **Hourglass9** *(allows us to restore NANDs and such before boot to recover from bricks and do many other miscellaneous functions)*, and **EmuNAND9** *(manages RedNAND installations in addition to several miscellaneous features)*.

Screeninit arm9loaderhax payloads turn on the screen before handing control over to arm9loaderhax.bin (making sure it works with all arm9loaderhax.bin files), while noscreeninit arm9loaderhax payloads do not (allowing arm9loaderhax.bin to control things like brightness during boot). You can choose to use either (the guide used to only have screeninit payloads).

#### Do NOT use the original `payload_input.zip` or `data_input.zip` with SafeA9LHInstaller v2 or you will BRICK!

#### What you need

* [data_input**_v2**.zip](https://mega.nz/#!RwUDVL5T!65gKJHAAVFk3R0jCA7zRFC5q5QTsL5CLoRUoqhET-WI) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaU53U0MtSHlkTDA))
* [aeskeydb.bin](https://mega.nz/#!lhMnnDRJ!1ss7wJNU6ep02nCzEBHLytZd6he79UAnvq7G9hzL2uk) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDdGRPbzltTzJTRzg))
* The latest release of [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases)    
   + See above paragraphs for explanation of "screeninit" and "noscreeninit"
* The latest release of [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases)
* The latest release of [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases)
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases)
* The latest release of [Hourglass9](https://github.com/d0k3/Hourglass9/releases)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [Uncart for arm9loaderhax](https://github.com/AileSc/uncart/releases)
* The latest release of [Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases)

#### Instructions

##### Section I - Preparatory work

1. **Copy `emergency_SecureInfo_A`, `emergency_movable.sed`, `emergency_title.db`, `emergency_ticket.db`, `NCSD_header_[o/n]3ds.bin`, and `firm0firm1.xorpad` from the root of your SD card to a safe location on your computer and back them up to multiple locations (such as online file storage); they do not replace NAND backups, but in the event of lost backups could save you from total data loss (after further research and development is completed)**
2. Delete `emergency_SecureInfo_A`, `emergency_movable.sed`, `emergency_title.db`, `emergency_ticket.db`, `NCSD_header_[o/n]3ds.bin`, and `firm0firm1.xorpad` from the root of your SD card
2. Delete the `EmuNAND9` folder from the root of your SD card if you have one
3. Copy the `a9lh` folder from `data_input_v2.zip` to the root of your SD Card
3. Copy `payload_stage1.bin` and `payload_stage2.bin` from the arm9loaderhax zip to `a9lh` folder on your SD card
2. Copy `arm11.bin` and `arm9.bin` from the SafeA9LHInstaller zip to the root of your SD card
3. Copy `hblauncher_loader.cia` from the hblauncher_loader zip to the root of your SD card
4. Copy `lumaupdate.cia` from the Luma3DS Updater zip to the root of your SD card
1. Copy `arm9loaderhax.bin` and the `luma` folder from the Luma3DS zip to the root of your SD card
7. Copy `Hourglass9.bin` from the Hourglass9 zip to the `/luma/payloads/` folder on your SD card and rename `Hourglass9.bin` to `start_Hourglass9.bin`
7. Copy `EmuNAND9.bin` from the EmuNAND9 zip to the `/luma/payloads/` folder on your SD card and rename `EmuNAND9.bin` to `y_EmuNAND9.bin`
7. Copy `uncart_arm9loaderhax.bin` to the `/luma/payloads/` folder on your SD card and rename `uncart_arm9loaderhax.bin` to `x_Uncart.bin`
1. Copy `aeskeydb.bin` to the root of your SD card
2. Copy `emuNAND_original.bin` and `emuNAND_original.bin.sha` from Section I of Part 4 to the root of your SD card

##### Section II - Installing arm9loaderhax

12. Reinsert your SD card into your 2.1.0 3DS
14. Go to `http://dukesrg.github.io/2xrsa.html?arm11.bin` on your 3DS
    + If you get am error, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_browser)
14. Select Full Install
15. The installer will now install arm9loaderhax on your device (this is very fast)
18. Following this, booting to a black screen is normal (Luma3DS cannot boot a 2.1.0 NAND).
18. Copy your console specific `OTP.bin` from the `/a9lh/` folder on your SD card to a safe location on your computer and back it up to multiple locations (such as online file storage)

##### Section III - Configuring Luma3DS

1. Hold select on boot to enter the Luma3DS menu.     
  + If you get a black screen, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_sys_a9lh).    
  + If you boot to SafeA9LHInstaller, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_safe_a9lh).
1. Use the A button and the D-Pad to turn on the following:    
 + "Autoboot SysNAND"
 + "SysNAND is updated"
 + "Force A9LH detection"
 + "Show current NAND in System Settings"
 + "Show GBA boot screen in patched AGB_FIRM"
2. If you are using a New 3DS, you should *also* enable the following:
 + Toggle "New 3DS CPU" to "Clock+L2(x)" for improved game performance
2. Press Start to save and reboot
18. Following this, booting to a black screen is normal (Luma3DS cannot boot a 2.1.0 NAND).

##### Section IV - Copying RedNAND data to SysNAND

1. Open Hourglass9 from arm9loaderhax by holding Start on boot
1. Go to "SysNAND Backup/Restore..."
2. Select "SysNAND Restore"
3. Confirm and restore from `emuNAND_original.bin`
4. Your device should now be able to boot properly once more.

##### Section V - Removing RedNAND from your SD

2. Press Select on the main menu to eject your SD card
4. Delete `emuNAND_original.bin` and `emuNAND_original.bin.sha` from the root of your SD card
3. **Backup every file on your SD card to a folder on your computer, all files will be deleted in the next step**    
(if you followed Part 3 of this guide, you can delete the SD card backup from that - this will replace it)
0. Reinsert your SD card into your 3DS.
2. Hold Y on boot to launch EmuNAND9
4. Go to "SD Format Options", then "Format SD..."
5. Select the "Format SD (No EmuNAND)" option
6. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy all your files back into it

##### Section VI - Finalizing setup

14. Reinsert your SD card into your 3DS
15. Still from EmuNAND9, go to EmuNAND Manager Options and make a backup of SysNAND to `sysNAND.bin`
14. Press Select on the main menu to eject your SD card, then put it in your computer
17. Rename `sysNAND.bin` to `sysNAND-A9LHAX.bin`, `sysNAND.bin.sha` `sysNAND-A9LHAX.bin.sha`, and copy both to a safe location on your computer; this is a SysNAND backup containing arm9loaderhax **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
15. Delete `sysNAND-A9LHAX.bin` and `sysNAND-A9LHAX.bin.sha` from your SD card
7. Reinsert your SD card into your 3DS then press Start to reboot
6. Update your CFW SysNAND to the latest version using system settings (if it is not already)
8. Open Health and Safety (which is now FBI)
9. Select "SD"
9. Navigate to `hblauncher_loader.cia` and press A to install
9. Navigate to `lumaupdate.cia` and press A to install
10. Exit with the home button
10. Launch the Homebrew Launcher from the home menu icon at least once to ensure the payload is functional
14. Reboot!

If everything has gone according to plan, arm9loaderhax will be installed to your device, your RedNAND will have been copied to your SysNAND, you will no longer need RedNAND, you will have a CIA installer, and you'll be able to launch the Homebrew Launcher from an icon on your home menu. Your device will now automatically launch into CFW SysNAND.

You can now use Luma3DS Updater to update your Luma3DS to the latest version just by opening it and pressing A. *(This is not the same thing as a System Update; it just downloads and extracts the newest Luma3DS files)*

You will no longer be able to boot without the SD card in, that is normal.    
You will now boot a Custom Firmware based SysNAND by default.    
You can now hold Select on boot to launch the Luma3DS configuration menu.    
You can now hold Start on boot to launch Hourglass9, a full featured NAND tool.    
You can now hold Y on boot to launch EmuNAND9, a full featured RedNAND and SD management tool.    
You can now hold X on boot to launch Uncart, a tool for [converting a physical game cart](https://www.reddit.com/r/3dshacks/comments/4hwuhf/) to an installable file.    

You can update your arm9loaderhax installation in the future by following the instructions on the [Updating arm9loaderhax](https://github.com/Plailect/Guide/wiki/Updating-arm9loaderhax/) page.

To use [NTR CFW](https://github.com/44670/BootNTR/), get `ntr.bin` from the appropriate zip on [this](https://github.com/44670/BootNTR/releases) page and copy it to the root of your SD card, then install `BootNTR.cia` from [this](https://github.com/astronautlevel2/BootNTR/releases/) page.

You can remove any extra files from the root of the SD card that are not in the image.    

![SD Card](http://i.imgur.com/TbXejSM.png)