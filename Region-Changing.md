This is add-on section for region changing your arm9loaderhax CFW SysNAND. This is done by installing the 9.2.0 ctrtransfer image for the region you want to switch to and modifying your SecureInfo_A file.

**You MUST have already completed Part 3 and installed arm9loaderhax + Luma3DS to use this.**

*This process will unlink your NNID from the system, since it will no longer be compatible with it. NNID's are locked to the region of the device that created them, and cannot be transferred between regions without [a very complex and advanced process](https://gist.githubusercontent.com/yifanlu/e80db121d38aceb8cca0e03cefd5853b/raw/3c4dd89869156ca0f945a2791e699acfdb32b510/gistfile1.txt).*

After this process, only Old 3DSs will be able to access the eShop after creating an NNID. Region changed New 3DSs cannot access the eShop!

**Region changing is almost completely unnecessary since Luma3DS supports out of region games and individual [title region emulation](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).**

#### What you need

* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest)
* The 9.2.0 ctrtransfer image for your device and region     
*(if your device is not from one of these regions, just pick one that matches your device type)*:
  +    <a href="https://plailect.github.io/Guide/9.2.0-20E_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - EUR - ctrtransfer</a> ([mirror](https://mega.nz/#!lxcWTTCJ!AP8xIzlwdqsGOHRDHpVGhOR-grpPmjFVTTdocpUtt3w)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDYU5OSUg2NS1zajQ))  
  +    <a href="https://plailect.github.io/Guide/9.2.0-20J_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - JPN - ctrtransfer</a> ([mirror](https://mega.nz/#!llUzGZCK!D_e8RfhzUnBFX9sBv-bQXXBJ1ARftMyrLxPCZsCNvrY)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDcWF2dFNNeERPTFk))    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20U_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - USA - ctrtransfer</a> ([mirror](https://mega.nz/#!1gF1SLTC!Lg8z7FKvdxdc3iOTGX9GWmMX33dQfVGPPklrRNCkTE0)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDalhTaEhDekxlWjg))    
~
  +    <a href="https://plailect.github.io/Guide/9.2.0-20E_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - EUR - ctrtransfer</a> ([mirror](https://mega.nz/#!dt1j1abR!-DXxty0Ca9ERXMM_5WPIu9bOkdy3DP1A96VrIxW0FjQ)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDblQ1ZXNZcXkzLWM))    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20J_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - JPN - ctrtransfer</a> ([mirror](https://mega.nz/#!4p1xVDyZ!VITvzSRRdUfdsgg_t00LSut9ItAB_mEqxeTqk8NgBPM)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDdEQ5NmNUclFsdTQ))    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20U_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - USA - ctrtransfer</a> ([mirror](https://mega.nz/#!k8lkjYIR!Bf2CMM4iP1VuNwWaCMnl8WvJFNkX2pQ3H4J_5P_tDDA)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDYW1tbUhtblBBdVU))

#### Instructions

**Some consoles have a `SecureInfo_B` instead of `SecureInfo_A`; this is fine and you should use `SecureInfo_B` for the relevant steps.**    

##### Section I - Prep work

1. Copy `GodMode9.bin` from the GodMode9 zip to the `/luma/payloads` folder on your SD card and rename `GodMode9.bin` in `/luma/payloads` to `up_GodMode9.bin`
7. Copy `Decrypt9WIP.bin` to the `/luma/payloads/` folder on your SD card and rename `Decrypt9WIP.bin` to `x_Decrypt9WIP.bin`
1. Copy the 9.2.0 ctrtransfer image `.bin` and `.bin.sha` from the ctrtransfer zip to the `/files9/` folder on your SD card
4. Reinsert your SD card into your 3DS
4. Open Decrypt9 from arm9loaderhax by holding (X) during boot
1. Go to "SysNAND Options", then "CTRNAND Transfer", then "Auto CTRNAND Transfer"
2. Select the 9.2.0 ctrtransfer image when prompted by pressing (A)
2. **Backup SysNAND to `NANDmin.bin` when prompted by pressing (A)**
3. Allow the transfer process to proceed automatically, this may take some time
2. Once the transfer is complete, press Select to eject your SD card
3. Put your SD card in your computer, then copy `NANDmin.bin` and `NANDmin.bin.sha` from the `/files9/` folder on your SD card to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong in the future **(Your backup should match one of the sizes on [this](NAND-Size) page; if it does not, you should delete it and make a new one!)**
4. Delete the 9.2.0 ctrtransfer image from the `/files9/` folder on your SD card after copying it
5. Reinsert your SD card into your 3DS

##### Section II - Editing SecureInfo

6. Press (Start) then hold (Up) to reboot into arm9loaderhax GodMode9
**(Be VERY careful with this tool, it can brick you if you misuse it, even with arm9loaderhax installed!)**
14. Navigate to `SYSNAND CTRNAND` -> `data` -> (32 Character ID) -> `sysdata` -> `00010038`
15. Hold down the (R) trigger, then press X on `00000000` to rename this file
16. Press Up once to change the name to `10000000`
17. Press (A) to save changes
18. Press (A) to unlock SysNAND writing, then input the key combo given
18. Navigate back to the Main Menu
14. Navigate to `SYSNAND CTRNAND` -> `rw` -> `sys`
15. Press (Y) on `SecureInfo_A` to copy it
16. Press (Y) to paste a copy of `SecureInfo_A`
17. Select "Copy path(s)"
20. Select "Choose new name"
20. Use the D-Pad to rename the file to `SecureInfo_C`, pressing (A) when you're done (overwrite any existing `SecureInfo_C`)
18. Scroll down to the `SecureInfo_C` you just pasted
21. Press (A) on `SecureInfo_C` then select "Show in Hexeditor"
22. Press (A) to continue
23. Press (A) to enter edit mode
11. Go to the beginning of line 00000100 and press (A) on it
12. Hold (A) while pressing (Up) or (Down) on the D-Pad to edit the number
13. Change the first number pair on line 00000100 to the following pair that corresponds to *the region you want to change to*:
    - "00" : JPN
    - "01" : USA
    - "02" : EUR
13. Press (B) to exit edit mode, then save changes, then press (B) again to return to the directory
19. You should see both a `SecureInfo_A` and `SecureInfo_C` if everything was done properly. (`SecureInfo_C` is used in place of `SecureInfo_A` when using Luma3DS if it detects the file on boot)
16. Press Start to reboot

You can now update your region changed CFW SysNAND to the latest version
