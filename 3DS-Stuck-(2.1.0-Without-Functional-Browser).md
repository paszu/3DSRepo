**IF YOU HAVE A NEW 3DS AND SOMEHOW GET YOURSELF TO 2.1 WITH NO NAND BACKUPS OR A BROKEN BROWSER, DO NOT UPDATE. IF YOU UPDATE FROM A 2.1 NEW 3DS TO A VERSION ABOVE 6.X, YOU WILL BRICK. FOR NOW, YOU MUST RESTORE FROM A NAND BACKUP OF SOME KIND.**

If you downgraded to 2.1.0, **on Old 3DS, 2DS, or New 3DS** but for some reason you have a **nonfunctional browser**, this guide is for you.

If you downgraded to 2.1.0 **on Old 3DS or 2DS** but for some reason have **no functional NAND backups** (with or without a functional browser), you can update to 9.2.0 by updating via a cart to 4.X, then following [this](https://github.com/Plailect/Guide/wiki/9.2.0-Update).

If you downgraded to 2.1.0 **on New 3DS** but for some reason have **no functional NAND backups** (with or without a functional browser), I am working on a possible solution involving EmuNAND + NCSD / Crypto trickery.

If you downgraded to 2.1.0 **2DS** and **left Wireless Communication off** (with or without a functional browser), you can update to 9.2.0 by updating via a cart to any version above 6.X (possibly 4.X as well, read the New 3DS paragraph right below this one), then following [this](https://github.com/Plailect/Guide/wiki/9.2.0-Update).

If you downgraded to 2.1.0 **New 3DS** and **left Wireless Communication off** (with or without a functional browser), you *might* be able to follow this guide **(DO NOT UPDATE, ONLY NAND RESTORE)**. In testing we discovered that a 2.1.0 New 3DS with Wireless Communication off in home menu's settings can turn it back on after updating via cart update to 4.X *(even though this option should not show up because the first device to not have a physical Wireless switch was the 2DS which shipped on 6.0.0; any device with a physical wireless switch does not show this option)*.

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
9. Open the browser and go to `http://dukesrg.no-ip.org/3ds/go/?Launcher.dat` or `http://www.reboot.ms/3ds/load.html?Launcher.dat`
10. If the exploit was successful, you will have booted into Decrypt9
11. Go to SysNAND File Options, then select NAND Restore
12. Restore from NAND Backup bin