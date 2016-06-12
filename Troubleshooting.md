If you are unable to boot your 3DS, please look for the section relevant to you, and follow the instructions. Once a solution works for you, you can proceed on with the main guide.

(The section is fairly long, try using Ctrl+F to search for your issue.)

**If you still cannot solve your issue and need to reach out for help, please upload all relevant .log files from the root of your SD card to [Up1](https://up1.ca/), then come for help prepared with a detailed description of your problem and what you've tried.**

## <a name="ts_browser" />A browser based exploit is not working
Browser based exploits (such as browserhax or 2xrsa) are often unstable and crash frequently, but they can sometimes be fixed by doing the following steps.

1. Open the browser, then open the browser settings
   1. Scroll to the bottom and Initialize Savedata (it also may be called Clear All Save Data) 
   2. Try the exploit again

## <a name="ts_safe_a9lh" />System boots directly SafeA9LHInstaller
You copied the wrong `arm9loaderhax.bin` file to your SD card (you were only supposed to copy the `3ds` folder and `SafeA9LHInstaller.dat` file from the SafeA9LHInstaller zip).

1. Use the correct `arm9loaderhax.bin`
   1. Copy `arm9loaderhax.bin` from the Luma3DS zip to the root of your SD card
   2. Reboot holding select and continue

## <a name="ts_bs_rednand" />Black screen on RedNAND boot

1. Try resetting Luma's config and fix options
   1. Delete `/luma/config.bin` from your SD card
   2. Set your options when it boots
2. Try restoring a backup to RedNAND. *(You should have one of these)*

## <a name="ts_otphelper_verify_fail" />OTPHelper fails to verify my NAND

Do the steps for the error you are getting.

####"FIRM0 hash mismatch!"

1. **STOP; DO NOT TOUCH ANYTHING; A REBOOT RIGHT NOW COULD BRICK YOU IF AN INCORRECT FIRM WAS INSTALLED TO SYSNAND**
3. Download the 2.1.0 [firm.bin](https://mega.nz/#!R0NHBBhZ!R8EjGr9aL5iL_OFoGmDpXxtoIk4bLlFxE68ioo4zLEQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVm55N1dhNmsyZjQ/view?usp=sharing))
2. On your 3DS, press B until you see the main menu
3. **Carefully** press the **SELECT** button to eject your SD card
4. **WITHOUT TURNING OFF YOUR 3DS,** take your SD card out and put it in your computer
5. Copy `firm.bin` to the root of your SD card
6. Reinsert your SD card into your 3DS
7. Press **B** until you see the main menu
8. Select "FIRM Dump & Inject..."
9. Select "EmuNAND FIRM0 Inject" from `firm.bin`
11. Select "EmuNAND FIRM1 Inject" from `firm.bin`
12. Press B until you see the main menu
13. Perform "One Click Setup"
14. If this still fails, restore SysNAND from `sysNAND_original.bin`, restore RedNAND from `emuNAND_formatted.bin` and retry from Part 4 - Section II - Step 9.

####"Validation Stage 1: FAILED" and "Validation Stage 2: FAILED"  

**THIS APPLIES ONLY TO .TMD RELATED ERRORS, NOT .APP RELATED ERRORS**    
**If you got a .app related error, you should restore SysNAND from `sysNAND_original.bin`, restore RedNAND from `emuNAND_formatted.bin` and retry from Part 4 - Section II - Step 9..**

1. Check `otphelper.log` to see which titles the TMD hash mismatches on
2. Download the latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases)
3. Copy the `GodMode9` folder from the `GodMode9` zip to the `/3ds/` folder on the root of your SD card
4. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
5. Open GodMode9 **(Be VERY careful with this tool, it can brick you if you delete something important with it)**
6. Select (on bottom screen) `emuNAND CTRNAND`
7. Select `title`
8. Select the folder which has the same 8 characters as the beginning of the title that mismatched *(for example, if you mismatched after `Checking title 0004013000003202...` then you would select the `00040130` folder)*
9. Select the folder which has the same 8 characters as the end of the title that mismatched *(for example, if you mismatched after `Checking title 0004013000003202...` then you would select the `00003202` folder)*
10. Select `content`

The latest release of OTPHelper rarely shows false positives, but if you want to you can check manually just to be sure. To do this, press A on each .tmd and select "Calculate SHA-256" to manually compare to see if at least one of the `.tmd` files in each folder match a Sha256Sum to [this list](https://gist.github.com/Plailect/a6789c6a87a2eee575da).

If, in each folder, **at least one** of the `.tmd` files matches a hash on the list, this was a a false positive and you can use the following steps. **If it is a New 3DS you should unbrick EmuNAND first.** Go to "NAND Backup & Restore" -> "Clone RedNAND to SysNAND" then use "NAND Validation Options" -> "Validate SysNAND Downgrade" and confirm your SysNAND only has the same error as EmuNAND. **If you get a NEW error after cloning RedNAND to SysNAND, restore SysNAND from `SysNAND_original.bin`, restore RedNAND from `emuNAND_formatted.bin` and retry from Part 4 - Section II - Step 9.** If you do not get a NEW error, continue with the guide, ignoring the error.

If, in any folder, **none** of the `.tmd` files match, then this was a legitimate downgrade error and you have been saved from a brick; you should restore SysNAND from `sysNAND_original.bin`, restore RedNAND from `emuNAND_formatted.bin` and retry from Part 4 - Section II - Step 9.

Check all of the titles that mismatch with this same method.

####"Validation Stage 1: SUCCESS" and "Validation Stage 2: FAILED"

This will happen due to having a fragmented NAND (caused by various things such as rxTools' shitty FBI injection or some Gateway software). OTPHelper cannot check the files of a fragmented NAND, but if you got "Validation Stage 1: SUCCESS" then "Validation Stage 2: FAILED" will rarely be an anything but a false positive.

You can either flash to SysNAND at your own risk, or attempt to defragment your NAND by using Decrypt9 to dump your CTRNAND partition, then mounting it on your computer using something like [OSFMount](http://www.osforensics.com/tools/mount-disk-images.html) and defragging that mounted CTRNAND using something like [Defraggler](https://www.piriform.com/defraggler/download/standard).

## <a name="ts_otp_helper" />OTPHelper/Decrypt9 won't restore / can't find my NAND backup

1. Make sure you do not have any folder named "Decrypt9" on **the root** of your SD card
1. Try redownloading and recopying the OTPHelper files
3. Try checking your SD card file system with something like `fsck.vfat <sd partition path>` (on *nix) or `CHKDSK <sd drive letter> /F` (on Windows)
2. Try backing up your SD card files, then formatting it and copying them back
5. Try a different SD card

## <a name="ts_sys_down" />Black screen on SysNAND boot after downgrading

1. Try booting with your SD card out, and then reinserting it after booting.
   1. Power off your 3DS by holding down the power button.
   2. Take out the SD card.
   3. Power on the 3DS.
   4. When the home menu appears, reinsert your SD card.
2. If you have a hardmod and a NAND backup, flash the backup back to SysNAND.
3. Try booting into recovery mode and updating your system.    
   *This probably will not work for an Old 3DS downgraded to 2.1.0*    
   **This will BRICK a New 3DS downgraded to 2.1.0**
   1. Power off your 3DS by holding down the power button.
   2. Hold L+R+A+Up.
   3. Power on the 3DS.
   4. If you enter safe mode, update your 3DS *only if you have an entrypoint for the latest FW version and it is possible to downgrade from it* and attempt the downgrade again.
4. Your 3DS may be bricked. For real time support, contact me or any other channel operator at [#3dshacks on Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4).

## <a name="ts_sys_a9lh" />Black screen on SysNAND boot after installing arm9loaderhax

1. Ensure you have a working payload.
   1. Check for the existence of `arm9loaderhax.bin` in the root of your SD card.
   2. Check that
      1. `/luma/firmware.bin` exist; and
      2. `/luma/firmware.bin` is the correct one for your console.
2. Try resetting Luma's config and fix options
   1. Delete `/luma/config.bin` from your SD card
   2. Set your options when it boots
2. Test booting Decrypt9
   2. On Luma3DS, hold Start on boot
2. Try [this test payload](https://mega.nz/#!YxMiGDhB!VZLv2XPSqFFzEhf4kGMXAdQtSpIGvnp2vu2W1j4o7cc/) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDanVaR3FTUTFqNFU/view?usp=sharing)).
   1. Rename `/arm9loaderhax.bin`, if it exists, to something else.
   2. Place the `arm9loaderhax.bin` from the archive linked above in your SD root.
   3. Insert your SD card into your 3DS and power on.
   4. Press A. Your 3DS should power off; this means arm9loaderhax is working and something else is broken; your device is **not** bricked.
3. Your 3DS may be bricked. For real time support, contact me or any other channel operator at [#3dshacks on Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4).

## <a name="ts_sys_blue" />Blue screen on boot (bootrom error)

1. Your 3DS is bricked.
2. You will need to get a [hardmod](https://gbatemp.net/threads/414498/) or repair / replace the device.
