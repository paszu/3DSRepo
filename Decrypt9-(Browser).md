This guide relies on the new feature in Decrypt9, CTRNAND injection. As such Part 1 is now entirely based on using one of many possible entrypoints to launch Decrypt9.

If you already have a RedNAND setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

#### What you need

* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)

#### Instructions

1. Create a folder named `files9` on the root of your SD card if it does not already exist
2. Copy `Launcher.dat` and `Decrypt9WIP.dat` from the Decrypt9WIP zip to the root of your SD card
4. Reinsert your SD card into your 3DS
5. Open the browser and go to one of the following URLs on your 3DS
    + `https://dukesrg.github.io/?Decrypt9WIP.dat`
    + `http://go.gateway-3ds.com/`
    + `http://www.reboot.ms/3ds/load.html?Launcher.dat`
    + `http://dukesrg.dynu.net/3ds/rop?GW17567.dat&Launcher.dat`
    + If you get an error, [follow this troubleshooting guide](Troubleshooting#ts_browser)
6. If the exploit was successful, you will have booted into Decrypt9

You can now continue from [Part 2 - 2.1.0 ctrtransfer](Part-2-(2.1.0-ctrtransfer)).
