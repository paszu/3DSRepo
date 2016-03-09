The final step of this guide is to install arm9loaderhax and setup CakesFW to run just milliseconds into the boot. This is accomplished by using a handy web compiler by [felipejfc](https://gbatemp.net/threads/416385/) to build arm9loaderhax for our device, then setting it up to work with BootCtr9, a boot manager that lets us load things on boot.

This will install [Delebile's Fork](https://github.com/delebile/arm9loaderhax) of arm9loaderhax.

This guide uses "Updated SysNAND" mode, in which we copy our EmuNAND to SysNAND (to keep games and such) and install arm9loaderhax to have permanant SysNAND hax with no EmuNAND required at all.

We will also setup the ability to launch Decrypt9 from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.

#### What you need

* [boot_config.ini](https://gist.github.com/Plailect/66566928c286de6ecf61)
* [slot0x11key96.bin](https://mega.nz/#!IgdFVJiK!TTdhiZ25uxoWlciIySVOynTcHCh8Oyp9JQMzu4opPy4) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZzB5dUhtMjlfcnc/view?usp=sharing))
* [slot0x25keyX.bin](https://mega.nz/#!BoFyzbzT!95N9tJXAi8BfPUzlbwuZC8r8S6Sq6oy-UfuAZz3LhHo) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZ1VNUHpQd2owUlE/view?usp=sharing))
* The latest release of [MiniPasta](https://github.com/d0k3/MiniPasta/releases)
* The latest release of [BootCtr9](https://github.com/hartmannaf/BootCtr9/releases)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [CakesFW](https://github.com/mid-kid/CakesForeveryWan/releases) (just the .zip file)
* *New 3DS:* CakesFW [*numbered file*](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013820000002/0000001F)
* *New 3DS:* CakesFW [cetk](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013820000002/cetk)
* *Old 3DS:* CakesFW [*numbered file*](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000050)
* *Old 3DS:* CakesFW [cetk](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)

#### Instructions

3. Copy my `boot_config.ini` to the root of your SD card
2. Copy `arm9bootloader.bin` and `arm9loaderhax.bin` from the BootCtr9 zip to the root of your SD card
4. Create a folder called `a9lh` on the root of your SD card
7. Copy `Decrypt9WIP.bin` to the `/a9lh/` folder on your SD card
1. Copy both `slot0x11key96.bin` and `slot0x25keyX.bin` to the root of your SD card
2. Copy the contents of the CakesFW zip to the root of your SD card
3. Copy the *numbered file* and `cetk` to the `Cakes` folder on your SD card
4. Rename the *numbered file* you copied into the `Cakes` folder to `firmware.bin`
7. Copy `Cakes.dat` from the CakesFW zip to the `/a9lh/` folder on your SD card
1. Copy the `3DS` folder from the EmuNAND9 zip to the root of your SD card
12. Copy `MiniPasta.3dsx` and `MiniPasta.smdh` to the `/3ds/` folder on your SD card
3. **Backup every file on your SD card to a folder on your computer, all files will be deleted in the next step**    
(if you followed Part 3 of this guide, you can delete the SD card backup from that - this will replace it)
2. Reinsert your SD card into your 3DS, then get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
3. Open EmuNAND9
4. Go to "SD Format Options"
5. Select the "Format SD Without EmuNAND" option
6. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy all your files back into it
8. Open [this](https://felipejfc.com/a9lh) link on your computer
9. Drag `otp.bin` **(not `otp0x108.bin`!)** onto the CloudA9H page
10. Wait, it can sometimes take a while
11. Copy the produced `arm9loaderhax.3dsx` to the `/3ds/` folder on your SD card
1. Copy the `emuNAND.bin` you created at the beginning of Part 4 - Section I to the root of your SD card    
(if you didn't follow that part of the guide, you will need to create a backup of your EmuNAND using EmuNAND9)
1. Rename `emuNAND.bin` to `NAND.bin` on the root of your SD
12. Reinsert your SD card into your 3DS, then press Start to reboot
13. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
14. Launch CakesFW from the Homebrew Launcher and "Boot CFW" to initialize some key files    
**(if you do not do this then it won't work from a9lhax as a9lhax can't generate the keys by itself, it needs to be launched from Homebrew Launcher at least once)**
15. Cakes is not setup, so after it boots shut it back down and reboot into SysNAND
13. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch MiniPasta, which will patch your SysNAND and reboot you into the home menu
14. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch the arm9loaderhax installer
14. If you get stuck on "exploiting arm9," restart and try again
15. The installer will now restore your EmuNAND `NAND.bin` to SysNAND, then install arm9loaderhax to it
16. Your 3DS should reboot into the CakesFW menu
17. Go to "Select Patches"
15. Deactivate the "Enable emuNAND" patch if it is active
14. Activate the "Block FIRM partition updates", "Disable Signature Checks", and "Survive reboots when launching some titles" patches, then press Start to continue     
**(MAKE SURE YOU SELECT THE BLOCK FIRM PARTITION UPDATES PATCH OR THE NEXT SYSTEM UPDATE WILL DELETE ARM9LOADERHAX AND UPDATE YOUR SYSNAND)**
15. Select "More options"
16. Select "Toggleable options"
17. Select "Enable autoboot (Press L to enter the menu)"
18. Press Start to continue
19. Press B to get back to the Main Menu
15. Select "Boot CFW" to enter CFW SysNAND

If everything has gone according to plan, arm9loaderhax will be installed to your device, your EmuNAND will have been copied to your SysNAND, and you will no longer need EmuNAND. You can now reboot and your device should automatically launch into CFW SysNAND.

You will no longer be able to boot without the SD card in, that is normal    
You can now hold A on boot to launch any updater bins Delebile releases in the future    
You can now hold X on boot to launch Decrypt9, a full featured NAND tool    
You can now hold L on boot to boot into SysNAND