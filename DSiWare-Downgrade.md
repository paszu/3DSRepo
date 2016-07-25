If you are on 11.0.0, you must follow this guide to downgrade your NATIVE_FIRM using DSiWare and a second 3DS which has already has a Custom Firmware installed on it in order to dump and restore your NAND.    

If you are below version 9.0.0 then you should follow [this](https://github.com/Plailect/plailect.github.io/wiki/9.2.0-Update) guide instead to update.    

If you are between 9.0.0 and 10.7.0 you can just follow the instructions [here](https://github.com/Plailect/plailect.github.io/wiki/Get-Started).    

This takes advantage of an oversight which allows DSiWare titles to read and write anywhere in NAND.

This is a currently working implementation of the "FIRM partitions known-plaintext" exploit detailed [here](https://www.3dbrew.org/wiki/3DS_System_Flaws).

This guide will assume the CFW 3DS is running arm9loaderhax and was setup with this guide, but will work (with slight modifications such as doing all SysNAND steps on RedNAND) on systems running an EmuNAND or RedNAND.

This exploit requires you to [System Transfer](http://en-americas-support.nintendo.com/app/answers/detail/a_id/13996/) from a CFW 3DS to a stock 3DS as part of the steps. System Transfers will work in the following directions *only*:
  + New 3DS -> New 3DS
  + Old 3DS -> Old 3DS
  + Old 3DS -> New 3DS

Both systems MUST be from the same region.

System Transfers can only be performed once a week.

The reason we buy the game and perform a transfer on a disposable NNID is that the NNID which is transfered cannot be moved back to the first device (except by a system transfer back, which isn't always an option since going from O3DS -> N3DS can't be done in reverse)

**After following these instructions on version 11.0.0, you must have an alternate entrypoint such as one of the ones detailed in [Get Started](https://github.com/Plailect/Guide/wiki/Get-Started) in order to enter the homebrew launcher and downgrade.**

#### What you need

* Two 3DS systems
  + **3DS #1**: the 3DS running some kind of custom firmware (arm9loaderhax or some form of EmuNAND/RedNAND)
  + **3DS #2**: the 3DS on stock firmware  
* (**DO NOT BUY THIS YET**) You will purchase one of the following exploitable DSiWare games (a pirated copy of the game will **not** work) **as part of the instructions**.
  + **Fieldrunners**: Works for **USA + EUR** (never released for JPN)
  + **Legends of Exidia**: Works for **USA + EUR** (JPN title pulled from eShop)
* The exploited save for your game and region:
  + Fieldrunners USA Region: [`public.sav`](https://mega.nz/#!NwkUzKSb!VUauxzpzqm3IKIh8yoaGYednbZdYhUjFWHB2zu_ALZQ) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDR2I3ME5LNW1ST2c))
  + Fieldrunners EUR Region: [`public.sav`](https://mega.nz/#!ho0yyBhB!Rf0qAZ_jxfdDOWBnFfT10Se0uzPhRIqFQg3ybjEBXa8) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDdnpCZ09NMGZxaVk))
  + Legends of Exidia ALL Regions: [`public.sav`](https://mega.nz/#!JslhRIBK!35_qU_mg5tYOOQSoKBQOKUf_WTN-311RsgJC9slduuQ) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDN3pYbXI4S0pldzQ))
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases/)
* The latest version of [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* The latest release of [dgTool](https://github.com/Plailect/dgTool/releases)
* The dgTool zip for your device:
    + [Old 3DS 11.0.0 -> 10.4.0](https://mega.nz/#!UklRTTiA!ricB9kIC2HRd6_dKvnf-9sbP1O3Q4P5sdKOWmMiY7LA) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDS1RKckFSNk9CMnc))    
    + [New 3DS 11.0.0 -> 10.4.0](https://mega.nz/#!E4VTCCTT!nCyvAWQN20p_92j5Xuj-ESuO82CtMjOMhbbT1ofK1BU) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDZG52ODdTeFVSM1U))

#### Instructions

##### Section I - Prep Work

1. **Use a [save manager](https://github.com/J-D-K/JKSM/releases) to backup any saves you care about on 3DS #2 (it will be formatted!)**
1. Copy `public.sav` to the root of **3DS #1's** SD card
12. On **3DS #1**, hold Start on boot to launch Hourglass9
19. If you do not have `sysNAND-A9LHAX.bin` on your computer from Part 5 already, do the following:    
  + Go to SysNAND Backup/Restore and backup SysNAND to `sysNAND.bin`
  + Press Select on the main menu to eject your SD card, then put it in your computer
  + Rename `sysNAND.bin` to `sysNAND-A9LHAX.bin` and `sysNAND.bin.sha` to `sysNAND-A9LHAX.bin.sha`
  + Copy both to a safe location on your computer; this is a SysNAND backup containing arm9loaderhax **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
10. Press Select on the main menu to eject **3DS #1's** SD card, then put it in your computer
12. Put **3DS #2's** SD card into your computer
12. **Backup every file on both 3DS's SD cards to two separate folders on your computer (keep track of which is which)!**
11. Reinsert each SD card back into their corresponding 3DS
11. Press Start to reboot

##### Section II - Formatting 3DS #1

1. On **3DS #1**, Go to the last page of "Other Settings" and select "Format System Memory", then follow all instructions
2. Copy all files from your backup back onto the device **except** the `Nintendo 3DS` folder (it only makes this slower and you don't need it)
3. Boot your device, then use initial setup to create a **new** Nintendo Network ID **(if you use an existing NNID, it will be stuck on 3DS #2!)**

##### Section III - Injecting FBI

**If FBI is still injected into Health and Safety (check now), you can skip this section!**

2. On **3DS #1**, hold Start on boot to launch Hourglass9
11. Go to "SysNAND Backup/Restore", then select the "Health & Safety Dump" option to dump Health & Safety to `hs.app` **(you can use Up and Down / Left and Right to change the name)**
12. Press Select to eject your SD card, then put it in your computer
13. Extract Universal Inject Generator, then copy both `hs.app` from your SD card and `FBI.cia` from the FBI zip to the `input` folder
14. Double click `go.bat` *(or  execute `go.sh` with Terminal on Linux, or double click `Mac_inject_launcher.app` on Mac)*
15. Copy `FBI_inject_with_banner.app` to the root of your SD card and reinsert your SD card into your 3DS
16. Press B on Hourglass9, then go to "SysNAND Backup/Restore", and select the "Health & Safety Inject" option
17. Press down once to select `FBI_inject_with_banner.app`, then press A and confirm to inject
18. Go to the main menu, then press Start to reboot


##### Section IV - Installing the save

5. Purchase one of the following exploitable DSiWare games (a pirated copy of the game will **not** work)
  + **Fieldrunners**: Works for **USA + EUR**
  + **Legends of Exidia**: Works for **USA + EUR**
5. Launch FBI on **3DS #1**
5. Navigate to `SD`
7. Press A on `public.sav` and copy it
6. Press B to get back to the main menu
5. Navigate to `TWL NAND` -> `title` -> `00030004`
5. Navigate to the folder for your game and region:
  + Fieldrunners USA Region: `4b464445` -> `data`
  + Fieldrunners EUR Region: `4b464456` -> `data`
  + Legends of Exidia USA Region: `4b4c4545` -> `data`
  + Legends of Exidia EUR Region: `4b4c4556` -> `data`
16. Press A on the existing `public.sav` and delete it
16. Press A on the current directory and paste `public.sav`
16. Press B to get back to the main menu
18. Press Start to exit

##### Section V - System Transfer

12. Hold Start on boot to launch Hourglass9
19. If you do not have `sysNAND-A9LHAX.bin` on your computer from Part 5 already, do the following:    
  + Go to SysNAND Backup/Restore and backup SysNAND to `sysNAND.bin`
  + Press Select on the main menu to eject your SD card, then put it in your computer
  + Rename `sysNAND.bin` to `sysNAND-A9LHAX.bin` and `sysNAND.bin.sha` to `sysNAND-A9LHAX.bin.sha`
  + Copy both to a safe location on your computer; this is a SysNAND backup containing arm9loaderhax **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
10. Press Select on the main menu to eject **3DS #1's** SD card, then put it in your computer
12. Put **3DS #2's** SD card into your computer
12. **Backup every file on both 3DS's SD cards to two separate folders on your computer (keep track of which is which)!**
11. Reinsert each SD card back into their corresponding 3DS
11. Press Start to reboot
12. If **3DS #2** has a Nintendo Network ID on it, you must format the device using System Settings:
  + Go to the last page of "Other Settings" and select "Format System Memory", then follow all instructions
12. Read the following:
  + Your CFW 3DS = 3DS #1 = "Source System"
  + Your Stock 3DS = 3DS #2 = "Target System"
  + **Move DSiWare titles when prompted!**
  + Do **NOT** delete the target system's SD card contents when prompted
  + Make sure neither device's battery dies during the transfer
12. Go to [this link](http://en-americas-support.nintendo.com/app/answers/detail/a_id/227/) and follow Nintendo's official instructions for System Transferring from one system to another while keeping in mind what you just read

##### Section VI - Restoring 3DS #1

12. On **3DS #1**, sign back into your initial NNID and complete initial setup before restoring its NAND in the next step
14. Reboot **3DS #1** while holding Start to launch Hourglass9
16. Go to SysNAND Backup/Restore and restore SysNAND from `sysNAND-A9LHAX.bin`

##### Section VII - Backing up 3DS #2's firmware

2. Copy `boot.nds` to the root of **3DS #2's** SD card
3. Copy the `dgTool` folder for your device to the root of **3DS #2's** SD card
2. Launch your DSiWare game on **3DS #2**
3. Launch dgTool using your DSiWare game
  + Fieldrunners: Touch the 'Scores' button at the main menu
  + Legends of Exidia: After pressing A or Start at the two title screens, select the first save slot and press continue
4. Use dgTool to flash the 10.4.0 firmware bin to **3DS #2**
  + New 3DS: select "Dump F0F1_N3DS.bin"
  + Old 3DS: select "Dump F0F1_O3DS.bin"
5. Make note of the firmware backup's location
5. Exit dgTool
6. Put your SD card in your computer, then copy `F0F1_N3DS.bin` or `F0F1_O3DS.bin` (depending on your device) to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong

##### Section VIII - Flashing 3DS #2's firmware

2. Launch your DSiWare game on **3DS #2**
3. Launch dgTool using your DSiWare game
  + Fieldrunners: Touch the 'Scores' button at the main menu
  + Legends of Exidia: After pressing A or Start at the two title screens, select the first save slot and press continue
4. Select "Downgrade FIRM to 10.4" and confirm to flash the 10.4.0 firmware bin to **3DS #2**
5. Exit dgTool
6. Reboot

**3DS #2's** version number will *not* have changed in the settings, but the exploit has worked

**You can now follow the rest of this guide from [here](https://github.com/Plailect/Guide/wiki/Part-1-(Homebrew)) on 3DS #2. Remember that you will still need an alternate entrypoint such as one of the ones detailed in [Get Started](https://github.com/Plailect/Guide/wiki/Get-Started) in order to enter the homebrew launcher and downgrade.**
