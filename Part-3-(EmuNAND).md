This part of the guide will use two terms you must be familiar with in order to understand what's going on: SysNAND and EmuNAND. The term SysNAND refers to a physical chip inside your 3DS which contains all system software, the OS, the bootloader, and so on (games, themes, and save files for installed games are stored and encrypted on the SD card). Doing something sketchy to your SysNAND, even if it's just removing a system title, can result in a bricked 3DS (it becomes as useful as a brick).

Because of this, we keep the 9.2.0 SysNAND as it is, but we copy it to a partition on your SD card then redirect to it when any Custom Firmware (CFW) is launched. Using this method, you can unlink theses two NANDs and have a fully exploitable 9.2.0 system that can launch a secondary OS at the latest version which is then patched to allow exploits to work.

If your SysNAND is ever broken, you have a bricked system, but if your EmuNAND is broken, you will only have bricked the EmuNAND which is easy to fix. A SysNAND brick can only be recovered by soldering internal components and writing an existing SysNAND backup from your computer to the internal memory, but EmuNAND bricks can be recovered just by using a homebrew application such as EmuNAND9 to restore your EmuNAND from backup.

EmuNAND, since it is completely separate from your SysNAND, can be updated to the latest version, allowing you to play all games on an exploited system.

This part of the guide will take you through the process of setting up EmuNAND and a CFW on your SD card and device, then through the process of formatting one of the NANDs to unlink them from each other.

#### What you need

* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [TinyFormat](https://github.com/javimadgit/TinyFormat/releases)
* The latest release of [AuReiNAND](https://github.com/AuroraWright/AuReiNand/releases)
* *New 3DS:* AuReiNAND NTR [firmware bin](https://mega.nz/#!p0tTDJIQ!aikEtlvB8cjq-aJG9jC6GKx4uvlwN6oI9X2m1OY_ylE) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDM016eHZBQV95anc/view?usp=sharing)) zip file
* *Old 3DS:* AuReiNAND NTR [firmware bin](https://mega.nz/#!04lmVQxD!7IMsl4ChzKhkEaPXhCvEPmbEq_PpD9i06EzrIjtVSIQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVFhnaVNzMlR4SVk/view?usp=sharing)) zip file

#### Instructions

1. Copy both the `3ds` folder from the EmuNAND9 zip and the `3ds` folder from the AuReiNAND zip to the root of your SD card
3. Copy the `rei` folder from the AuReiNAND zip to the root of your SD card
5. Copy `ReiNand.dat` the AuReiNAND zip to the root of your SD card
4. Copy `firmware.bin` from the firmware zip to the `/rei/` folder on your SD card
2. Copy the `TinyFormat` folder from the TinyFormat zip to the `/3ds/` folder on your SD card
4. Put a blank file named `EmuNAND.txt` in the `/Nintendo 3DS/<id0>/` folder; `<id0>` will be a long string of random characters; this will let you know which folder is SysNAND and which is EmuNAND after unlinking; if you do not know which one is EmuNAND, it is generally the larger folder
3. **Backup every file on your SD card to a folder on your computer, all files will be deleted in the next step**
4. Reinsert your SD card into your 3DS, then get into the Homebrew Launcher through the entrypoint of your choice
5. Open EmuNAND9
6. Select the "Complete emuNAND setup" option
9. Ignore the `starter.bin` prompt and continue
7. Wait
8. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy all your files back into it
10. Reinsert your SD card into your 3DS, then press Start to reboot
11. Get into the Homebrew Launcher through the entrypoint of your choice
12. Open AuReiNAND
13. If you boot into the home menu, you have successfully launched EmuNAND
16. Reboot into SysNAND and get into the Homebrew Launcher through the entrypoint of your choice (menuhax will always launch the Homebrew Launcher from SysNAND)
17. Open TinyFormat
18. Press Y to format your SysNAND (Don't worry, everything is still saved on EmuNAND)
19. Go through initial setup without linking your Nintendo Network ID, you want it to remain linked only to EmuNAND to prevent issues
13. Create a folder named "SysNAND" on the first page of the home menu
19. Follow Part 1 to reinstall menuhax on SysNAND as the format will have removed it
14. Boot EmuNAND, then change your theme in EmuNAND to uninstall menuhax from EmuNAND; it can cause problems if you don't and having a different theme on each will help you to tell them apart
13. **If you see the SysNAND folder, then you are not on EmuNAND. DO NOT UPDATE, FIND WHAT WENT WRONG**
10. Update your **EmuNAND** to the latest version using system settings
11. Open the eShop on EmuNAND at least once to allow it to initialize databases
15. As your 3DS is setup right now, you must launch AuReiNAND from the Homebrew Launcher every time you want to boot EmuNAND; by the end of the guide you will boot into EmuNAND by default instead of SysNAND