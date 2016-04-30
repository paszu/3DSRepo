**IF YOU HAVE A NEW 3DS AND SOMEHOW GET YOURSELF TO 2.1 WITH NO NAND BACKUPS OR A BROKEN BROWSER, DO NOT UPDATE. IF YOU UPDATE FROM A 2.1 NEW 3DS TO A VERSION ABOVE 6.X, YOU WILL BRICK. FOR NOW, YOU MUST RESTORE FROM A NAND BACKUP OF SOME KIND.**

If you downgraded to 2.1.0, **on Old 3DS, 2DS, or New 3DS** but for some reason you have a **nonfunctional browser**, this guide is for you.

If you downgraded to 2.1.0 **on Old 3DS or 2DS** but for some reason have **no functional NAND backups** (with or without a functional browser), you can update to 9.2.0 by updating via a cart to 4.X, then following [this](https://github.com/Plailect/Guide/wiki/9.2.0-Update).

If you downgraded to 2.1.0 **on New 3DS** but for some reason have **no functional NAND backups** (with or without a functional browser), we are working on a possible solution involving EmuNAND + NCSD / Crypto trickery. For an overview of how this will be done, read [this](http://gbatemp.net/threads/424476/#post-6299678) post.

If you downgraded to 2.1.0 on **New 3DS** or **2DS** and **left Wireless Communication off** (with or without a functional browser), you can reset the wireless to be on by removing the battery for several seconds then booting back up.

#### What you need

* A [game cart](http://www.3dsdb.com/) that contains a 4.X update
* [Decrypt9WIP 20160118](https://github.com/d0k3/Decrypt9WIP/releases/tag/20160118)
* A valid NAND backup of some kind.

#### Instructions

3. Copy `Launcher.dat` from the Decrypt9WIP zip to the root of your SD card
4. Copy your NAND backup to your SD card
6. Launch your game cart which contains a **4.X** update
7. Accept the update when prompted
8. Wait for it to reboot you
9. Open the browser and go to `http://www.reboot.ms/3ds/load.html?Launcher.dat`
10. If the exploit was successful, you will have booted into Decrypt9
11. Go to SysNAND File Options, then select NAND Restore
12. Restore from `sysNAND_original.bin`
