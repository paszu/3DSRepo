The final step of this guide is to install arm9loaderhax and setup AuReiNand to run just milliseconds into the boot. This is accomplished by using SafeA9LHInstaller by [AuroraWright](http://gbatemp.net/members/46970/).

This will install [Delebile's Fork](https://github.com/delebile/arm9loaderhax) of arm9loaderhax.

**If you followed an old version of this guide that did not include Updated SysNAND and want to switch to Updated SysNAND + AuReiNand, just do this entire Part, but skip "Section II - Installing arm9loaderhax"**

**If you currently have Updated SysNAND + Cakes and want to switch to Updated SysNAND + AuReiNand, just follow "Preparatory work."**

**If you used an old revision of this page (and already have Updated SysNAND + AuReiNand), you may only have the ability to launch Decrypt9, if you would like to switch to the new method, download the latest AuReiNand version and follow "Preparatory work."**

**If you used an old revision of this page, you may not have AGB_FIRM and TWL_FIRM patching, if you would like to switch to the new method, download the latest firmware bins and copy them to `/aurei/`.**

This guide uses "Updated SysNAND" mode, in which we copy our RedNAND to SysNAND (to keep games and such) and install arm9loaderhax to have permanent SysNAND hax with no RedNAND required at all.

We will also setup the ability to launch Decrypt9 from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.

#### What you need

* [data_input.zip](https://mega.nz/#!Qkth0BoI!pDgWMamN5cu6HZ91j238MNh7q5ROQKq-a6NLC7Q0dhU) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZUVfWkJkYlM1UEU/view?usp=sharing))
* [payload_input.zip](https://mega.nz/#!YhNRVZAB!Dyx315T174kdy9E3IyOfeXEek-L8262BJnozHHMcez4) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRjh1eXZDRmhXWUk/view?usp=sharing))
* [slot0x05KeyY.bin](https://mega.nz/#!E9VDBApA!QJandFwHWGSGM6SRRwlUodL63ynKrYY9rJp98YXy6Ss) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDekc3YVVjN3dUTWs/view?usp=sharing))
* [slot0x11key96.bin](https://mega.nz/#!IgdFVJiK!TTdhiZ25uxoWlciIySVOynTcHCh8Oyp9JQMzu4opPy4) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZzB5dUhtMjlfcnc/view?usp=sharing))
* [slot0x25keyX.bin](https://mega.nz/#!BoFyzbzT!95N9tJXAi8BfPUzlbwuZC8r8S6Sq6oy-UfuAZz3LhHo) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZ1VNUHpQd2owUlE/view?usp=sharing))
* [slot0x1BKeyX.bin](https://mega.nz/#!opEjwCAL!6OryL37QQO_K_1UP6QG9hRnWvsWKiGSJjHXFcCCEaOI) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDY0RFYm0zdWFUWDQ/view?usp=sharing))
* The latest release of [MiniPasta](https://github.com/d0k3/MiniPasta/releases)
* The latest release of [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases)
* The latest release of [AuReiNand](https://github.com/AuroraWright/AuReiNand/releases)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases)
* The latest release of [Uncart for arm9loaderhax](https://mega.nz/#!R1MFUCBb!s9Nei_EbZsGzAdNaAWB5DGDPuDR72wAUL0sWVqIPOBU) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDdFhoQWJZZ0dKYnc/view?usp=sharing))
* *New 3DS:*
    + AuReiNand NTR [firmware bin](https://mega.nz/#!p0tTDJIQ!aikEtlvB8cjq-aJG9jC6GKx4uvlwN6oI9X2m1OY_ylE) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDM016eHZBQV95anc/view?usp=sharing)) zip file
    + AuReiNand AGB [firmware bin](https://mega.nz/#!998DCCqD!lkzeL2FGvP8f2-1vEPwRz71Di2IctcW4bCd6hHzvGQc) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDLVBXN2ZRbXJpbTg)) zip file
    + AuReiNand TWL [firmware bin](https://mega.nz/#!1x8WkLCT!Nrcv4gdXLK_a9XoXcQSgFkwynAgmqlSy8sTWKfxxdqM) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDeEUtN21nX2VtUmM)) zip file
* *Old 3DS:*
    + AuReiNand NTR [firmware bin](https://mega.nz/#!04lmVQxD!7IMsl4ChzKhkEaPXhCvEPmbEq_PpD9i06EzrIjtVSIQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVFhnaVNzMlR4SVk/view?usp=sharing)) zip file
    + AuReiNand AGB [firmware bin](https://mega.nz/#!0k8CFZjR!YNWR5KWFfR06vjJDrB6MvbfybK9Q1GsznU3ZhBtMQmY) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDMGV2T1pxenFwX0U)) zip file
    + AuReiNand TWL [firmware bin](https://mega.nz/#!gol0CA4T!AqWB7iiPgPb-0vcRv5jBZzHD8IK93kzRZeXJzxs-7d8) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDVi0zOWl4MGhsYms)) zip file

#### Instructions

##### Section I - Preparatory work

2. Delete the `Decrypt9` folder from the root of your SD card if you have one
3. Copy the `a9lh` folder from `data_input.zip` to the root of your SD Card
3. Copy and merge the `a9lh` folder from `payload_input.zip` to the root of your SD Card
4. **Copy your console specific `OTP.bin` (the one you got in Part 4) to the `/a9lh/` folder on the root of your SD card**
1. Copy and merge the `3ds` folder from the SafeA9LHInstaller zip to the root of your SD card
2. Copy `SafeA9LHInstaller.dat` from the SafeA9LHInstaller zip to the root of your SD card
3. Copy `hblauncher_loader.cia` from the `hblauncher_loader` zip to the root of your SD card
1. Copy `arm9loaderhax.bin` and the `aurei` folder from the AuReiNand zip to the root of your SD card
4. Create a new folder called `payloads` in the `/aurei/` folder
7. Copy `Decrypt9WIP.bin` from the Decrypt9WIP zip to the `/aurei/payloads/` folder on your SD card
5. In the `/aurei/payloads` folder, rename `Decrypt9WIP.bin` to `default.bin`
1. Copy and merge the `3DS` folder from the EmuNAND9 zip to the root of your SD card
7. Copy `EmuNAND9.bin` from the EmuNAND9 zip to the `/aurei/payloads/` folder on your SD card
5. In the `/aurei/payloads` folder, rename `EmuNAND9.bin` to `y.bin`
7. Copy `Uncart.bin` from the Uncart zip to the `/aurei/payloads/` folder on your SD card
5. In the `/aurei/payloads` folder, rename `Uncart.bin` to `x.bin`
1. Copy `slot0x05KeyY.bin`, `slot0x11key96.bin`, `slot0x1BKeyX.bin`, and `slot0x25keyX.bin` to the root of your SD card
3. Copy `firmware.bin` from the AuReiNand NTR Firmware zip to the `/aurei/` folder on your SD card
3. Copy `firmware_agb.bin` from the AuReiNand AGB Firmware zip to the `/aurei/` folder on your SD card
3. Copy `firmware_twl.bin` from the AuReiNand TWL Firmware zip to the `/aurei/` folder on your SD card
12. Copy `MiniPasta.3dsx` and `MiniPasta.smdh` to the `/3ds/` folder on your SD card
2. Copy your `emuNAND_original.bin` backups from Section I to the root of your SD card

##### Section II - Installing arm9loaderhax

12. Reinsert your SD card into your 3DS
13. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch MiniPasta, which will patch your SysNAND and reboot your device *(if you use menuhax, you should hold your menuhax key while launching MiniPasta to reboot directly into SysNAND Homebrew Launcher)*
14. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch SafeA9LHInstaller
14. "Exploiting arm9" should be nearly instant, if you get stuck restart and try again
14. Select Full Install
15. The installer will now install arm9loaderhax on your device (this is very fast)
16. Your 3DS should reboot into the AuReiNand menu. If you get a black screen, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_sys_a9lh).

##### Section III - Configuring AuReiNand

1. Use the A button and the D-Pad to turn on the following:    
 + "Updated SysNAND mode"
 + "Use pre-patched FIRMs"
 + "Force A9LH detection"
 + "Show current NAND in System Settings"
 + "Show GBA boot screen in patched AGB_FIRM"
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
6. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy all your files back into it

##### Section VI - Finalising setup

15. From EmuNAND Manager Options, make a backup of SysNAND to `sysNAND.bin`
14. Press Select on the main menu to eject your SD card, then put it in your computer
17. Rename `sysNAND.bin` to `sysNAND-A9LHAX.bin` and copy it to a safe location on your computer; this is a SysNAND backup containing arm9loaderhax **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
15. Delete `sysNAND-A9LHAX.bin` from your SD card
7. Reinsert your SD card into your 3DS then press Start to reboot
6. Update your CFW SysNAND to the latest version using system settings
8. Open Health and Safety (which is now FBI)
9. Navigate to `hblauncher_loader.cia` and press A to install
10. Exit with the home button
10. Launch the HomeBrew Launcher from the home menu icon at least once to download the payload

If everything has gone according to plan, arm9loaderhax will be installed to your device, your RedNAND will have been copied to your SysNAND, you will no longer need RedNAND, you will have a CIA installer, and you'll be able to launch the Homebrew Launcher from an icon on your home menu. Your device will now automatically launch into CFW SysNAND.

You will no longer be able to boot without the SD card in, that is normal.    
You will now boot a Custom Firmware based SysNAND by default.    
You can now hold Select on boot to launch the AuReiNand configuration menu.    
You can now hold Start on boot to launch Decrypt9, a full featured NAND tool.    
You can now hold Y on boot to launch EmuNAND9, a full featured RedNAND and SD management tool.    
You can now hold X on boot to launch Uncart, a tool for [converting a physical game cart](https://www.reddit.com/r/3dshacks/comments/40etaz/) to an installable file. (in the linked guide, replace Brahma with arm9loaderhax)      
You can remove any extra files from the root of the SD card that are not in the image.    

![SD Card](http://i.imgur.com/EfVV0pM.png)
