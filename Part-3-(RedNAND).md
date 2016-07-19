This part of the guide will use two terms you must be familiar with in order to understand what's going on: SysNAND and RedNAND (named for redirected NAND). The term SysNAND refers to a physical chip inside your 3DS which contains all system software, the OS, the bootloader, and so on (games, themes, and save files for installed games are stored and encrypted on the SD card). Doing something sketchy to your SysNAND, even if it's just removing a system title, can result in a bricked 3DS (it becomes as useful as a brick).

Because of this, we keep the 9.2.0 SysNAND as it is, but we copy it to a partition on your SD card then redirect to it when any Custom Firmware (CFW) is launched. Using this method, you can unlink theses two NANDs and have a fully exploitable 9.2.0 system that can launch a secondary OS at the latest version which is then patched to allow exploits to work.

If your SysNAND is ever broken, you have a bricked system, but if your RedNAND is broken, you will only have bricked the RedNAND which is easy to fix. A SysNAND brick can only be recovered by soldering internal components and writing an existing SysNAND backup from your computer to the internal memory (or by using arm9loaderhax), but RedNAND bricks can be recovered just by using a homebrew application such as EmuNAND9 to restore your RedNAND from backup.

RedNAND, since it is completely separate from your SysNAND, can be updated to the latest version, allowing you to play all games on an exploited system.

**Unfortunately, RedNAND has its own set of [drawbacks](https://www.reddit.com/r/3dshacks/comments/49qj9w/arm9loaderhax_if_you_dont_like_sysnand_permahax/d0ud80d), which is why we only take advantage of it for the purpose of safely getting our OTP before setting up arm9loaderhax and CFW SysNAND, which is far superior.**

This part of the guide will take you through the process of setting up RedNAND and a CFW on your SD card and device, then through the process of formatting one of the NANDs to unlink them from each other.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

#### Overview of steps

This section will take you through the steps of setting up a CFW ("Custom Firmware"), specifically Luma3DS by [AuroraWright](https://github.com/AuroraWright/), which can boot a RedNAND partition off the SD card. This requires access to arm9 kernel, and is one of the reasons we downgraded to 9.2.0 earlier.

The actual creation of the RedNAND is handled by an application called EmuNAND9 by [d0k3](https://github.com/d0k3/) which formats your SD card to contain a partition on it which houses a copy of your system's internal memory (NAND Chip).

The NAND does *not* contain any of your user content (games, saves, dlc, themes, etc), rather just all system titles, some console unique files, and a "link" to the folder on your SD card which *does* contain all of your user content. This "link" is what is replaced during a system format, causing the 3DS to look in a new folder for content (with a different encryption key so other NANDs can't use it).

In this process, we will copy the NAND containing this link to your RedNAND and format the SysNAND then perform a process called "unlinking," which is when you format one NAND to completely separate the NANDs from each other, ensuring they do not try to use the same SD card folder, which can cause many weird side effects.

Following this, we update the RedNAND, but not the SysNAND since we still need access to that to perform the arm9 kernel exploit, to the latest version.

#### What you need

* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The latest release of [TinyFormat](https://github.com/javimadgit/TinyFormat/releases)
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases)

#### Instructions

2. Copy the `Luma3DS.dat` file, the `3ds` folder, and the `luma` folder from the Luma3DS zip to the root of your SD card
1. Copy and merge the `3ds` folder from the EmuNAND9 zip to the root of your SD card
2. Copy and merge the `3ds` folder from the TinyFormat zip to the root of your SD card
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
12. Open Luma3DS (this can sometimes black screen, just try again)
14. Activate "Show current NAND in System Settings"
15. Press Start to boot RedNAND     
  + You must launch Luma3DS from the Homebrew Launcher every time you want to boot RedNAND
  + Be patient, this initial boot has been reported take as long as two minutes for some users!
13. If you boot into the home menu, you have successfully launched RedNAND
16. Reboot into SysNAND and get into the Homebrew Launcher through the entrypoint of your choice (menuhax will always launch the Homebrew Launcher from SysNAND)
17. Open TinyFormat
18. Press Y to format your SysNAND (Don't worry, everything is still saved on RedNAND)
19. Go through initial setup without linking your Nintendo Network ID, you want it to remain linked only to RedNAND to prevent issues
19. Reinstall menuhax on SysNAND as the format will have removed it
14. Boot RedNAND
14. Open System Settings
15. Make sure your DNS settings are on Auto-Obtain
13. **If you do not see "Emu" in front of the version number, then you are not on RedNAND. DO NOT UPDATE, FIND WHAT WENT WRONG**
10. Update your **RedNAND** to the latest version using System Settings by going to the fourth page of "Other Settings" and selecting "System Update" (**Once you exit System Settings / SD Card Management you will be returned to SysNAND, make sure to enter back into RedNAND before updating!**)
15. As your 3DS is setup right now, you must launch Luma3DS from the Homebrew Launcher every time you want to boot RedNAND; by the end of the guide you will boot into CFW SysNAND by default instead of having to use RedNAND
