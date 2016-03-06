#### What you need

* A working emuNAND and CFW (you should have gotten this with Part 3)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [sysUpdater](https://github.com/profi200/sysUpdater/releases/)
* The latest release of [TinyFormat](https://github.com/javimadgit/TinyFormat/releases)
* The latest release of [OTPHelper](https://github.com/d0k3/OTPHelper/releases)
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases)* The latest version of [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* The 2.1.0 firmware zip file for your device and region:
 +    [Old 3DS or 2DS 2.1.0 - EUR](https://mega.nz/#!MhcxXJKA!xcx62RvFiu7oKzCveqxUlDX1icv9UI-7BB1MoiWfn-Q
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDajdOM1QyQlhjRUk/view?usp=sharing))    
 +    [Old 3DS or 2DS 2.1.0 - JAP](https://mega.nz/#!Ix9Fnb6Q!33ujhZnFLL48aY6mE_jEXuMFtCB7cugdg1eRH1geK94
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDYzBIckVEcW5IcW8/view?usp=sharing))    
 +    [Old 3DS or 2DS 2.1.0 - USA](https://mega.nz/#!EpExwB6K!jfMSznN3_aT14N7LyM_BDBonBQz0mQTs0fx5pURoneU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDWWtBODVzQWxpZ3c/view?usp=sharing)) 

#### Instructions

##### Section I - Prep Work

1. Copy the `OTPHelper` folder from the OTPHelper zip, the `TinyFormat` folder from the TinyFormat zip, and the `Decrypt9WIP` folder from the Decrypt9 zip to the `/3ds/` folder on your SD card
2. Copy `sysUpdater.cia` from the sysUpdater zip, and`arm11.bin` and `arm9.bin` from the OTPHelper zip to the root of your SD card
3. Copy the `3ds` folder and `FBI.cia` file from the FBI zip to the root of your SD card 
3. From SysNAND, get into the Homebrew Launcher through the entrypoint of your choice
4. Open OTPHelper
5. Go to "NAND Backup & Restore"
6. Backup SysNAND and EmuNAND to `sysNAND.bin` and `emuNAND.bin` respectively
7. Press Select on the main menu to eject your SD card
8. Put your SD card in your computer, then copy over `sysNAND.bin`, `emuNAND.bin`, and the `Nintendo 3DS` folder to a safe folder on your computer, you will need them later
9. Delete `emuNAND.bin` from your SD card; do not delete `sysNAND.bin`
3. **Make sure your WiFi is on (it has not been disabled from the SysNAND home menu settings), you will not be able to toggle it in 2.1**
4. Boot your 3DS into EmuNAND using any CFW (if you followed Part 3 of this guide, you can do this by launching AuReiNAND from the homebrew launcher)
5. Get into the Homebrew Launcher **on EmuNAND** through an entrypoint that is launched **after EmuNAND has booted**, such as [browserhax](https://yls8.mtheall.com/3dsbrowserhax.php) **(if you do not, TinyFormat will format your SysNAND)**
6. Open TinyFormat **on EmuNAND**
7. Press Y to format **EmuNAND**
8. Reboot back into EmuNAND and complete initial setup *without* signing into your Nintendo Network ID
9. **Repeat steps 14 through 17, this is not optional (in other words, you must TinyFormat your EmuNAND twice - if you do not, you will most likely brick your device when you downgrade)**
10. Remove any TWL modifications done to the device or sysUpdater will throw an error (most users will not have to worry about this)
10. Update your **EmuNAND** to the latest version using system settings if it is not already
11. Open the eShop at least once to allow it to initialize databases
12. Get into the Homebrew Launcher on EmuNAND through the entrypoint of your choice
11. Open Decrypt9, then go to "EmuNAND File Options", then select the "Dump Health & Safety" option
12. Press Select to eject your SD card, then put it in your computer
13. Extract Universal Inject Generater, then copy both `hs.app` from your SD card and `FBI.cia` from the FBI zip to the `input` folder
14. Double click `go.bat`
15. Copy `FBI_inject_with_banner.app` to the root of your SD card and reinsert your SD card into your 3DS
16. Press B on Decrypt9, then go to "EmuNAND File Options" and select the "Inject Health & Safety" option
17. Press down once to select `FBI_inject_with_banner.app`, then press A to inject
18. Press start, then reboot into EmuNAND
19. Launch the Health and Safety Application (which is now FBI)
20. Navigate to `sysUpdater.cia` and press A to install

##### Section II - Downgrading
26. Reboot into SysNAND, then get into the Homebrew Launcher through the entrypoint of your choice
27. Open OTPHelper, then go to "Nand Backup and Restore", then select the "EmuNAND Backup" option
28. Backup your emuNAND to `emuNAND.bin`
29. Press Select on the main menu to eject your SD card
23. Put your SD card in your computer, then rename `emuNAND.bin` on the root of your SD card to `emuNAND_formatted.bin`
26. Copy over `emuNAND_formatted.bin` to a safe folder on your computer
24. Delete any existing `updates` folder from your SD card root that may be leftover from a previous downgrade or update
25. Copy the `updates` folder from the 2.1.0 firmware zip to the root of your SD card
27. Reinsert your SD card into your 3DS then press Start and reboot into emuNAND
28. Open sysUpdater **on emuNAND**
29. Press Y to downgrade emuNAND to 2.1.0
30. If you encounter an error at any point during the downgrade, restore your emuNAND backup from `emuNAND_formatted.bin` using OTPHelper through the Homebrew Menu on SysNAND. Afterwards, you can retry the downgrade on EmuNAND, restoring from backup whenever it fails until it goes through successfully. *This downgrade process can take many many tries in some situations, just keep trying until it works*
31. **If, after many tries, you repeatedly fail on 0004003000008F02.cia, you can try following the instructions [here](https://github.com/Plailect/Guide/wiki/0004003000008F02.cia)**
31. *EmuNAND will be bricked by the downgrade and you will no longer be able to get into it (a black screen when you try to load EmuNAND is normal)*
32. Reboot into SysNAND, then get into the Homebrew Launcher through the entrypoint of your choice
33. Go to the "NAND Backup & Restore" option in OTPHelper, then backup EmuNAND to `emuNAND.bin`
34. Go to the "NAND Backup & Restore" option in OTPHelper, then flash the 2.1 Unbricked NAND to your SysNAND by restoring SysNAND from `emuNAND.bin`
35. Cross your fingers
36. Reboot
37. If you get a black screen, boot with the SD card removed then reinsert after successful boot.

##### Section III - Getting the OTP

1. Go to `http://dukesrg.github.io/2xrsa.html?arm11.bin` on your 3ds
2. OTPHelper will launch, then select the "Dump otp.bin (0x108) (< 3.0)" option
3. Press Select on the main menu to eject your SD card
4. Put your SD card in your computer, then rename `otp.bin` to `otp0x108.bin`
5. Copy over `otp0x108.bin` to a safe folder on your computer.
6. Reinsert your SD card into your 3DS then press B to return to the main menu
7. Select the "Dump otp.bin (0x100) (< 3.0)" option
8. Press Select on the main menu to eject your SD card
9. Put your SD card in your computer, then copy over `otp.bin` to a safe folder on your computer
10. Ensure that `otp.bin` is 256 bytes and `otp0x108.bin` is 264 bytes
11. Backup `otp.bin` and `otp0x108.bin` to multiple locations (such as online file storage)

##### Section IV - Restoring the System
1. Rename `emuNAND.bin` on the root of your SD card to `emuNAND_2-1-0.bin` and copy it to a safe folder on your computer so you can downgrade back to 2.1.0 easily if you ever need to. You can delete `emuNAND_2-1-0.bin` from your SD card.
1. Copy the `emuNAND.bin` you created at the beginning of Section I to the root of your SD card
2. Delete the folders from the inside of the `Nintendo 3DS` folder on your SD card that are **not** in the `Nintendo 3DS` folder you copied to your computer in Section I (the `Nintendo 3DS` folder on your SD card should now look the same as the one from Section I)
2. Reinsert your SD card into your 3DS then press B to return to the main menu
3. Go to "NAND Backup & Restore"
4. Restore SysNAND and EmuNAND from `sysNAND.bin` and `emuNAND.bin` respectively
5. Cross your fingers
6. Reboot!