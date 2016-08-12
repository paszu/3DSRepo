This is add-on section for region changing your arm9loaderhax CFW SysNAND. This is done by installing the CIAs for and injecting the SecureInfo_A file from the region you want to switch to.

**You MUST have already completed Part 5 and installed arm9loaderhax + Luma3DS to use this.**

**You SHOULD have confirmed functional NAND backups of your arm9loaderhax 3DS (such as `NANDmin.bin`) in case something goes wrong.**

*For the eShop to be functional (Old 3DS only, New 3DS cannot access eShop after region change), you MUST [delete your eShop account](http://en-americas-support.nintendo.com/app/answers/detail/a_id/74/~/how-to-delete-a-nintendo-eshop-account) before starting then format the system once you have completed all steps. You must then create a new eShop account. You will lose all user data such as games, DLC, themes, and saves (unless you back them up with something like [JK Save Manager](https://gbatemp.net/threads/413143/)).*

Note that region changing is experimental and can break several things.

**Region changing is almost completely unnecessary since Luma3DS now supports out of region games and individual [title region emulation](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).**

#### What you need

* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/)
* The 9.2.0 ctrtransfer image for your device and region:
  +    <a href="https://plailect.github.io/Guide/9.2.0-20E_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - EUR - ctrtransfer</a> ([mirror]()) ([mirror]())  
  +    <a href="https://plailect.github.io/Guide/9.2.0-20J_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - JPN - ctrtransfer</a> ([mirror]()) ([mirror]())    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20U_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - USA - ctrtransfer</a> ([mirror]()) ([mirror]())    
~
  +    <a href="https://plailect.github.io/Guide/9.2.0-20E_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - EUR - ctrtransfer</a> ([mirror]()) ([mirror]())    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20J_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - JPN - ctrtransfer</a> ([mirror]()) ([mirror]())    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20U_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - USA - ctrtransfer</a> ([mirror]()) ([mirror]())_

#### Instructions

**Some consoles have a `SecureInfo_B` instead of `SecureInfo_A`; this is fine and you should use `SecureInfo_B` for the relevant steps.**    

1. Copy `GodMode9.bin` from the GodMode9 zip to the `/luma/payloads` folder on your SD card
1. Rename `GodMode9.bin` in `/luma/payloads` to `up_GodMode9.bin`
4. Eject your SD card and put it back in your 3DS
4. Boot into arm9loaderhax Decrypt9 by holding X during boot

// ???

5. Boot into arm9loaderhax GodMode9 by holding Up during boot    
**(Be VERY careful with this tool, it can brick you if you misuse it, even with arm9loaderhax installed!)**
14. Navigate to `SYSNAND CTRNAND` -> `rw` -> `sys`
15. Press Y on `SecureInfo_A` to copy it
16. Press Y to paste a copy of `SecureInfo_A`
17. Select "Copy path(s)"
18. Press A to unlock SysNAND writing, then input the key combo given
20. Select "Choose new name"
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
13. Press B to exit edit mode, then save changes, then press B again to return to the directory
19. You should see both a `SecureInfo_A` and `SecureInfo_C` if everything was done properly. (`SecureInfo_C` is used in place of `SecureInfo_A` when using Luma3DS if it detects the file on boot)
16. Press Start to reboot

You can now update your region changed CFW SysNAND to the latest version

*For the eShop to be functional (Old 3DS only, New 3DS cannot access eShop after region change), you MUST have [deleted your eShop account](http://en-americas-support.nintendo.com/app/answers/detail/a_id/74/~/how-to-delete-a-nintendo-eshop-account) before starting then format the system now that you have completed all steps. You must then create a new eShop account. You will lose all user data such as games, DLC, themes, and saves (unless you back them up with something like [JK Save Manager](https://gbatemp.net/threads/413143/)).*
