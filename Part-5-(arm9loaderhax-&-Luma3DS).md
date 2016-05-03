The final step of this guide is to install arm9loaderhax and setup Luma3DS to run just milliseconds into the boot. This is accomplished by using SafeA9LHInstaller by [AuroraWright](http://gbatemp.net/members/46970/).

This will install [Delebile's Fork](https://github.com/delebile/arm9loaderhax) of arm9loaderhax.

**If you currently have Updated SysNAND + Cakes and want to switch to Updated SysNAND + Luma3DS, just follow "Preparatory work."**

This guide uses "Updated SysNAND" mode, in which we copy our RedNAND to SysNAND (to keep games and such) and install arm9loaderhax to have permanent SysNAND hax with no RedNAND required at all.

We will also setup the ability to launch payloads from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.

#### What you need

* [data_input.zip](https://mega.nz/#!Qkth0BoI!pDgWMamN5cu6HZ91j238MNh7q5ROQKq-a6NLC7Q0dhU) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZUVfWkJkYlM1UEU/view?usp=sharing))
* [payload_input.zip](https://mega.nz/#!YhNRVZAB!Dyx315T174kdy9E3IyOfeXEek-L8262BJnozHHMcez4) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRjh1eXZDRmhXWUk/view?usp=sharing))
* [slotkey_input.zip](https://mega.nz/#!R0VQGDLJ!LIUoz_ErqmbXpOO2cBsmyG6KGCgBdR5xjOg7EPci5Ao) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDN0ZaTjFfQkpNc3M))
* The latest release of [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases)
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases)
* The latest release of [Uncart for arm9loaderhax](https://github.com/AuroraWright/uncart/releases)
* The latest release of [Luma3DS Updater](http://3ds.intherack.com/files/lumaupdate_1.2.0.cia)
* *New 3DS:*
    + Luma3DS NTR [firmware bin](https://mega.nz/#!p0tTDJIQ!aikEtlvB8cjq-aJG9jC6GKx4uvlwN6oI9X2m1OY_ylE) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDM016eHZBQV95anc/view?usp=sharing)) zip file
* *Old 3DS:*
    + Luma3DS NTR [firmware bin](https://mega.nz/#!04lmVQxD!7IMsl4ChzKhkEaPXhCvEPmbEq_PpD9i06EzrIjtVSIQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVFhnaVNzMlR4SVk/view?usp=sharing)) zip file

#### Instructions

##### Section I - Preparatory work

2. Delete the `Decrypt9` folder from the root of your SD card if you have one
3. Copy the `a9lh` folder from `data_input.zip` to the root of your SD Card
3. Copy and merge the `a9lh` folder from `payload_input.zip` to the root of your SD Card
4. **Copy your console specific `OTP.bin` (the one you got in Part 4) to the `/a9lh/` folder on the root of your SD card**
1. Copy and merge the `3ds` folder from the SafeA9LHInstaller zip to the root of your SD card
2. Copy `SafeA9LHInstaller.dat` from the SafeA9LHInstaller zip to the root of your SD card
3. Copy `hblauncher_loader.cia` from the `hblauncher_loader` zip to the root of your SD card
4. Copy `lumaupdate_1.1.2.cia` to the root of your SD card
1. Copy `arm9loaderhax.bin` and the `luma` folder from the Luma3DS zip to the root of your SD card
7. Copy `Decrypt9WIP.bin` from the Decrypt9WIP zip to the `/luma/payloads/` folder on your SD card
5. In the `/luma/payloads` folder, rename `Decrypt9WIP.bin` to `start_Dec9.bin`
1. Copy and merge the `3DS` folder from the EmuNAND9 zip to the root of your SD card
7. Copy `EmuNAND9.bin` from the EmuNAND9 zip to the `/luma/payloads/` folder on your SD card
5. In the `/luma/payloads` folder, rename `EmuNAND9.bin` to `y_EmuN9.bin`
7. Copy `arm9loaderhax.bin` from the Uncart zip to the `/luma/payloads/` folder on your SD card
5. In the `/luma/payloads` folder, rename `arm9loaderhax.bin` to `x_Uncart.bin`
1. Copy the contents of `slotkey_input.zip` to the root of your SD card
3. Copy `firmware.bin` from the Luma3DS NTR Firmware zip to the `/luma/` folder on your SD card
2. Copy your `emuNAND_original.bin` backups from Section I to the root of your SD card

##### Section II - Installing arm9loaderhax

12. Reinsert your SD card into your 3DS
14. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch SafeA9LHInstaller
14. "Exploiting arm9" should be nearly instant, if you get stuck restart and try again
14. Select Full Install
15. The installer will now install arm9loaderhax on your device (this is very fast)
16. Your hold select on boot to enter the Luma3DS menu. If you get a black screen, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_sys_a9lh).

##### Section III - Configuring Luma3DS

1. Use the A button and the D-Pad to turn on the following:    
 + "Autoboot SysNAND"
 + "SysNAND is updated"
 + "Force A9LH detection"
 + "Show current NAND in System Settings"
 + "Show GBA boot screen in patched AGB_FIRM"
2. If you are using a New 3DS, you should *also* enable the following:
 + Toggle "New 3DS CPU" to "CLock+L2(x)" for improved game performance
2. Press Start to save and reboot

##### Section IV - Copying RedNAND data to SysNAND

11. Reboot, then open Decrypt9 from arm9loaderhax by holding Start on boot
1. Go to "SysNAND Options"
1. Go to "SysNAND Backup/Restore..."
2. Select "NAND Restore **(keep a9lh)**"
3. Confirm and restore from `emuNAND_original.bin`

##### Section V - Removing RedNAND from your SD

2. Press Select on the main menu to eject your SD card
4. Delete `emuNAND_original.bin` from the root of your SD card
3. **Backup every file on your SD card to a folder on your computer, all files will be deleted in the next step**    
(if you followed Part 3 of this guide, you can delete the SD card backup from that - this will replace it)
0. Reinsert your SD card into your 3DS.
2. Hold Y on boot to launch EmuNAND9
4. Go to "SD Format Options", then "Format SD..."
5. Select the "Format SD Without EmuNAND" option
9. Ignore the `starter.bin` prompt and continue
6. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy all your files back into it

##### Section VI - Finalising setup

14. Reinsert your SD card into your 3DS
15. From EmuNAND Manager Options, make a backup of SysNAND to `sysNAND.bin`
14. Press Select on the main menu to eject your SD card, then put it in your computer
17. Rename `sysNAND.bin` to `sysNAND-A9LHAX.bin` and copy it to a safe location on your computer; this is a SysNAND backup containing arm9loaderhax **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
15. Delete `sysNAND-A9LHAX.bin` from your SD card
7. Reinsert your SD card into your 3DS then press Start to reboot
6. Update your CFW SysNAND to the latest version using system settings
8. Open Health and Safety (which is now FBI)
9. Select "SD"
9. Navigate to `hblauncher_loader.cia` and press A to install
9. Navigate to `lumaupdate_1.1.2.cia` and press A to install
10. Exit with the home button
10. Launch the HomeBrew Launcher from the home menu icon at least once to download the payload

If everything has gone according to plan, arm9loaderhax will be installed to your device, your RedNAND will have been copied to your SysNAND, you will no longer need RedNAND, you will have a CIA installer, and you'll be able to launch the Homebrew Launcher from an icon on your home menu. Your device will now automatically launch into CFW SysNAND.

You can now use Luma3DS Updater to update your Luma3DS to the latest version just by opening it and pressing A. *(This is not the same thing as a System Update; it just downloads and extracts the newest Luma3DS files)*

You will no longer be able to boot without the SD card in, that is normal.    
You will now boot a Custom Firmware based SysNAND by default.    
You can now hold Select on boot to launch the Luma3DS configuration menu.    
You can now hold Start on boot to launch Decrypt9, a full featured NAND tool.    
You can now hold Y on boot to launch EmuNAND9, a full featured RedNAND and SD management tool.    
You can now hold X on boot to launch Uncart, a tool for [converting a physical game cart](https://www.reddit.com/r/3dshacks/comments/40etaz/) to an installable file. (in the linked guide, replace Brahma with arm9loaderhax)      
You can remove any extra files from the root of the SD card that are not in the image.    

![SD Card](http://i.imgur.com/OxjXC1O.png)
