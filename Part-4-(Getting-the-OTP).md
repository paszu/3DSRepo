**If you somehow get yourself stuck on 2.1.0, read all information on [this](https://github.com/Plailect/Guide/wiki/3DS-Stuck-(2.1.0-Without-Functional-Browser)) page before attempting anything. It could save you from a brick!**

The OTP is a console unique region from which console specific keys seem to be derived, although it is unknown how.

The OTP is a requirement to use arm9loaderhax, which gets you, among other things, 100% boot rate, RedNAND boot speed almost as fast as regular sysNAND (using something like Luma3DS), and very early Arm9 access. In the future, this will allow for running things like Decrypt9 to unbrick yourself without a hardmod and other awesome tools.

Since version 3.0, the OTP is locked out early in sysNAND boot. There is a New 3DS only exploit that works on 9.6, but it requires extra hardware. The solution we are using is to downgrade RedNAND (to ensure we don't partial downgrade) to 2.1, then flash RedNAND to sysNAND to get the OTP.

If you have an existing EmuNAND, you can follow this part without switching to RedNAND by following all RedNAND steps as if they said EmuNAND.

More info [here](https://github.com/Plailect/Guide/wiki/OTP-Info) and [here](https://3dbrew.org/wiki/OTP_Registers).

**Your RedNAND SecureInfo_A MUST be the same as your SysNAND SecureInfo_A or you will BRICK. If you have changed your RedNAND region or otherwise modified SecureInfo_A in any way, you MUST create a NEW RedNAND or you will BRICK.**

**You MUST downgrade with the correct pack for your console region or you will BRICK.**

*If you are using ReiNand, you MUST be using the latest version (v4.1 or above) or you will be unable to downgrade NATIVE_FIRM on EmuNAND/RedNAND and PlaiSysUpdater will fail 100% of the time.*

**If you are using Luma3DS and DID NOT follow Part 3, you should copy the appropriate `firmware.bin` from Part 3 to the `/luma/` folder on your SD card, otherwise the downgrade will fail.**

#### Overview of steps

In this section, we will be downgrading to 2.1.0 in order to take advantage of an oversight in 2.1.0 for the purpose of extracting the [OTP](https://github.com/Plailect/Guide/wiki/OTP-Info) unique to your console. This OTP file is required to install arm9loaderhax, and **cannot** be shared with other consoles.

This is accomplished by making backups of both RedNAND and SysNAND, then preparing them for downgrading. We prepare for downgrading by putting all files for various needed applications on the SD card (including injecting FBI, which is an installer for applications in CIA format), then formatting the RedNAND.

We use the RedNAND for the actual downgrade procedure, rather than SysNAND, because if something installs improperly or goes wrong then you are left with a broken RedNAND (which can be easily restored from SysNAND) rather than being left with a broken SysNAND which would be a brick (nonfunctional console).

Before downgrading the RedNAND, we first format it twice (after making a backup). The formatting itself is done to avoid any conflicts with installed user titles and further increase the safety of the process.

The reason we format twice, rather than just once, is because RedNAND and SysNAND are determined to be linked if they have both been formatted the same number of times.

In the case of most users, since you formatted SysNAND in Part 3, formatting the RedNAND will bring the format count for each NAND up to 1 format which will relink them and cause them to read from the same SD card folders. In our testing, linked NANDs exhibited weird behaviors during the 2.1.0 downgrade process, and because of this we format RedNAND a second time to unlink them again.

Once prepared, the RedNAND is then downgraded to the Old 3DS 2.1.0 firmware. We then use OTPHelper, a handy tool once again created by [d0k3](https://github.com/d0k3/), to do the rest of the 2.1.0 setup by running its One Click Setup.

This setup first checks to see if the console is a New 3DS, and if it finds one it applies some unbricking steps (swapping a NAND header and fixing encryption types) to allow the New 3DS to run an Old 3DS only firmware (since New 3DS shipped with the firmware 8.1.0).

After this New 3DS check, it then (on all consoles) verifies application hashes in RedNAND to ensure the 2.1.0 downgrade successfully completed before copying our RedNAND to SysNAND. It then does some final checks to ensure everything completed successfully, then allows you to reboot.

Upon booting 2.1.0, we use a browser-based arm9 kernel exploit (["2xrsa"](https://github.com/b1l1s/2xrsa) by [Bilis](https://github.com/b1l1s)) to boot OTPHelper and dump the console unique OTP before restoring our SysNAND from backup to go back to 9.2.0.

#### What you need

* A working RedNAND and CFW (you should have gotten this with Part 3)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [PlaiSysUpdater](https://github.com/Plailect/PlaiSysUpdater/releases/)
* The latest release of [TinyFormat](https://github.com/javimadgit/TinyFormat/releases)
* The latest release of [OTPHelper](https://github.com/d0k3/OTPHelper/releases/)
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases/)
* The latest version of [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* The 2.1.0 firmware zip file for your device and region:
 +    [New 3DS / Old 3DS or 2DS 2.1.0 - EUR](https://mega.nz/#!MhcxXJKA!xcx62RvFiu7oKzCveqxUlDX1icv9UI-7BB1MoiWfn-Q) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDajdOM1QyQlhjRUk/view?usp=sharing))    
 +    [New 3DS / Old 3DS or 2DS 2.1.0 - JAP](https://mega.nz/#!Ix9Fnb6Q!33ujhZnFLL48aY6mE_jEXuMFtCB7cugdg1eRH1geK94) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDYzBIckVEcW5IcW8/view?usp=sharing))   
 +    [New 3DS / Old 3DS or 2DS 2.1.0 - USA](https://mega.nz/#!EpExwB6K!jfMSznN3_aT14N7LyM_BDBonBQz0mQTs0fx5pURoneU) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDWWtBODVzQWxpZ3c/view?usp=sharing))    

#### Instructions

##### Section I - Prep Work

1. **Right now is a good time to use a [save manager](https://github.com/meladroit/svdt/releases) to backup any saves you care about (do steps 10 - 18 then install the [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases) CIA) (just in case something goes wrong unexpectedly)**
1. Copy both the `OTPHelper` folder from the OTPHelper zip and the `Decrypt9WIP` folder from the Decrypt9 zip to the `/3ds/` folder on your SD card
2. Copy `PlaiSysUpdater.cia` from the PlaiSysUpdater zip, `TinyFormat.cia` from the TinyFormat zip, and `arm11.bin` and `arm9.bin` from the OTPHelper zip to the root of your SD card
18. Reinsert your SD card into your 3DS, then boot your 3DS into RedNAND using any CFW (if you followed Part 3 of this guide, you can do this by launching Luma3DS from the HomeBrew Launcher)
11. **MAKE SURE YOU ARE IN RedNAND (IF YOU FOLLOWED PART 3, MAKE SURE THAT YOU SEE "EMU" IN FRONT OF THE VERSION NUMBER)**
10. Update your **RedNAND** to the latest version using system settings if it is not already (**DO NOT ENTER SD CARD MANAGEMENT OR EXIT SYSTEM SETTINGS AS THIS WILL REBOOT YOU INTO SYSNAND**)		
12. Reboot into SysNAND
3. **Make sure your WiFi is on (it has not been disabled from the SysNAND home menu settings), you can only toggle it by pulling the battery which resets it to be on**
2. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
11. Open Decrypt9 **(This can sometimes take a few tries)**, then go to "EmuNAND Options", then select the "Health & Safety Dump" option to dump Health & Safety to `hs.app` **(you can use Up and Down / Left and Right to change the name)**
12. Press Select to eject your SD card, then put it in your computer
13. Extract Universal Inject Generator, then copy both `hs.app` from your SD card and `FBI.cia` from the FBI zip to the `input` folder
14. Double click `go.bat` *(or  execute `go.sh`with Terminal on Linux / Mac)*
15. Copy `FBI_inject_with_banner.app` to the root of your SD card and reinsert your SD card into your 3DS
16. Press B on Decrypt9, then go to "EmuNAND Options" and select the "Health & Safety Inject" option
17. Press down once to select `FBI_inject_with_banner.app`, then press A and confirm to inject
18. Go to the main menu, then press Start to reboot
19. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
20. Open OTPHelper (this can take a few tries in some situations)
21. Go to "NAND Backup & Restore"
19. Backup EmuNAND to `emuNAND_original.bin` **(you can use Up and Down / Left and Right to change the name)**
29. Backup SysNAND to `sysNAND_original.bin`
7. Press Select on the main menu to eject your SD card
8. Put your SD card in your computer, then copy over `sysNAND_original.bin` and `emuNAND_original.bin` to a safe folder on your computer, you will need them later **(Your backups should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if they do not, you should delete them and make new ones!)**
9. Delete `emuNAND_original.bin` from your SD card
9. If you have a small SD card and require space, also delete `sysNAND_original.bin` from your SD card
18. Reinsert your SD card into your 3DS, press Start and right at the same time to reboot, then boot your 3DS into RedNAND using any CFW (if you followed Part 3 of this guide, you can do this by launching Luma3DS from the HomeBrew Launcher)
19. Launch the Health and Safety Application (which is now FBI) on RedNAND
20. Navigate to SD then `TinyFormat.cia` and press A to install
21. Press home to exit FBI, then launch TinyFormat using the home menu icon
7. Press Y to format **RedNAND**
8. Reboot back into RedNAND and complete initial setup *without* signing into your Nintendo Network ID
9. **Repeat steps 28 through 32, this is not optional (in other words, you must TinyFormat your RedNAND twice - if you do not, your device may brick when you downgrade)**
10. Remove any TWL modifications done to the device or PlaiSysUpdater will throw an error      
(if you have no idea what this is, don't worry about it; most users will not need to do this)
19. Launch the Health and Safety Application (which is now FBI)
20. Navigate to SD then `PlaiSysUpdater.cia` and press A to install

##### Section II - Downgrading
26. Reboot into SysNAND, then get into the Homebrew Launcher through the entrypoint of your choice
27. Open OTPHelper, then go to "NAND Backup and Restore", then select the "EmuNAND Backup" option
28. Backup your RedNAND to `emuNAND_formatted.bin`
29. Press Select on the main menu to eject your SD card
23. Put your SD card in your computer, then copy over `emuNAND_formatted.bin` to a safe folder on your computer
24. Delete any existing `updates` folder from your SD card root that may be left over from a previous downgrade or update
25. Copy the `updates` folder from the 2.1.0 firmware zip to the root of your SD card
27. Reinsert your SD card into your 3DS, press Start and right at the same time to reboot, then boot your 3DS into RedNAND using any CFW
28. Open PlaiSysUpdater **on RedNAND**
29. Press X to downgrade RedNAND to 2.1.0    
  + **If you encounter an error in downgrading related to NFIRM, make sure you have read the information just above the "Overview of steps" and done all relevant instructions**
30. If you encounter an error at any point during the downgrade, restore your RedNAND backup from `emuNAND_formatted.bin` using OTPHelper through the Homebrew Menu on SysNAND. Afterwards, you can retry the downgrade on RedNAND, restoring from backup whenever it fails until it goes through successfully. *This downgrade process can take many many tries in some situations, just keep trying until it works*     
31. **RedNAND will be bricked by the downgrade on New 3DS (not on Old 3DS), but you will no longer be able to get into it on either since no current CFW can boot a 2.1.0 RedNAND (a black screen when you try to load RedNAND is normal)**
32. Reboot into SysNAND, then get into the Homebrew Launcher through the entrypoint of your choice
33. Open OTPHelper
33. Select "One Click Setup" and confirm (you do not need to do an extra backup if asked, but you should make sure that you have copied the backup you made earlier to your computer as you **will** need it later). This can take a while.         
**(If this fails or gives you an error do NOT continue or you may BRICK; you should [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_otphelper_verify_fail))**
35. Cross your fingers
36. Reboot
37. If you get a black screen, boot with the SD card remove then reinsert when you see the home menu. If this fails, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_sys_down)

##### Section III - Getting the OTP

*(On 2DS at 2.1.0, the screen being stretched is normal)*

**There have been multiple reports of bricks caused by leaving a 2.1.0 New 3DS in sleep mode for long periods of time. Because of this, you should avoid leaving the device in sleep mode and could complete the remainder of Part IV without delay (this strictly applied to devices left in sleep mode for long periods of time, not devices that are being used).**

1. Go to `http://dukesrg.github.io/2xrsa.html?arm11.bin` on your 3DS
2. OTPHelper will launch, then select the "Dump otp.bin (0x100)" option
3. Press Select on the main menu to eject your SD card
4. Put your SD card in your computer, then copy over `otp.bin` to a safe folder on your computer.		
10. Ensure that `otp.bin` is 256 bytes
11. Backup `otp.bin` to multiple locations (such as online file storage)

##### Section IV - Restoring the System
2. Copy your `sysNAND_original.bin` backup from Section I to the root of your SD card
2. Reinsert your SD card into your 3DS then press B to return to the main menu
3. Go to "NAND Backup & Restore"
4. Restore SysNAND from `sysNAND_original.bin`
5. Cross your fingers
6. Reboot!