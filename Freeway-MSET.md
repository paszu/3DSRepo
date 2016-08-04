Most 3DS CFW applications and software are designed for use with a SysNAND version between 9.0.0 and 9.2.0. If you are below version 9.0.0, you will need to use this guide to update your 3DS without going all the way to the latest version.    

If you are on versions 9.0.0 through 10.7.0 you can just follow the instructions [here](https://github.com/Plailect/Guide/wiki/Get-Started).

If you already have a RedNAND setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

This section of the guide is just a part of the larger [9.2.0 Update](https://github.com/Plailect/Guide/wiki/9.2.0-Update) section.

#### What you need

* DS flashcard that works on your 3DS version
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)
* The latest release of [Freeway](https://github.com/Wolfvak/freeway/releases/)
* The latest release of [sysUpdater](https://github.com/profi200/sysUpdater/releases/)
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases/)
* The latest version of [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* The 9.2.0 firmware pack zip file for your device and region:
 +    <a href="https://plailect.github.io/Guide/9.2.0-20E(Full).torrent" target="_blank">Old 3DS or 2DS 9.2.0 - EUR</a> ([mirror](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    <a href="https://plailect.github.io/Guide/9.2.0-20J(Full).torrent" target="_blank">Old 3DS or 2DS 9.2.0 - JPN</a> ([mirror](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    <a href="https://plailect.github.io/Guide/9.2.0-20U(Full).torrent" target="_blank">Old 3DS or 2DS 9.2.0 - USA</a> ([mirror](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))


#### Instructions

2. Copy `Freeway.dat` to the root of your SD card
3. Delete any existing `updates` folder from your SD card if there is one
4. Copy the `updates` folder from the 9.2.0 firmware zip to the root of your SD card
5. Copy sysUpdater.cia from the sysUpdater zip to the root of your SD card
6. Eject your SD card and put it back in your 3DS
8. Copy `Decrypt9.dat` from the Decrypt9 zip to the root of your SD card
8. Put `Decrypt9.nds` from the Decrypt9 zip on your DS flashcard
9. Start your DS flashcard from your 3DS
10. Boot `Decrypt9.nds` using your flashcart and allow it to install the MSET exploit
11. Reboot the system, then go to System Settings, then "Other Settings", then "Profile", then "Nintendo DS Profile" to load Decrypt9
10. Go to "SysNAND Options", then "Miscellaneous...", then select the "Health & Safety Dump" option to dump Health & Safety to `hs.app` **(you can use Up and Down / Left and Right to change the name)**
12. Press Select to eject your SD card, then put it in your computer
13. Extract Universal Inject Generater, then copy both `hs.app` from your SD card and `FBI.cia` from the FBI zip to the `input` folder
14. Double click `go.bat` *(or  execute `go.sh` with Terminal on Linux, or double click `Mac_inject_launcher.app` on Mac)*
15. Copy `FBI_inject_with_banner.app` to the root of your SD card and reinsert your SD card into your 3DS
16. Press B on Decrypt9, then go to "SysNAND Options", then "Miscellaneous...", and select the "Health & Safety Inject" option
17. Press down once to select `FBI_inject_with_banner.app`, then press A to inject
18. Go back to the EmuNAND file options menu in Decrypt9 *(If you have one)*
19. Backup EmuNAND to `emuNAND.bin` *(If you have one)*
19. Go to the SysNAND file options menu on the main menu
29. Backup SysNAND to `sysNAND.bin`
7. Press Select on the main menu to eject your SD card
8. Put your SD card in your computer, then rename `sysNAND.bin` and `emuNAND.bin` *(If you have one)* to `sysNAND-OLD.bin` and `emuNAND-OLD.bin` *(If you have one)*
9. Copy over `sysNAND-OLD.bin` and `emuNAND-OLD.bin` *(If you have one)* to a safe folder on your computer in case you ever want to revert to this version
10. Delete `sysNAND-OLD.bin` and `emuNAND-OLD.bin` *(If you have one)* from your SD card
18. Reinsert your SD card into your 3DS, then press Start to restart your 3DS
7. Put `Freeway.nds` from the Freeway zip on your DS flashcard
9. Start your DS flashcard from your 3DS
10. Boot `Freeway.nds` using your flashcart
10. Select the correct option for your system version
    + 4.X.X -> "4.x Freeway.dat"
    + 6.X.X -> "6.x Freeway.dat"
11. Go to System Settings, then "Other Settings", then "Profile", then "Nintendo DS Profile"
14. Your 3DS will reboot back into the home menu
25. Launch the Health and Safety Application (which is now FBI)
26. Navigate to `sysUpdater.cia` and press A to install
28. Press the home button to go to the home menu, then open the sysUpdater application and press the A button to install

You can now follow the rest of this guide from [here](https://github.com/Plailect/Guide/wiki/Get-Started).