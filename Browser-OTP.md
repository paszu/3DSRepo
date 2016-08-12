This guide relies on the new feature in Decrypt9, CTRNAND injection. As such Part 1 is now entirely based on using one of many possible entrypoints to launch Decrypt9.

If you already have a RedNAND setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

#### What you need

* The latest release of [OTPHelper](https://github.com/d0k3/OTPHelper/releases/)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)

#### Instructions

##### Section I - Getting the OTP

1. Create a folder named `files9` on the root of your SD card if it does not already exist
2. Copy `arm11.bin` and `arm9.bin` from the OTPHelper zip to the root of your SD card
3. Reinsert your SD card into your 3DS
4. Go to http://dukesrg.github.io/2xrsa.html?arm11.bin on your 3DS
5. OTPHelper will launch, then select the "Dump otp.bin (0x100)" option
6. Press Select on the main menu to eject your SD card
7. Put your SD card in your computer, then copy over `otp.bin` from `/files9/` to a safe folder on your computer.
8. Ensure that `otp.bin` is 256 bytes
9. Backup `otp.bin` to multiple locations (such as online file storage)

##### Section II - Launching Decrypt9

1. Delete `arm9.bin` from the root of your SD card
2. Copy `Decrypt9WIP.bin` to the root of your SD card
3. Rename `Decrypt9WIP.bin` to `arm9.bin` on the root of your SD card
4. Reinsert your SD card into your 3DS
5. Go to http://dukesrg.github.io/2xrsa.html?arm11.bin on your 3DS
    + If you get an error, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_browser)
6. If the exploit was successful, you will have booted into Decrypt9

##### Section III - Injecting CTRNAND

// ???

You can now continue from [Part 2 - 2.1.0 CTRNAND](https://github.com/Plailect/Guide/wiki/Part-2-(2.1.0-CTRNAND)).
