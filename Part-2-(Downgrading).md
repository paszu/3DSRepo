This part of the guide will take you through the process of downgrading to 9.2.0 (the latest version which gives us full control of the system) using sysUpdater.

This version of sysUpdater (which is compatible with >9.2.0 systems) uses an unstable exploit, and because of this it may take many tries just to load the button prompts.

If sysUpdater crashes at any point during the downgrade (which can happen occasionally), you can power off the system by holding the power button. You will be left with what's called a "partial downgrade" or "partial", which is recoverable.

Although a partially downgraded system may show 9.2.0 as the system version, you are not done. You must restart from the beginning and downgrade a second time to install any files that were not installed. Browserhax will work for partial downgrades as long as you are using the recommended version of sysUpdater.

**You MUST downgrade with the correct pack for your console/region or you will BRICK.**

#### What you need

* The Homebrew Launcher and an installed entrypoint (such as menuhax)
* The latest release of [PlaiSysUpdater](https://github.com/Plailect/PlaiSysUpdater/releases/)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The 9.2.0 firmware pack zip file for your device and region:
 +    [New 3DS 9.2.0 - EUR](https://mega.nz/#!F4U32b4B!tPhl3G0HEmzg5Pd5zQ29ndf1icQqU_LBoogygSL13EY
) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDOWpMTWdybzF3TUU))    
 +    [New 3DS 9.2.0 - JAP](https://mega.nz/#!VxcF3TIK!Bm5LgFxo5V4Nepe9ZlWnx7bichE1V7p7pR_HqwimU5M
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDU2plUWwxa2gtV0E/view?usp=sharing))    
 +    [New 3DS 9.2.0 - USA](https://mega.nz/#!gslWiIoK!SF7uFk9rzWTK6oitCDoeAdvphcCzhKWsnTAMXw7zwOU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDbEV2aTRjb1oxekE/view?usp=sharing))        
~    
 +    [Old 3DS or 2DS 9.2.0 - EUR](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    [Old 3DS or 2DS 9.2.0 - JAP](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    [Old 3DS or 2DS 9.2.0 - USA](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))

#### Instructions

**If you are already on 9.2.0-20, skip to step 18.**

1. Copy and merge the `3ds` folder from the PlaiSysUpdater zip to root of your SD card
2. Copy and merge the `3ds` folder from the EmuNAND9 zip to root of your SD card
2. Delete any existing `updates` folder from your SD card if there is one
3. Copy the `updates` folder from the 9.2.0 firmware zip to the root of your SD card
4. Eject your SD card and put it back in your 3DS
5. Boot into the Homebrew Launcher (if you followed the previous part, you can do this by holding dpad down on boot)
6. Open sysUpdater
7. If you do not see the button prompts, power off your 3DS by holding the power button and try again (this can take many tries)
8. If you see button prompts, proceed
9. Press Y to downgrade to 9.2.0
10. Wait; do not touch anything even if it appears to freeze
10. If, after around 30 seconds, it is still frozen, it is safe to power off and try again
11. If you get an error before installation, power off your 3DS by holding the power button and try again (this can take many tries)
12. If you get an error in the middle of installation, follow the instructions in the beginning for partial downgrades
13. If you freeze on the "Rebooting in 10 seconds" line for longer than 10 seconds, it is safe to power off your 3DS by holding the power button
14. If you get a black screen after downgrading, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_sys_down); when you have booted, put the SD card back in, change your theme to anything else, then change it back to remove the old menuhax version
14. Follow the steps in Part 1 to reinstall menuhax
15. Check the system settings, you should be on 9.2.0
16. Launch the Homebrew Launcher using the entrypoint of your choice (such as menuhax)
17. Open EmuNAND9 **(This can sometimes take a few tries)**
18. Go to EmuNAND Manager Options, then backup SysNAND to `sysNAND.bin`
20. Press Select on the main menu to eject your SD card
21. Put your SD card in your computer, then copy `sysNAND.bin` to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong in the future **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
22. You can delete `sysNAND.bin` from your SD card after copying it
23. Reinsert your SD card into your 3DS, then press Start to reboot