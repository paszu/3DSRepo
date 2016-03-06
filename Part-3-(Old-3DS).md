This part of the guide will use two terms you must be familiar with in order to understand what's going on: SysNAND and EmuNAND. The term SysNAND refers to a physical chip inside your 3DS which contains all system software, the OS, the bootloader, and so on (games, themes, and save files for installed games are stored and encrypted on the SD card). Doing something sketchy to your SysNAND, even if it's just removing a system title, can result in a bricked 3DS (it becomes as useful as a brick).

Because of this, we keep the 9.2.0 SysNAND as it is, but we copy it to a partition on your SD card then redirect to it when any Custom Firmware (CFW) is launched. Using this method, you can unlink theses two NANDs and have a fully exploitable 9.2.0 system that can launch a secondary OS at the latest version which is then patched to allow exploits to work.

If your SysNAND is ever broken, you have a bricked system, but if your EmuNAND is broken, you will only have bricked the EmuNAND which is easy to fix. A SysNAND brick can only be recovered by soldering internal components and writing an existing SysNAND backup from your computer to the internal memory, but EmuNAND bricks can be recovered just by using a homebrew application such as EmuNAND9 to restore your EmuNAND from backup.

EmuNAND, since it is completely separate from your SysNAND, can be updated to the latest version, allowing you to play all games on an exploited system.

This part of the guide will take you through the process of setting up EmuNAND and a CFW on your SD card and device, then through the process of formatting one of the NANDs to unlink them from each other.

#### What you need

* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [TinyFormat](https://github.com/javimadgit/TinyFormat/releases)
* The latest release of [AuReiNAND](https://github.com/AuroraWright/AuReiNand/releases)
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases)
* The latest version of [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* The Old 3DS AuReiNAND NTR [firmware bin](https://mega.nz/#!04lmVQxD!7IMsl4ChzKhkEaPXhCvEPmbEq_PpD9i06EzrIjtVSIQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVFhnaVNzMlR4SVk/view?usp=sharing)) zip file

#### Instructions

1. Copy both the `3ds` folder from the EmuNAND9 zip and the `3ds` folder from the AuReiNAND zip to the root of your SD card
2. Copy the `Decrypt9WIP` folder from the Decrypt9 zip to the `/3ds/` folder on your SD card
3. Copy the `rei` folder from the AuReiNAND zip to the root of your SD card
5. Copy `ReiNand.dat` the AuReiNAND zip to the root of your SD card
4. Copy `firmware.bin` from the firmware zip to the `/rei/` folder on your SD card
2. Copy the `TinyFormat` folder from the TinyFormat zip to the `/3ds/` folder on your SD card
3. Copy the `3ds` folder from the FBI zip to the root of your SD card
4. Put a blank file named `EmuNAND.txt` in the `/Nintendo 3DS/<id0>/` folder; `<id0>` will be a long string of random characters; this will let you know which folder is SysNAND and which is EmuNAND after unlinking
3. **Backup every file on your SD card to a folder on your computer, they will be deleted in the next step**
4. Reinsert your SD card into your 3DS, then get into the Homebrew Launcher through the entrypoint of your choice
5. Open EmuNAND9
6. Select the "Complete emuNAND setup" option
9. Ignore the `starter.bin` prompt
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
14. Change your theme in EmuNAND to uninstall menuhax from EmuNAND; it can cause problems if you don't and having a different theme on each will help you to tell them apart
10. Update your **EmuNAND** to the latest version using system settings
11. Open the eShop at least once to allow it to initialize databases
19. Follow Part 1 to reinstall menuhax on SysNAND
12. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
11. Open Decrypt9, then go to "EmuNAND File Options", then select the "Dump Health & Safety" option
12. Press Select to eject your SD card, then put it in your computer
13. Extract Universal Inject Generater, then copy both `hs.app` from your SD card and `FBI.cia` from the FBI zip to the `input` folder
14. Double click `go.bat`
15. Copy `FBI_inject_with_banner.app` to the root of your SD card and reinsert your SD card into your 3DS
18. Put a blank file named `SysNAND.txt` in the `/Nintendo 3DS/<id0>/` folder that was created (not the one you did earlier)
16. Press B on Decrypt9, then go to "EmuNAND File Options" and select the "Inject Health & Safety" option
17. Press down once to select `FBI_inject_with_banner.app`, then press A to inject
18. Go to Decrypt9's main menu, the EmuNAND options, then backup EmuNAND to `emuNAND.bin`
8. Press Select on the main menu to eject your SD card
10. Copy `emuNAND.bin` to a safe folder on your computer
10. Reinsert your SD card into your 3DS, then press Start to reboot
15. As your 3DS is setup right now, you must launch AuReiNAND from the Homebrew Launcher every time you want to boot EmuNAND; by the end of the guide you will boot into EmuNAND by default instead of SysNAND