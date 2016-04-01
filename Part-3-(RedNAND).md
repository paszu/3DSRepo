This part of the guide will use two terms you must be familiar with in order to understand what's going on: SysNAND and RedNAND (named for redirected NAND). The term SysNAND refers to a physical chip inside your 3DS which contains all system software, the OS, the bootloader, and so on (games, themes, and save files for installed games are stored and encrypted on the SD card). Doing something sketchy to your SysNAND, even if it's just removing a system title, can result in a bricked 3DS (it becomes as useful as a brick).

Because of this, we keep the 9.2.0 SysNAND as it is, but we copy it to a partition on your SD card then redirect to it when any Custom Firmware (CFW) is launched. Using this method, you can unlink theses two NANDs and have a fully exploitable 9.2.0 system that can launch a secondary OS at the latest version which is then patched to allow exploits to work.

If your SysNAND is ever broken, you have a bricked system, but if your RedNAND is broken, you will only have bricked the RedNAND which is easy to fix. A SysNAND brick can only be recovered by soldering internal components and writing an existing SysNAND backup from your computer to the internal memory (or by using arm9loaderhax), but RedNAND bricks can be recovered just by using a homebrew application such as EmuNAND9 to restore your RedNAND from backup.

RedNAND, since it is completely separate from your SysNAND, can be updated to the latest version, allowing you to play all games on an exploited system.

Unfortunately, RedNAND has its own set of [drawbacks](https://www.reddit.com/r/3dshacks/comments/49qj9w/arm9loaderhax_if_you_dont_like_sysnand_permahax/d0ud80d), which is why we only take advantage of it for the purpose of safely getting our OTP before setting up arm9loaderhax and CFW SysNAND, which is far superior.

This part of the guide will take you through the process of setting up RedNAND and a CFW on your SD card and device, then through the process of formatting one of the NANDs to unlink them from each other.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

#### What you need

* [slot0x11key96.bin](https://mega.nz/#!IgdFVJiK!TTdhiZ25uxoWlciIySVOynTcHCh8Oyp9JQMzu4opPy4) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZzB5dUhtMjlfcnc/view?usp=sharing))
* [slot0x25keyX.bin](https://mega.nz/#!BoFyzbzT!95N9tJXAi8BfPUzlbwuZC8r8S6Sq6oy-UfuAZz3LhHo) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZ1VNUHpQd2owUlE/view?usp=sharing))
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [TinyFormat](https://github.com/javimadgit/TinyFormat/releases)
* The latest release of [CakesFW](https://github.com/mid-kid/CakesForeveryWan/releases) (the .zip file)
* *New 3DS:*
    + CakesFW [firmware.bin](https://mega.nz/#!1xdnWDjR!dgy0Vs2VjuJsL23axRYIlAKeLctbYzyQBEvVwh6T-Zw) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDR3VUY1BQTjloSDA))
    + CakesFW [firmkey.bin](https://mega.nz/#!VtdAlB7C!w5aZdVoDjaSYSJao0u9a-La6CoY2mWzjLVFzRvT8MmA) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDOHlpR2t4S2ZlTlU/view?usp=sharing))
* *Old 3DS:*
    + CakesFW [firmware.bin](https://mega.nz/#!5kFDTa6Q!xhiYtPIkXoaRlfp65DmHXjXLFW6_-OWodpUqvOtLGtc) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDSW5mOVREcWE0Q2c/view?usp=sharing))
    + CakesFW [firmkey.bin](https://mega.nz/#!htlGzArZ!AianutIfa4K-WtGfrVZNjDSCL_LaykJwGD20aMxDXtc) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDSXRhMlRfNU5OdTA/view?usp=sharing))

#### Instructions

1. Copy both `slot0x11key96.bin` and `slot0x25keyX.bin` to the root of your SD card
2. Copy the contents of the CakesFW zip to the root of your SD card
3. Copy the `firmware.bin` and `firmkey.bin` to the `Cakes` folder on your SD card
1. Copy and merge the `3ds` folder from the EmuNAND9 zip to the root of your SD card
2. Copy the `TinyFormat` folder from the TinyFormat zip to the `/3ds/` folder on your SD card
3. **Backup every file on your SD card to a folder on your computer, all files will be deleted in the next step**
4. Reinsert your SD card into your 3DS, then get into the Homebrew Launcher through the entrypoint of your choice
5. Open EmuNAND9 **(This can sometimes take a few tries - if you still can't get it to work after quite a few, you can rerun the downgrade to make sure everything worked properly)**
6. Select the "Complete RedNAND setup" option
9. Ignore the `starter.bin` prompt and press A to continue
9. Confirm and wait for it to finish
8. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy all your files back into it
10. Reinsert your SD card into your 3DS, then press Start to reboot
11. Get into the Homebrew Launcher through the entrypoint of your choice
12. Open CakesFW **(This can sometimes take a few tries)**
13. Go to "Select Patches"
14. Activate the "Enable EmuNAND" and "Disable Signature Checks" patches, then press Start to continue
15. Select "Boot CFW" to enter RedNAND (you must launch CakesFW from the Homebrew Launcher every time you want to boot RedNAND)
13. If you boot into the home menu, you have successfully launched RedNAND
16. Reboot into SysNAND and get into the Homebrew Launcher through the entrypoint of your choice (menuhax will always launch the Homebrew Launcher from SysNAND)
17. Open TinyFormat
18. Press Y to format your SysNAND (Don't worry, everything is still saved on RedNAND)
19. Go through initial setup without linking your Nintendo Network ID, you want it to remain linked only to RedNAND to prevent issues
13. Create a folder named "SysNAND" on the first page of the home menu
19. Follow Part 1 to reinstall menuhax on SysNAND as the format will have removed it
14. Boot RedNAND, then change your theme in RedNAND to uninstall menuhax from RedNAND; it can cause problems if you don't and having a different theme on each will help you to tell them apart
13. **If you see the SysNAND folder, then you are not on RedNAND. DO NOT UPDATE, FIND WHAT WENT WRONG**
10. Update your **RedNAND** to the latest version using system settings (**DO NOT ENTER DATA MANAGEMENT OR EXIT SYSTEM SETTINGS AS THIS WILL REBOOT YOU INTO SYSNAND**)
11. Open the eShop on RedNAND at least once to allow it to initialize databases (you don't need to sign in)
15. As your 3DS is setup right now, you must launch CakesFW from the Homebrew Launcher every time you want to boot RedNAND; by the end of the guide you will boot into CFW SysNAND by default instead of SysNAND
