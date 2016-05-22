This is add-on section for region changing your arm9loaderhax CFW SysNAND. This is done by installing the CIAs for and injecting the SecureInfo_A file from the region you want to switch to.

**You MUST have already completed Part 5 and installed arm9loaderhax + Luma3DS to use this.**

**You SHOULD have confirmed functional NAND backups of your arm9loaderhax 3DS (such as `sysNAND-A9LHAX.bin`) in case something goes wrong.**

*For the eShop to be functional, you MUST [delete your eShop account](http://en-americas-support.nintendo.com/app/answers/detail/a_id/74/~/how-to-delete-a-nintendo-eshop-account) then format the system once you have completed all steps. You will lose all user data such as games, DLC, themes, and saves (unless you back them up with something like [JK Save Manager](https://gbatemp.net/threads/413143/)).*
Note that region changing is experimental and can break several things.

**Region changing is almost completely unnecessary since Luma3DS now supports out of region games and individual [title region emulation](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).**

#### What you need

* The latest release of [sysUpdater](https://github.com/profi200/sysUpdater/releases)
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases)
* The latest build of [GodMode9](https://mega.nz/#!Fh0SHSCJ!wca8zg6cSIGwVVjmPJH_kda9h1BfG5pNYxrPrnd-c6Y) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDUnhRRjhJTVZOQ0k))
* The 9.2.0 firmware pack zip file for your device and the region you want to switch to:    
**Note that the New 3DS 9.2.0 packs are not the same as the ones in Part 2**
 +    [New 3DS 9.2.0 (Region Change) - EUR](https://mega.nz/#!Rg8XlZaR!-q7Xe_GHyt2MEWrLzKc3rxY2fE47QMFk-VN_3PE5i4w) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDSDdEY1d1Zkg3eDg/view?usp=sharing))    
 +    [New 3DS 9.2.0 (Region Change) - JAP](https://mega.nz/#!x0c3CKBA!zJCScD9i_pVyu3s35N8ap4nLLC6M0GmDyz_VdNunGms) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDTHlWNmlKaFRBM2s/view?usp=sharing))    
 +    [New 3DS 9.2.0 (Region Change) - USA](https://mega.nz/#!1oc0XASa!kAeUYyKEKFwdnE31c2hNHjvavSkE5HThDNLpMqXHH4o) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDUURZUmc2d0VSVW8/view?usp=sharing))    
 ~
 +    [Old 3DS or 2DS 9.2.0 - EUR](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    [Old 3DS or 2DS 9.2.0 - JAP](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    [Old 3DS or 2DS 9.2.0 - USA](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))    

#### Instructions

**Some consoles have a `SecureInfo_B` instead of `SecureInfo_A`; this is fine and you should use `SecureInfo_B` for the relevant steps.**    

1. Copy `GodMode9.bin` from the GodMode9 zip to the `/luma/payloads` folder on your SD card
1. Rename `GodMode9.bin` in `/luma/payloads` to `up_GodMode9.bin`
1. Copy `sysUpdater.cia` from the sysUpdater zip to the root of your SD card
1. Copy `FBI.cia` from the FBI zip to the root of your SD card
2. Delete any existing `updates` folder from your SD card if there is one
3. Copy the `updates` folder from the 9.2.0 firmware zip to the root of your SD card
4. Eject your SD card and put it back in your 3DS
5. Use FBI to install `sysUpdater.cia` and `FBI.cia` *(keep track of which FBI was installed via CIA and which was injected into H&S)*
6. Get back to the home menu then open sysUpdater
7. Press Y to downgrade to the region you want to switch to
11. If you get an error before installation, power off your 3DS by holding the power button and try again (this can take many tries)
13. If you freeze on the "Rebooting in 10 seconds" line for longer than 10 seconds, it is safe to power off your 3DS by holding the power button
5. Boot into arm9loaderhax GodMode9 by holding Up    
**(Be VERY careful with this tool, it can brick you if you misuse it, even with arm9loaderhax installed!)**
14. Navigate to `SYSNAND CTRNAND` -> `rw` -> `sys`
15. Press Y on `SecureInfo_A` to copy it
16. Press Y to paste a copy of `SecureInfo_A`
17. Select "Copy path(s)"
18. Press A to unlock SysNAND writing, then input the key combo given
20. Use the D-Pad to rename the file to `SecureInfo_C`, pressing A when you're done (overwrite any existing `SecureInfo_C`)
18. Scroll down to the `SecureInfo_C` you just pasted
21. Press A on `SecureInfo_C` then select "Show in Hexeditor"
22. Press A to continue
23. Press A to enter edit mode
11. Go to the beginning of line 00000100 and press A on it
12. Hold A while pressing Up or Down on the D-Pad to edit the number
13. Change the first number pair on line 00000100 to the following pair that corresponds to *the region you want to change to*:
    - "00" : JPN
    - "01" : USA
    - "02" : EUR
13. Press B to exit edit mode, then press B again to return to the directory
19. You should see both a `SecureInfo_A` and `SecureInfo_C` if everything was done properly. (`SecureInfo_C` is used in place of `SecureInfo_A` when using Luma3DS if it detects the file on boot)
16. Press Start to reboot
11. Launch the FBI which was installed via CIA earlier
12. Navigate to the "Titles" menu

Scroll past the green titles until you see the red ones begin. These are system titles installed to the internal flash memory of your device, not to the SD card. Many, but not all, of these red system titles will have a "Product Code" on the top screen.

**Any red system title that either does not have a Product Code, or has the Product Code "CTR-P-CTAP" should be ignored for the following instructions!**

Look at the following list and determine the letter that corresponds to your PREVIOUS device region. This should be the one from *BEFORE* the region change.

+ "E" : USA
+ "J" : JPN
+ "P" : EUR

Use the FBI title menu to delete any title whose product code *ends* in the letter corresponding to your previous device region. This will remove leftover system programs designed for your previous region which will cause issues if left installed.

**Remember that any red system title that either does not have a Product Code, or has the Product Code "CTR-P-CTAP" (even though it ends in "P") should be ignored!**

You can now update your region changed CFW SysNAND to the latest version

If you experience any strange bugs (especially any related to Super Smash Bros and Monster Hunter 4 if you are on an Old 3DS), you should make a SysNAND backup, then backup your SD card, then try performing a System Format.

*For the eShop to be functional, you MUST [delete your eShop account](http://en-americas-support.nintendo.com/app/answers/detail/a_id/74/~/how-to-delete-a-nintendo-eshop-account) then format the system now that you have completed all steps. You will lose all user data such as games, DLC, themes, and saves (unless you back them up with something like [JK Save Manager](https://gbatemp.net/threads/413143/)).*