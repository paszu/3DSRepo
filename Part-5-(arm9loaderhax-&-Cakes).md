The final step of this guide is to install arm9loaderhax and setup CakesFW to run just milliseconds into the boot. This is accomplished by using SafeA9LHInstaller by [AuroraWright](http://gbatemp.net/members/46970/), then setting it up to work with BootCtr9, a boot manager that lets us load things on boot.

This will install [Delebile's Fork](https://github.com/delebile/arm9loaderhax) of arm9loaderhax.

**If you followed an old version of this guide that did not include Updated SysNAND and want to switch to Updated SysNAND + Cakes, just restore your SysNAND from a pre-arm9loaderhax SysNAND backup and follow all of this Part.**

**If you currently have Updated SysNAND + AuReiNAND and want to switch to Updated SysNAND + Cakes, just follow "Preparatory work" and "Configuring CakesFW".**

This guide uses "Updated SysNAND" mode, in which we copy our EmuNAND to SysNAND (to keep games and such) and install arm9loaderhax to have permanant SysNAND hax with no EmuNAND required at all.

We will also setup the ability to launch Decrypt9 from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.

#### What you need

* [boot_config.ini](https://gist.github.com/Plailect/66566928c286de6ecf61)
* [data_input.zip](https://mega.nz/#!Qkth0BoI!pDgWMamN5cu6HZ91j238MNh7q5ROQKq-a6NLC7Q0dhU) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZUVfWkJkYlM1UEU/view?usp=sharing))
* [payload_input.zip](https://mega.nz/#!YhNRVZAB!Dyx315T174kdy9E3IyOfeXEek-L8262BJnozHHMcez4) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRjh1eXZDRmhXWUk/view?usp=sharing))
* [slot0x05KeyY.bin](https://mega.nz/#!E9VDBApA!QJandFwHWGSGM6SRRwlUodL63ynKrYY9rJp98YXy6Ss) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDekc3YVVjN3dUTWs/view?usp=sharing))
* [slot0x11key96.bin](https://mega.nz/#!IgdFVJiK!TTdhiZ25uxoWlciIySVOynTcHCh8Oyp9JQMzu4opPy4) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZzB5dUhtMjlfcnc/view?usp=sharing))
* [slot0x25keyX.bin](https://mega.nz/#!BoFyzbzT!95N9tJXAi8BfPUzlbwuZC8r8S6Sq6oy-UfuAZz3LhHo) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZ1VNUHpQd2owUlE/view?usp=sharing))
* The latest release of [MiniPasta](https://github.com/d0k3/MiniPasta/releases)
* The latest release of [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases)
* The latest release of [BootCtr9](https://github.com/hartmannaf/BootCtr9/releases/)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases)
* The latest release of [Uncart for arm9loaderhax](https://mega.nz/#!R1MFUCBb!s9Nei_EbZsGzAdNaAWB5DGDPuDR72wAUL0sWVqIPOBU) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDdFhoQWJZZ0dKYnc/view?usp=sharing))
* The latest release of [CakesFW](https://github.com/mid-kid/CakesForeveryWan/releases) (just the .zip file)
* *New 3DS:*
    + CakesFW [firmware.bin](https://mega.nz/#!1xdnWDjR!dgy0Vs2VjuJsL23axRYIlAKeLctbYzyQBEvVwh6T-Zw) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDR3VUY1BQTjloSDA))
    + CakesFW [firmkey.bin](https://mega.nz/#!VtdAlB7C!w5aZdVoDjaSYSJao0u9a-La6CoY2mWzjLVFzRvT8MmA) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDOHlpR2t4S2ZlTlU/view?usp=sharing))
* *Old 3DS:*
    + CakesFW [firmware.bin](https://mega.nz/#!5kFDTa6Q!xhiYtPIkXoaRlfp65DmHXjXLFW6_-OWodpUqvOtLGtc) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDSW5mOVREcWE0Q2c/view?usp=sharing))
    + CakesFW [firmkey.bin](https://mega.nz/#!htlGzArZ!AianutIfa4K-WtGfrVZNjDSCL_LaykJwGD20aMxDXtc) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDSXRhMlRfNU5OdTA/view?usp=sharing))

#### Instructions

##### Preparatory work

2. Delete the `Decrypt9` folder from the root of your SD card if you have one
3. Copy the `a9lh` folder from `data_input.zip` to the root of your SD Card
3. Copy and merge the `a9lh` folder from `payload_input.zip` to the root of your SD Card
4. **Copy your console specific `OTP.bin` to the `/a9lh/` folder on the root of your SD card**
1. Copy and merge the `3ds` folder from the SafeA9LHInstaller zip to the root of your SD card
2. Copy `SafeA9LHInstaller.dat` from the SafeA9LHInstaller zip to the root of your SD card
2. Copy `arm9bootloader.bin` and `arm9loaderhax.bin` from the BootCtr9 zip to the root of your SD card
3. Copy `hblauncher_loader.cia` from the `hblauncher_loader` zip to the root of your SD card
3. **Copy `boot_config.ini` from the "What you need" section above the to the root of your SD card (not from the BootCtr9 zip)**
7. Copy `Decrypt9WIP.bin` from the Decrypt9WIP zip and `Uncart.bin` from the Uncart zip to the `/a9lh/` folder on your SD card
1. Copy `slot0x05KeyY.bin`, `slot0x11key96.bin`, and `slot0x25keyX.bin` to the root of your SD card
2. Copy the contents of the CakesFW zip to the root of your SD card
3. Copy `firmware.bin` and `firmkey.bin` to the `Cakes` folder on your SD card
7. Copy `Cakes.dat` from the CakesFW zip to the `/a9lh/` folder on your SD card
1. Copy and merge the `3DS` folder from the EmuNAND9 zip to the root of your SD card
2. Copy `EmuNAND9.bin` from the EmuNAND9 zip to the `/a9lh/` folder on your SD card
12. Copy `MiniPasta.3dsx` and `MiniPasta.smdh` to the `/3ds/` folder on your SD card

##### Installing arm9loaderhax

12. Reinsert your SD card into your 3DS, then press Start to reboot
13. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch MiniPasta, which will patch your SysNAND and reboot you into the home menu
14. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice **(You CANNOT use menuhax for this)**
13. Launch the arm9loaderhax installer
14. "Exploiting arm9" should be nearly instant, if you get stuck restart and try again
14. Select Full Install
15. The installer will now install arm9loaderhax on your device (this is very fast)
16. Your 3DS should reboot into the CakesFW menu. If you get a black screen, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_sys_a9lh).

##### Configuring CakesFW

17. Go to "Select Patches"
15. Deactivate the "Enable emuNAND" patch if it is active
14. Activate the "Block FIRM partition updates" and "Disable Signature Checks" patches, then press Start to continue     
**(MAKE SURE YOU SELECT THE BLOCK FIRM PARTITION UPDATES PATCH OR THE NEXT SYSTEM UPDATE WILL BRICK YOU)**
15. Select "More options"
16. Select "Toggleable options"
17. Select "Enable autoboot (Press L to enter the menu)"
18. Press Start to continue
19. Press B to get back to the Main Menu
15. Select "Boot CFW" to enter CFW SysNAND

##### Entering Decrypt9

11. Reboot, then open Decrypt9 from arm9loaderhax by holding X on boot

##### Copying EmuNAND data to SysNAND
1. Go to "EmuNAND File Options" then "Partition Dump..."
2. "Dump CTRNAND Partition" to `CTRNAND.bin`
3. Use B to go back to the Main Menu
4. Go to "SysNAND File Options" then "Partition Inject..."
5. "Inject CTRNAND Partition" from `CTRNAND.bin`

##### Removing EmuNAND from your SD

2. Press Select on the main menu to eject your SD card
4. Delete `CTRNAND.bin` from the root of your SD card
3. **Backup every file on your SD card to a folder on your computer, all files will be deleted in the next step**    
(if you followed Part 3 of this guide, you can delete the SD card backup from that - this will replace it)
0. Reinsert your SD card into your 3DS.
2. Hold Y on boot to launch EmuNAND9
4. Go to "SD Format Options", then "Format SD..."
5. Select the "Format SD Without EmuNAND" option
6. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy all your files back into it

##### Installing FBI into SysNAND

15. **If you already had FBI injected into EmuNAND, you can skip this section**
16. Hold X on boot to launch Decrypt9
12. Go to "SysNAND File Options", then select the "Dump Health & Safety" option to dump Health & Safety to `hs.app` **(you can use Up and Down / Left and Right to change the name)**
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
You can now hold X on boot to launch Decrypt9, a full featured NAND tool.    
You can now hold Y on boot to launch EmuNAND9, a full featured EmuNAND and SD management tool.    
You can now hold B on boot to launch Uncart, a tool for [converting a physical game cart](https://www.reddit.com/r/3dshacks/comments/40etaz/) to an installable file.    
You can now hold L on boot to enter the CakesFW menu.

You can remove any extra files from the root of the SD card that are not in the image.

![SD Card](http://i.imgur.com/nDMXVDa.png)
