Most 3DS CFW applications and software are designed for use with a SysNAND version between 9.0.0 and 9.2.0. If you are below version 9.0.0, you will need to use this guide to update your 3DS without going all the way to the latest version.    

If you are on versions 9.0.0 through 10.7.0 you can just follow the instructions [here](https://github.com/Plailect/Guide/wiki/Get-Started).

If you already have a RedNAND setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

**This will work for EUR/JPN/USA regions ONLY!**

#### What you need

* [Cubic Ninja](http://www.amazon.com//dp/B004SG211I)
* The latest release of [Decrypt9WIP9](https://github.com/d0k3/Decrypt9WIP/releases)
* <a href="https://plailect.github.io/Guide/3ds-private-update-server.torrent" target="_blank">3ds-private-update-server.zip</a> ([mirror](https://mega.nz/#!pgESgZYB!7ijunOSRA3kLF4BUOptrU6etNhuSHOddUvv1gCmdcAU)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDUmFNaUVFQVBtQzQ))
* [WAMPSERVER (PHP 5.5) 2.5](http://www.wampserver.com/en/#download-wrapper)
* [`node.exe`](http://nodejs.org/dist/latest/win-x86/node.exe)
* <a href="https://plailect.github.io/Guide/update.torrent" target="_blank">`update.php`</a> ([mirror](https://gist.githubusercontent.com/Plailect/caaf720be3e131de15d9a335e17cd21e/raw/503077b992ec7ca9a085f69cf9990ae011aa2de9/update.php))
* The v3.2 release of [NTR CFW](https://github.com/44670/BootNTR/releases/tag/3.2)
* The latest release of <a href="https://plailect.github.io/Guide/NTR%20Debugger.torrent" target="_blank">NTR Debugger</a> ([mirror](https://mega.nz/#!R1FRhLwa!5QzqrSQJoo7ZSJN0jyPeHcArtUTGbSrixDUEqEH2qY4)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDVndWRkFLV0ZsbVk))
* The 9.2.0 firmware pack zip file for your device and region:  
 +    <a href="https://plailect.github.io/Guide/9.2.0-20J(Full)_n3DS.torrent" target="_blank">New 3DS 9.2.0 - JPN</a> ([mirror](https://mega.nz/#!VxcF3TIK!Bm5LgFxo5V4Nepe9ZlWnx7bichE1V7p7pR_HqwimU5M)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDU2plUWwxa2gtV0E/view?usp=sharing))    
~    
 +    <a href="https://plailect.github.io/Guide/9.2.0-20E(Full).torrent" target="_blank">Old 3DS or 2DS 9.2.0 - EUR</a> ([mirror](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    <a href="https://plailect.github.io/Guide/9.2.0-20J(Full).torrent" target="_blank">Old 3DS or 2DS 9.2.0 - JPN</a> ([mirror](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    <a href="https://plailect.github.io/Guide/9.2.0-20U(Full).torrent" target="_blank">Old 3DS or 2DS 9.2.0 - USA</a> ([mirror](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))

#### Instructions

##### Section I - Prep Work

1. Install WAMP to the default directory
2. Copy the contents of `3ds-private-update-server.zip` to `C:\wamp\www\` (overwrite existing files)
3. Copy `update.php` to `C:\wamp\www\` (overwrite existing files)
6. Copy the `updates` folder from the 9.2.0 firmware zip to `C:\wamp\www\`
3. Move `node.exe` to `C:\wamp\www\updates`
3. Move `C:\wamp\www\CdnCiaUnpack.js` to `C:\wamp\www\updates`
4. In the `C:\wamp\www\updates` directory, drag `CdnCiaUnpack.js` onto `node.exe` to create `GetSystemUpdate.partial.xml`
5. Move `node.exe`, `CdnCiaUnpack.js`, and `GetSystemUpdate.partial.xml` back to `C:\wamp\www\`
6. Click the WAMP icon in your system tray, then click "Put Online"
7. Use the command "ipconfig" in CMD to get your computer's IPv4 Address, you will need it soon
8. Copy `ntr.bin` to the root of your SD card
1. Create a folder named `files9` on the root of your SD card if it does not already exist
2. Copy and merge the `3ds` folder from the Decrypt9WIP zip to root of your SD card

##### Section II - Updating

1. Boot your 3DS into recovery mode by holding L+R+A+UP while powering on
2. Decline the update and reboot
3. Open Cubic Ninja (if it already has NinjHax installed, hold L+R+X+Y to reset it)
4. Select "Create", then "QR Code", then "Scan QR Code"
5. Scan the QR code in the NTR CFW zip for your region
6. On the home menu, press Y and X at the same time to open NTR's menu
7. Enable the debugger and close the menu
8. Use your router's web page to get your 3DS's IP address (google it if you don't know how, all routers are different)
9. Run NTR Debugger on your computer
10. Enter the following commands (replace 192.168.1.100 with your 3DS's IP address and 192.168.1.200 with your computer's IP address)    
    + `connect("192.168.1.100", 8000)`
    + `write(0x15E424, tuple(map(ord, "http://192.168.1.200/update.php\0")), pid=0x25)`
    + `write(0x15E0EC, tuple(map(ord, "http://192.168.1.200/update.php\0")), pid=0x25)`
    + `write(0x15E463, tuple(map(ord, "http://192.168.1.200/update.php\0")), pid=0x25)`
11. Update your 3DS by going to System Settings, then "Other Settings", then going all the way to the right and using "System Update"

##### Section III - Decrypt9

1. Check the system settings, you should be on 9.2.0
2. Launch the Homebrew Launcher using the entrypoint of your choice (such as [ninjhax2](https://smealum.github.io/ninjhax2/))
3. Open Decrypt9WIP **(This can sometimes take a few tries)**

You can now continue from [Part 2 - 2.1.0 ctrtransfer](https://github.com/Plailect/Guide/wiki/Part-2-(2.1.0-ctrtransfer)).
