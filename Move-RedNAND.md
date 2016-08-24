This is add-on section for moving the contents of a previous RedNAND to your new SysNAND CFW, then removing the old EmuNAND partition.

**You MUST have already completed Part 3 and installed arm9loaderhax + Luma3DS to use this.**

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

#### What you need

* An existing EmuNAND or RedNAND
* Have completed [Part 3 - arm9loaderhax](Part-3-(arm9loaderhax)) up to the beginning of [Section IV - Restoring the System](Part-3-(arm9loaderhax)#section-iv---restoring-the-system)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)

#### Instructions

1. Copy `EmuNAND9.bin` from the EmuNAND9 zip to the `/luma/payloads/` folder on your SD card and rename `EmuNAND9.bin` to `y_EmuNAND9.bin`
2. Reinsert your SD card into your 3DS
3. Open Hourglass9 from arm9loaderhax by holding (Start) on boot
4. Go to "EmuNAND Backup/Restore", then select the "EmuNAND Backup" option to backup your RedNAND to `NAND_emu.bin`
5. Press (B) to get back to the main menu
6. Go to "SysNAND Backup/Restore", then select the "SysNAND Restore" option to restore your SysNAND from `NAND_emu.bin`
7. Press (Select) to eject your SD card
8. Put your SD card in your computer, then copy `NAND_emu.bin` and `NAND_emu.bin.sha` from the `/files9/` folder on your SD card to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong in the future **(Your backup should match one of the sizes on [this](NAND-Size) page; if it does not, you should delete it and make a new one!)**
9. Delete `NAND_emu.bin` from the `/files9/` folder on your SD card after copying it
10. **Backup every file on your SD card to a folder on your computer, all files will be deleted in the next step**
11. Reinsert your SD card into your 3DS
12. Press (Start) to reboot while holding (Y) to open EmuNAND9
13. Go to "SD Format Options", then "Format SD..."
14. Select the "Format SD (No EmuNAND)" option
15. Press Select on the main menu to eject your SD card
16. Put your SD card in your computer, then copy all your files back into it
13. Navigate to `/Nintendo 3DS/(32 Character ID)/(32 Character ID)/extdata/` on your SD card
    + EUR Region: Delete `00000098`
    + JPN Region: Delete `00000082`
    + USA Region: Delete `0000008f`
14. Reinsert your SD card into your 3DS and boot
12. If you still get a black screen after downgrading and deleting the folder, [follow this troubleshooting guide](Troubleshooting#ts_sys_down)

Continue from [Part 3 - arm9loaderhax - Section V - Injecting FBI](Part-3-(arm9loaderhax)#section-v---removing-rednand-from-your-sd)
