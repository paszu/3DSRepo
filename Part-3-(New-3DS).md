This part of the guide will use two terms you must be familiar with in order to understand what's going on: SysNAND and EmuNAND. The term SysNAND refers to a physical chip inside your 3DS which contains all system software, the OS, the bootloader, and so on (games, themes, and save files for installed games are stored and encrypted on the SD card). Doing something sketchy to your SysNAND, even if it's just removing a system title, can result in a bricked 3DS (it becomes as useful as a brick).

Because of this, we keep the 9.2.0 SysNAND as it is, but we copy it to a partition on your SD card then redirect to it when any Custom Firmware (CFW) is launched. Using this method, you can unlink theses two NANDs and have a fully exploitable 9.2.0 system that can launch a secondary OS at the latest version which is then patched to allow exploits to work.

If your SysNAND is ever broken, you have a bricked system, but if your EmuNAND is broken, you will only have bricked the EmuNAND which is easy to fix. A SysNAND brick can only be recovered by soldering internal components and writing an existing SysNAND backup from your computer to the internal memory, but EmuNAND bricks can be recovered just by using a homebrew application such as EmuNAND9 to restore your EmuNAND from backup.

This part of the guide will take you through the process of setting up EmuNAND and a CFW on your SD card and device.

#### What you need



#### Instructions

