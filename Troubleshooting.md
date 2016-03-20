If you are unable to boot your 3DS, please look for the section relevant to you, and follow the instructions. Once a solution works for you, you can proceed on with the main guide.

#### <a name="ts_bs_emunand" />Black screen on EmuNAND boot

1. Restore a backup to EmuNAND. *(You should have one of these)*

#### <a name="ts_bs_ctrnand" />Black screen on SysNAND boot after injecting CTRNAND

I screwed up in an old version of the guide and had users backup before updating rather than the other way around, so your CFW expects a 10.2+ NAND and gets a 9.2 one instead.

#####CakesFW

1. Download [firmware_patched.bin](https://up1.ca/#LQm-QJ3j5htr2vTG6Z2TnA)
2. Delete `firmware_patched.bin` from the `/cakes/` folder on the root of your SD card if it exists
3. Copy the `firmware_patched.bin` you downloaded to the `/cakes/` folder on the root of your SD card
4. Do the rest of Part 5, after updating EmuNAND to the latest version delete `firmware_patched.bin` from the `/cakes/` folder on the root of your SD card to have it generate a new one

#####AuReiNAND

1. Download [patched_firmware_sys.bin](https://up1.ca/#BBTyUYm47YF3hBwBYhKGsA)
2. Delete `patched_firmware_sys.bin` from the `/rei/` folder on the root of your SD card if it exists
3. Copy the `patched_firmware_sys.bin` you downloaded to the `/rei/` folder on the root of your SD card
4. Do the rest of Part 5, after updating EmuNAND to the latest version delete `patched_firmware_sys.bin` from the `/rei/` folder on the root of your SD card to have it generate a new one

#### <a name="ts_otphelper_verify_fail" />OTPHelper fails to verify my NAND

Check `otphelper.log` on your SD card to see where it fails, then follow the appropriate part to check if it's a  false positive or not.

#####"Validation Stage 1: FAILED" and "Validation Stage 2: FAILED"  
 
1. Check `otphelper.log` to see which titles the TMD hash mismatches on
2. Download the latest build of [GodMode9](https://mega.nz/#!9oUSBRKS!OPabQRkS1az88jH8FIBkrb_N_hd4IWaguCENabot1r4) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDUUlRbFNZbDZjR2M/view?usp=sharing))
3. Copy the `GodMode9` folder from the `GodMode9` zip to the `/3ds/` folder on the root of your SD card
4. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
5. Open GodMode9 **(Be VERY careful with this tool, it can brick you if you delete something important with it)**
6. Select (on bottom screen) `EMUNAND CTRNAND`
7. Select `title`
8. Select the folder which has the same 8 characters as the beginning of the title that mismatched *(for example, if you mismatched on `Checking title 0004013000003202...` then you would select the `00040130` folder)*
9. Select the folder which has the same 8 characters as the end of the title that mismatched *(for example, if you mismatched on `Checking title 0004013000003202...` then you would select the `00003202` folder)*
10. Select `content`

*I only have one file ending with a `.tmd` extension:* This was a legitimate downgrade error and you have been saved from a brick; you should restore EmuNAND from `emuNAND_formatted.bin` and retry from Part 4 - Section II - Step 9

*I have two or more files ending with a `.tmd` extension:* Because of a limitation of OTPHelper we cannot yet check hashes of titles that have ended up with two TMDs (this can be caused by a variety of rare factors). This COULD be a false positive; you can either flash to SysNAND at your own risk or wait for an updated version of OTPHelper to be released that can check these.

Check all of the titles that mismatch with this same method.

#####"Validation Stage 1: SUCCESS" and "Validation Stage 2: FAILED"

This will happen due to having a fragmented NAND (caused by various things such as rxTools' shitty FBI injection or some Gateway software). OTPHelper cannot check the files of a fragmented NAND, but if you got "Validation Stage 1: SUCCESS" then "Validation Stage 2: FAILED" will rarely be an anything but a false positive.

You can either flash to SysNAND at your own risk, or attempt to defragment your NAND by using Decrypt9 to dump your CTRNAND partition, then mounting it on your computer using something like [OSFMount](http://www.osforensics.com/tools/mount-disk-images.html) and defragging that mounted CTRNAND using something like [Defraggler](https://www.piriform.com/defraggler/download/standard).

#### <a name="ts_agb_firm" />Loading AGB_FIRM...

1. CakesFW AGB_FIRM patching is not complete and this error is normal. You will need to use a [patched AGB_FIRM CIA](https://gbatemp.net/threads/390313/) for GBA game support.

#### <a name="ts_otp_helper" />OTPHelper won't restore / can't find my NAND backup

1. Try redownloading and recopying the OTPHelper files
3. Try checking your SD card file system with something like `fsck.vfat <sd partition path>` (on *nix) or `CHKDSK <sd drive letter> /F` (on Windows)
2. Try backing up your SD card files, then formatting it and copying them back
5. Try a different SD card

#### <a name="ts_sys_down" />Black screen on SysNAND boot after downgrading

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

#### <a name="ts_sys_a9lh" />Black screen on SysNAND boot after installing arm9loaderhax

1. Ensure you have a working payload.
   1. Check for the existence of `arm9loaderhax.bin` in the root of your SD card.
   2. If you are following the AuReiNand guide, check that
      1. `/rei/updatedsysnand` and `/rei/firmware.bin` exist; and
      2. `/rei/firmware.bin` is the correct one for your console.
   3. If you are following the CakesFW guide, check that
      1. `/arm9bootloader.bin` exists;
      2. `/Cakes/firmware.bin` and `/Cakes/firmkey.bin` exist and are the correct ones for your console; and
      3. `/boot_config.ini` exists.
2. Test booting Decrypt9
   1. On CakesFW, hold X on boot
   2. On AuReiNAND, hold L + R on boot
2. Try [this test payload](https://mega.nz/#!YxMiGDhB!VZLv2XPSqFFzEhf4kGMXAdQtSpIGvnp2vu2W1j4o7cc/) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDanVaR3FTUTFqNFU/view?usp=sharing)).
   1. Rename `/arm9loaderhax.bin`, if it exists, to something else.
   2. Place the `arm9loaderhax.bin` from the archive linked above in your SD root.
   3. Insert your SD card into your 3DS and power on.
   4. Press A. Your 3DS should power off; this means arm9loaderhax is working and something else is broken; your device is **not** bricked.
3. Your 3DS may be bricked. For real time support, contact me or any other channel operator at [#3dshacks on Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4).

#### <a name="ts_sys_blue" />Blue screen on boot (bootrom error)

1. Your 3DS is bricked.
2. You will need to get a [hardmod](https://gbatemp.net/threads/414498/) or repair / replace the device.
