This guide relies on the new feature in Decrypt9, CTRNAND injection. As such Part 1 is now entirely based on using one of many possible entrypoints to launch Decrypt9.

If you already have a RedNAND setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

#### What you need

* DS flashcard that works on your 3DS version
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)

#### Instructions

1. Create a folder named `files9` on the root of your SD card if it does not already exist
2. Copy `Launcher.dat` and `Decrypt9WIP.dat` from the Decrypt9WIP zip to the root of your SD card
4. Reinsert your SD card into your 3DS
5. Put `Decrypt9.nds` from the Decrypt9 zip on your DS flashcard
6. Start your DS flashcard from your 3DS
7. Boot `Decrypt9.nds` using your flashcart
8. Select the correct option for your system version
    + 4.X.X -> "4.x Decrypt9WIP"
    + 6.X.X -> "6.x Decrypt9WIP"
9. Reboot the system, then go to System Settings, then "Other Settings", then "Profile", then "Nintendo DS Profile"
10. If the exploit was successful, you will have booted into Decrypt9

You can now continue from [Part 2 - 2.1.0 ctrtransfer](../Part-2-(2.1.0-ctrtransfer)).
