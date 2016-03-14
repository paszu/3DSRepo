The final step of this guide is to install arm9loaderhax and setup AuReiNAND to run just milliseconds into the boot. This is accomplished by using a handy web compiler by [felipejfc](https://gbatemp.net/threads/416385/) to build arm9loaderhax for our device, then setting it up to work with BootCtr9, a boot manager that lets us load things on boot.

This will install [Delebile's Fork](https://github.com/delebile/arm9loaderhax) of arm9loaderhax.

**If you followed an old version of this guide that did not include Updated SysNAND and want to switch to Updated SysNAND + AuReiNAND, just restore your SysNAND from a pre-arm9loaderhax SysNAND backup and follow all of this Part.**

**If you currently have Updated SysNAND + Cakes and want to switch to Updated SysNAND + AuReiNAND, just follow "Preparatory work".**

This guide uses "Updated SysNAND" mode, in which we copy our EmuNAND to SysNAND (to keep games and such) and install arm9loaderhax to have permanant SysNAND hax with no EmuNAND required at all.

We will also setup the ability to launch Decrypt9 from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.

#### What you need

* [AuReiNAND_options.zip](https://mega.nz/#!ApMwEDaS!5QORKPl5ewnr4Ffrsm4J69n1sOC0ijEGsYEKBqBI1TI) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDeU9LRXVhNjgyU2c/view?usp=sharing))
* [slot0x05KeyY.bin](https://mega.nz/#!E9VDBApA!QJandFwHWGSGM6SRRwlUodL63ynKrYY9rJp98YXy6Ss) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDekc3YVVjN3dUTWs/view?usp=sharing))
* [slot0x11key96.bin](https://mega.nz/#!IgdFVJiK!TTdhiZ25uxoWlciIySVOynTcHCh8Oyp9JQMzu4opPy4) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZzB5dUhtMjlfcnc/view?usp=sharing))
* [slot0x25keyX.bin](https://mega.nz/#!BoFyzbzT!95N9tJXAi8BfPUzlbwuZC8r8S6Sq6oy-UfuAZz3LhHo) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZ1VNUHpQd2owUlE/view?usp=sharing))
* The latest release of [MiniPasta](https://github.com/d0k3/MiniPasta/releases)
* The latest release of [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [AuReiNAND](https://github.com/AuroraWright/AuReiNand/releases)
* *New 3DS:* 
    + AuReiNAND NTR [firmware bin](https://mega.nz/#!p0tTDJIQ!aikEtlvB8cjq-aJG9jC6GKx4uvlwN6oI9X2m1OY_ylE) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDM016eHZBQV95anc/view?usp=sharing)) zip file
* *Old 3DS:*
    + AuReiNAND NTR [firmware bin](https://mega.nz/#!04lmVQxD!7IMsl4ChzKhkEaPXhCvEPmbEq_PpD9i06EzrIjtVSIQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVFhnaVNzMlR4SVk/view?usp=sharing)) zip file

#### Instructions

##### Preparatory work

2. Delete the `Decrypt9` folder from the root of your SD card if you have one
1. Copy everything except the `menuhax` folder from the AuReiNAND zip to the root of your SD card
3. Copy `hblauncher_loader.cia` from the `hblauncher_loader` zip to the root of your SD card
7. Copy `Decrypt9WIP.bin` from the Decrypt9WIP zip to the `/rei/` folder on your SD card
5. In the `/rei/` folder, rename `Decrypt9WIP.bin` to `arm9payload.bin`
5. Copy all files from `AuReiNAND_options` zip to the `/rei/` folder on your SD card
1. Copy `slot0x05KeyY.bin`, `slot0x11key96.bin`, and `slot0x25keyX.bin` to the root of your SD card
3. Copy `firmware.bin` from the AuReiNAND NTR Firmware zip to the `/rei/` folder on your SD card
12. Copy `MiniPasta.3dsx` and `MiniPasta.smdh` to the `/3ds/` folder on your SD card
3. **Backup every file on your SD card to a folder on your computer, all files will be deleted in the next step**    
(if you followed Part 3 of this guide, you can delete the SD card backup from that - this will replace it)

##### Removing EmuNAND from your SD

0. Reinsert your SD card into your 3DS.
1. **Ensure you have the EmuNAND backup `emuNAND_original.bin` from Part 4 - Section I. If not, create one now.**
2. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
3. Open EmuNAND9
4. Go to "SD Format Options", then "Format SD..."
5. Select the "Format SD Without EmuNAND" option
6. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy all your files back into it

##### Installing arm9loaderhax

8. Open [this](https://felipejfc.com/a9lh) link on your computer
9. Drag `otp.bin` **(not `otp0x108.bin`!)** onto the CloudA9H page
10. Wait, it can sometimes take a while
11. Copy the produced `arm9loaderhax.3dsx` to the `/3ds/` folder on your SD card
1. Copy the `emuNAND_original.bin` you created at the beginning of Part 4 - Section I to the root of your SD card    
1. Rename `emuNAND_original.bin` to `NAND.bin` on the root of your SD
12. Reinsert your SD card into your 3DS, then press Start to reboot
13. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch MiniPasta, which will patch your SysNAND and reboot you into the home menu
14. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch the arm9loaderhax installer
14. "Exploiting arm9" should be nearly instant, if you get stuck restart and try again
15. The installer will now restore your EmuNAND `NAND.bin` to SysNAND, then install arm9loaderhax to it
14. Your 3DS should reboot into CFW SysNAND. If you get a black screen, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_sys_a9lh).

##### Enter Decrypt9

11. Reboot, then open Decrypt9 from arm9loaderhax by holding L+R on boot

##### Installing FBI into SysNAND

15. **If you already had FBI injected into EmuNAND, then skip this section**
12. Go to "SysNAND File Options", then select the "Dump Health & Safety" option
12. Press Select to eject your SD card, then put it in your computer
13. Extract Universal Inject Generater, then copy both `hs.app` from your SD card and `FBI.cia` from the FBI zip to the `input` folder
14. Double click `go.bat`
15. Copy `FBI_inject_with_banner.app` to the root of your SD card and reinsert your SD card into your 3DS
16. Press B on Decrypt9, then go to "SysNAND File Options" and select the "Inject Health & Safety" option
17. Press down once to select `FBI_inject_with_banner.app`, then press A to inject

##### Finalising setup

15. From the main menu, go to SysNAND File Options, then make a backup of SysNAND to `sysNAND.bin`
14. Press Select on the main menu to eject your SD card, then put it in your computer
17. Rename `sysNAND.bin` to `sysNAND-A9LHAX.bin` and copy it to a safe location on your computer; this is a SysNAND backup containing arm9loaderhax
15. Delete `sysNAND-A9LHAX.bin` from your SD card
15. Delete `NAND.bin` from your SD card
7. Reinsert your SD card into your 3DS then press Start to reboot
6. Update your CFW SysNAND to the latest version using system settings
8. Open Health and Safety (which is now FBI)
9. Navigate to `hblauncher_loader.cia` and press A to install
10. Exit with the home button
10. Launch the homebrew launcher from the home menu icon at least once to download the payload

If everything has gone according to plan, arm9loaderhax will be installed to your device, your EmuNAND will have been copied to your SysNAND, you will no longer need EmuNAND, you will have a CIA installer, and you'll be able to launch the Homebrew Launcher from an icon on your home menu. Your device will now automatically launch into CFW SysNAND.

You will no longer be able to boot without the SD card in, that is normal.    
You will now boot a Custom Firmware based SysNAND by default.    
You can now hold L+R on boot to launch Decrypt9, a full featured NAND tool.    
You can remove any extra files from the root of the SD card that are not in the image.

![SD Card](http://i.imgur.com/2bAlKhp.png)