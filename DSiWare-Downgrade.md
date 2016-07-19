#### Fieldrunners will only work for the USA region due to missing save files. If *anyone* has fieldrunhax installed on a EUR Region DSi, please extract the save using [this tool](https://gbatemp.net/attachments/dsi_sav_extract-zip.22221/), upload it, and create a github issue with the link

The version of autofirm used in this guide was modified from [Raugo](https://gbatemp.net/members/356694/)'s original autofirm by [Reboot.ms](https://www.reboot.ms/forum/threads/2403/), it is being rehosted [with permission](http://archive.is/KOrWp)

If you are on 11.0.0, you must follow this guide to downgrade your NATIVE_FIRM using DSiWare and a second 3DS which has already has a Custom Firmware installed on it in order to dump and restore your NAND.    

If you are below version 9.0.0 then you should follow [this](https://github.com/Plailect/plailect.github.io/wiki/9.2.0-Update) guide instead to update.    

If you are between 9.0.0 and 10.7.0 you can just follow the instructions [here](https://github.com/Plailect/plailect.github.io/wiki/Get-Started).    

This is a currently working implementation of the "FIRM partitions known-plaintext" exploit detailed [here](https://www.3dbrew.org/wiki/3DS_System_Flaws).

This guide will assume the CFW 3DS is running arm9loaderhax and was setup with this guide, but will work (with slight modifications) on systems running an EmuNAND or RedNAND.

This exploit requires you to [System Transfer](http://en-americas-support.nintendo.com/app/answers/detail/a_id/13996/) from a CFW 3DS to a stock 3DS as part of the steps. System Transfers will only work in the following directions *only*:
  + New 3DS -> New 3DS
  + Old 3DS -> Old 3DS
  + Old 3DS -> New 3DS

Both systems MUST be from the same region.

System Transfers can only be performed once a week.

**After following these instructions on version 11.0.0, you must have an alternate entrypoint such as one of the ones detailed in [Get Started](https://github.com/Plailect/Guide/wiki/Get-Started) in order to enter the homebrew launcher and downgrade.**

#### What you need

* Two 3DS systems
  + **3DS #1**: the 3DS running some kind of custom firmware (arm9loaderhax or some form of EmuNAND/RedNAND)
  + **3DS #2**: the 3DS on stock firmware  
* A legitimately purchased copy of one of the follwing exploitable DSiWare games on **3DS #1** (a pirated copy of the game will **not** work)
  + Fieldrunners (works for USA; EUR save missing and never released for JPN)
  + Legends of Exidia (works for USA + EUR; JPN title pulled from eShop)
* The exploited save for your game and region:
  + Fieldrunners USA Region: [`public.sav`](https://mega.nz/#!I5ljGDiD!wIVzpWxMVmj1u-n4do_5qRleawwCVySyYAx11ydt3UA) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDTk1oOW9od09OVWM))
  + Fieldrunners EUR Region: `MISSING!`
  + Legends of Exidia ALL Regions: [`public.sav`](https://mega.nz/#!FxNDBDDJ!mLAhdDyd5HcMFYaqcOI0ydiDDzTQ4VWPh_DE5kmEpXs) ([mirror](https://drive.google.com/open?id=0B32_U2tx5LXfdmNGMU03dkNoWWM))
* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases)
* fwTool 1.6.0: [`boot.nds`](https://mega.nz/#!A09F1LqZ!J2Co681BrnDiMe9LCdiemUCU-70pKx4aITYek2XkxII) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDZlNVR2x4VzBoVG8))
* [Autofirm 11.0 - Reboot edition](https://mega.nz/#!dl8ASTjB!2jsKbAYTAlspHhxYCt9Wzvia74xEvgtzGQxGLe3TJiM) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDRTlwYUQ1NDJoVlk))
* The 10.4.0 and 11.0.0 decrypted NATIVE_FIRM CIAs for your device:
    + [Old 3DS 10.4.0 - 0004013800000002 v23341](https://mega.nz/#!I5EmyCZC!pU-bG9Esg30LINlasTP43Sei6aDNnTIzh1ojwECKOrU) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDUGxYbmkwVThSUHc))    
    + [Old 3DS 11.0.0 - 0004013800000002 v24368](https://mega.nz/#!AgUGAbKD!0iNXI1ioLM7mBzACfBrPLotYk8g-LzcdTgcuTsQCmHQ) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaG1jbERyQ1BGcHc))    
    + [New 3DS 10.4.0 - 0004013820000002 v23341](https://mega.nz/#!1xcEAApQ!anu5UenuD-uEm6z14n680rQThEgViAsytWh5ZuTa_hc) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDRHlOTWJZNGtxVkk))
    + [New 3DS 11.0.0 - 0004013820000002 v24368](https://mega.nz/#!dk8BgZaJ!8EM0Wk4NHl6-_O4hhcatIpAx-vfkjMKZs7uQh__OKRw) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDeVhnUU1semtNQjQ))

#### Instructions

##### Section I - Prep Work

1. **Use a [save manager](https://github.com/J-D-K/JKSM/releases) to backup any saves you care about on 3DS #2 (it will be formatted!)**
2. **Backup every file on both 3DS's SD cards to two separate folders on your computer, all files will be deleted!**
1. Copy `public.sav` to the root of **3DS #1's** SD card
2. Copy `GodMode9.bin` from the GodMode9 zip to the `/luma/payloads` folder on **3DS #1's** SD card
2. Rename `GodMode9.bin` in `/luma/payloads` on **3DS #1's** SD card to `up_GodMode9.bin`
3. Launch your DSiWare game on **3DS #1** and play it enough to create a save file

##### Section II - Installing the save

5. Boot into arm9loaderhax GodMode9 by holding Up during boot    
**(Be VERY careful with this tool, it can brick you if you misuse it, even with arm9loaderhax installed!)**
5. Navigate to `SD`
7. Press Y on `public.sav` to copy it
6. Press B to get back to the main menu
5. Navigate to the folder for your game and region:
  + Fieldrunners USA Region: `SYSNAND TWLN` -> `title` -> `00030004` -> `4b464445` -> `data`
  + ~~Fieldrunners EUR Region: `SYSNAND TWLN` -> `title` -> `00030004` -> `4b464445` -> `data`~~
  + Legends of Exidia USA Region: `SYSNAND TWLN` -> `title` -> `00030004` -> `4b4c4545` -> `data`
  + Legends of Exidia EUR Region: `SYSNAND TWLN` -> `title` -> `00030004` -> `4b4c4556` -> `data`
16. Press Y to paste a copy of `public.sav`
17. Select "Copy path(s)"
18. Press A to unlock SysNAND writing, then input the key combo given
15. Select "Overwrite file(s)"
18. Press Start to reboot

##### Section III - System Transfer

12. Hold Start on boot to launch Hourglass9
19. If you do not have `sysNAND-A9LHAX.bin` on your computer from Part 5 already, do the following:    
  + Go to SysNAND Backup/Restore and backup SysNAND to `sysNAND.bin`
  + Press Select on the main menu to eject your SD card, then put it in your computer
  + Rename `sysNAND.bin` to `sysNAND-A9LHAX.bin`, `sysNAND.bin.sha` `sysNAND-A9LHAX.bin.sha`, and copy both to a safe location on your computer; this is a SysNAND backup containing arm9loaderhax **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
10. Press Select on the main menu to eject **3DS #1's** SD card, then put it in your computer
12. Put **3DS #2's** SD card into your computer
12. **Backup every file on both 3DS's SD cards to two separate folders on your computer (keep track of which is which)!**
11. Reinsert each SD card back into their corresponding 3DS
11. Press Start to reboot
12. If **3DS #2** has a Nintendo Network ID on it, you must format the device using System Settings:
  + Go to the fifth page of "Other Settings" and select "Format System Memory", then follow all instructions
12. Go to [this link](http://en-americas-support.nintendo.com/app/answers/detail/a_id/227/) and follow Nintendo's official instructions for System Transferring from one system to another while keeping in mind the following:
  + Your CFW 3DS = 3DS #1 = "Source System"
  + Your Stock 3DS = 3DS #2 = "Target System"
  + When prompted, do not delete the target system's SD card contents
  + Make sure neither device's battery dies during the transfer
13. Copy any removed files back onto the corresponding 3DS's SD card

##### Section IV - Restoring 3DS #1

12. If **3DS #1** previously had a Nintendo Network ID on it, you must sign back into that NNID and complete initial setup before restoring its NAND in the next step
14. Reboot **3DS #1** while holding Start to launch Hourglass9
16. Go to SysNAND Backup/Restore and restore SysNAND from `sysNAND-A9LHAX.bin`

##### Section V - Backing up 3DS #2's NAND
2. Copy `boot.nds` to the root of **3DS #2's** SD card
2. Launch your DSiWare game on **3DS #2**
3. Launch fwTool 1.6.0 using your DSiWare game
  + Fieldrunners: Touch the 'Scores' button at the main menu
  + Legends of Exidia: After pressing A or Start at the two title screens, select the first save slot and press continue
4. Use fwTool to backup **3DS #2's** NAND (this takes a *very* long time)
  + New 3DS: select "N3DS_NAND.bin backup"
  + Old 3DS: select "O3DS_NAND.bin backup"
5. Make note of the NAND backup's location

##### Section VI - Downgrading Firmware
1. Extract the `autofirm_Reboot_11.0.zip` file to a folder called `autofirm_Reboot_11.0`
2. Place a copy of **3DS #2's** NAND backup (named `nand.bin`) in the `autofirm_Reboot_11.0` folder
4. Place both NATIVE_FIRM CIAs that correspond to your device in the `autofirm_Reboot_11.0` folder
7. Run "autofirm_ENG.bat" and select which device the NAND backup is for
8. Wait while the script runs
8. If everything worked, then your original NAND will have been renamed to `backup_nand.bin` and you will have a modified `nand.bin` containing the 10.4.0 NATIVE_FIRM on version 11.0.0
3. Rename the modified backup back to the original name it was backed up to
1. Put the modified NAND backup into the same folder on **3DS #2's** SD card (overwrite the original)
2. Launch your DSiWare game on **3DS #2**
3. Launch fwTool 1.6.0 using your DSiWare game
  + Fieldrunners: Touch the 'Scores' button at the main menu
  + Legends of Exidia: After pressing A or Start at the two title screens, select the first save slot and press continue
4. Use fwTool to restore **3DS #2's** NAND (this takes a *very* long time)
  + New 3DS: select "N3DS_NAND.bin restore"
  + Old 3DS: select "O3DS_NAND.bin restore"

Format **3DS #2** at the end of the Guide to remove **3DS #1's** NNID

Your version number will *not* have changed in the settings, but the exploit has worked

**You can now follow the rest of this guide from [here](https://github.com/Plailect/Guide/wiki/Part-1-(Homebrew)). Remember that you will still need an alternate entrypoint such as one of the ones detailed in [Get Started](https://github.com/Plailect/Guide/wiki/Get-Started) in order to enter the homebrew launcher and downgrade.**
