If you are on 11.0.0, you must follow this guide to downgrade your NATIVE_FIRM using DSiWare and a second 3DS which has already has a Custom Firmware installed on it in order to dump and restore your NAND.    

This takes advantage of an oversight which allows DSiWare titles to read and write anywhere in NAND.

This is a currently working implementation of the "FIRM partitions known-plaintext" exploit detailed [here](https://www.3dbrew.org/wiki/3DS_System_Flaws).

This guide will assume the CFW 3DS is running arm9loaderhax and was setup with this guide, but will work (with slight modifications such as doing all SysNAND steps on RedNAND) on systems running an EmuNAND or RedNAND.

This exploit requires you to [System Transfer](http://en-americas-support.nintendo.com/app/answers/detail/a_id/13996/) from a CFW 3DS to a stock 3DS as part of the steps. System Transfers will work in the following directions *only*:
  + New 3DS -> New 3DS
  + Old 3DS -> Old 3DS
  + Old 3DS -> New 3DS

**3DS #1's NNID will be stuck on 3DS #2 unless you either system transfer back or call Nintendo! (details in the instructions)**

Both systems MUST be from the same region.

System Transfers can only be performed once a week.

#### What you need

* Two 3DS systems
  + **3DS #1**: the 3DS running some kind of custom firmware (arm9loaderhax or some form of EmuNAND/RedNAND)
  + **3DS #2**: the 3DS on stock firmware  
* Purchase one of the following exploitable DSiWare games (a pirated copy of the game will **not** work) on **3DS #1**
  + **Fieldrunners**: Works for **USA + EUR** (never released for JPN)
  + **Legends of Exidia**: Works for **USA + EUR** (JPN title pulled from eShop)
  + **Guitar Rock Tour**: Works for **EUR Only** (game has been pulled in all regions, you must have installed it already)
* The exploited save for your game and region:
  + Fieldrunners USA Region: <a href="https://plailect.github.io/Guide/fieldrunners_usa_save.torrent" target="_blank">`public.sav`</a> ([mirror](https://mega.nz/#!NwkUzKSb!VUauxzpzqm3IKIh8yoaGYednbZdYhUjFWHB2zu_ALZQ)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDR2I3ME5LNW1ST2c))
  + Fieldrunners EUR Region: <a href="https://plailect.github.io/Guide/fieldrunners_eur_save.torrent" target="_blank">`public.sav`</a> ([mirror](https://mega.nz/#!ho0yyBhB!Rf0qAZ_jxfdDOWBnFfT10Se0uzPhRIqFQg3ybjEBXa8)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDdnpCZ09NMGZxaVk))
  + Guitar Rock Tour EUR Region: <a href="https://plailect.github.io/Guide/grtpwn_eur_save.torrent" target="_blank">`public.sav`</a> ([mirror](https://mega.nz/#!59MUyKTS!6NCe0q1UG5OrFxcJCBnGcUKrfe0PdV9zr9fV2GbXDNg)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDc2pqaGxVaWhoQWM))
  + Legends of Exidia ALL Regions: <a href="https://plailect.github.io/Guide/exidia_save.torrent" target="_blank">`public.sav`</a> ([mirror](https://mega.nz/#!JslhRIBK!35_qU_mg5tYOOQSoKBQOKUf_WTN-311RsgJC9slduuQ)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDN3pYbXI4S0pldzQ))
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases/)
* The latest version of [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* The latest release of [dgTool](https://github.com/Plailect/dgTool/releases)
* The dgTool zip corresponding to **3DS #2**:
    + <a href="https://plailect.github.io/Guide/dgTool_o3ds.torrent" target="_blank">Old 3DS 11.0.0 -> 10.4.0</a> ([mirror](https://mega.nz/#!UklRTTiA!ricB9kIC2HRd6_dKvnf-9sbP1O3Q4P5sdKOWmMiY7LA)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDS1RKckFSNk9CMnc))    
    + <a href="https://plailect.github.io/Guide/dgTool_n3ds.torrent" target="_blank">New 3DS 11.0.0 -> 10.4.0</a> ([mirror](https://mega.nz/#!E4VTCCTT!nCyvAWQN20p_92j5Xuj-ESuO82CtMjOMhbbT1ofK1BU)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDZG52ODdTeFVSM1U))

#### Instructions

##### Section I - Prep Work

1. Create a folder named `files9` on the root of your SD card if it does not already exist
1. **Use a [save manager](https://github.com/J-D-K/JKSM/releases) to backup any saves you care about on 3DS #2 (it will be formatted!)**
2. Copy `public.sav` to the root of **3DS #1's** SD card
3. On **3DS #1**, hold Start on boot to launch Hourglass9
4. If you do not have `NANDmin.bin` on your computer from Part 2 already, do the following:    
  + Go to SysNAND Options, then SysNAND Backup/Restore, then backup **(min size)** SysNAND to `NANDmin.bin`
  + Press Select on the main menu to eject your SD card, then put it in your computer
  + Copy `NANDmin.bin` and `NANDmin.bin.sha` from the `/files9/` folder on your SD card to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong in the future **(Your backup should match one of the sizes on [this](NAND-Size) page; if it does not, you should delete it and make a new one!)**
5. Press Select on the main menu to eject **3DS #1's** SD card, then put it in your computer
6. Put **3DS #2's** SD card into your computer
7. **Backup every file on both 3DS's SD cards to two separate folders on your computer (keep track of which is which)!**
8. Reinsert each SD card back into their corresponding 3DS
9. Press Start to reboot

##### Section II - Injecting FBI

**If FBI is still injected into Health and Safety (check now), you can skip this section**

1. On **3DS #1**, open Hourglass9 from arm9loaderhax by holding Start on boot
11. Go to "SysNAND Backup/Restore", then select the "Health&Safety Dump" option to dump Health & Safety to `hs.app` **(you can use Up and Down / Left and Right to change the name)**
12. Press Select to eject your SD card, then put it in your computer
13. Extract Universal Inject Generator, then copy both `hs.app` from your SD card and `FBI.cia` from the FBI zip to the `input` folder
14. Double click `go.bat` *(or  execute `go.sh` with Terminal on Linux, or double click `Mac_inject_launcher.app` on Mac)*
15. Copy `FBI_inject_with_banner.app` to the `/files9/` folder on your SD card and reinsert your SD card into your 3DS
16. Press B, then go to "SysNAND Backup/Restore", then select the "Health&Safety Inject" option
17. Press down once to select `FBI_inject_with_banner.app`, then press A and confirm to inject
18. Go to the main menu, then press Start to reboot


##### Section III - Installing the save

1. Purchase one of the following exploitable DSiWare games (a pirated copy of the game will **not** work)
  + **Fieldrunners**: Works for **USA + EUR**
  + **Legends of Exidia**: Works for **USA + EUR**
  + **Guitar Rock Tour**: You must have already purchased this for **EUR**
2. Launch FBI on **3DS #1**
3. Navigate to `SD`
4. Press A on `public.sav` and copy it
5. Press B to get back to the main menu
6. Navigate to `TWL NAND` -> `title` -> `00030004`
7. Navigate to the folder for your game and region:
  + Fieldrunners USA Region: `4b464445` -> `data`
  + Fieldrunners EUR Region: `4b464456` -> `data`
  + Legends of Exidia USA Region: `4b4c4545` -> `data`
  + Legends of Exidia EUR Region: `4b4c4556` -> `data`
  + Guitar Rock Tour EUR Region: `4b475256` -> `data`
8. Press A on the existing `public.sav` and delete it
9. Press A on the current directory and paste `public.sav`
10. Press B to get back to the main menu
11. Press Start to exit

##### Section IV - System Transfer

1. **Backup every file on both 3DS's SD cards to two separate folders on your computer (keep track of which is which)!**
2. Reinsert each SD card back into their corresponding 3DS
3. Press Start to reboot
4. If **3DS #2** has a Nintendo Network ID on it, you must format the device using System Settings:
  + Go to the last page of "Other Settings" and select "Format System Memory", then follow all instructions
5. Read the following:
  + Your CFW 3DS = 3DS #1 = "Source System"
  + Your Stock 3DS = 3DS #2 = "Target System"
  + **Move DSiWare titles when prompted!**
  + Do **NOT** delete the target system's SD card contents when prompted
  + Make sure neither device's battery dies during the transfer
6. Go to [this link](http://en-americas-support.nintendo.com/app/answers/detail/a_id/227/) and follow Nintendo's official instructions for System Transferring from one system to another while keeping in mind what you just read

##### Section V - Restoring 3DS #1

1. On **3DS #1**, complete initial setup
2. Do one of the following *(or neither if you don't mind **3DS #1's** NNID being nonfunctional)*
    + Do the rest of the sections and then the full guide on **3DS #2**, then wait one week, then System Transfer from **3DS #2** back to **3DS #1** *(remember you cannot transfer back from a New 3DS to an Old 3DS)*
    + Go to the settings and attempt sign back into your initial NNID, then call Nintendo and ask about the error you get
3. Reboot **3DS #1** while holding Start to launch Hourglass9
4. Go to SysNAND Backup/Restore and restore SysNAND from `sysNAND-A9LHAX.bin`

##### Section VI - Backing up 3DS #2's firmware

1. Copy `boot.nds` to the root of **3DS #2's** SD card
2. Copy the `dgTool` folder from the dgTool zip to the root of **3DS #2's** SD card
3. Launch your DSiWare game on **3DS #2**
4. Launch dgTool using your DSiWare game
  + Fieldrunners: Touch the 'Scores' button at the main menu
  + Legends of Exidia: After pressing A or Start at the two title screens, select the first save slot and press continue
  + Guitar Rock Tour: Scroll down and go to High-Scores -> Drums -> Easy
5. Use dgTool to backup **3DS #2's** firmware
  + New 3DS: select "Dump F0F1_N3DS.bin"
  + Old 3DS: select "Dump F0F1_O3DS.bin"
6. Make note of the firmware backup's location
7. Exit dgTool
8. Put your SD card in your computer, then copy `F0F1_N3DS.bin` or `F0F1_O3DS.bin` (depending on your device) to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong

##### Section VII - Flashing 3DS #2's firmware

1. Launch your DSiWare game on **3DS #2**
2. Launch dgTool using your DSiWare game
  + Fieldrunners: Touch the 'Scores' button at the main menu
  + Legends of Exidia: After pressing A or Start at the two title screens, select the first save slot and press continue
  + Guitar Rock Tour: Scroll down and go to High-Scores -> Drums -> Easy
3. Select "Downgrade FIRM to 10.4" and confirm to flash the 10.4.0 firmware bin to **3DS #2**
4. Exit dgTool
5. Reboot

**3DS #2's** version number will *not* have changed in the settings, but the exploit has worked

You can now continue from either [Homebrew Launcher (No Browser)](Homebrew-Launcher-(No-Browser)) or [Homebrew Launcher (Browser)](Homebrew-Launcher-(Browser)), depending on what the [Part 1 - Decrypt9](Part-1-(Decrypt9)) chart specified for your version.
