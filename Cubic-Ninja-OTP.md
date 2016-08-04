Most 3DS CFW applications and software are designed for use with a SysNAND version between 9.0.0 and 9.2.0. If you are below version 9.0.0, you will need to use this guide to update your 3DS without going all the way to the latest version.    

If you are on versions 9.0.0 through 10.7.0 you can just follow the instructions [here](https://github.com/Plailect/Guide/wiki/Get-Started).

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

This section of the guide is just a part of the larger [9.2.0 Update](https://github.com/Plailect/Guide/wiki/9.2.0-Update) section.

#### What you need

* [Cubic Ninja](http://www.amazon.com//dp/B004SG211I)
* <a href="https://plailect.github.io/Guide/code.torrent" target="_blank">code.bin</a> ([mirror](https://mega.nz/#!90ExEJBa!_w5KYJIEM4NX0C5YwjCNSkt0nR2Bj-wc9C58fB3dFu0)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDdjBMRGV5TW85aVk))
* <a href="https://plailect.github.io/Guide/load.torrent" target="_blank">load.bin</a> ([mirror](https://mega.nz/#!lss0VQwY!eDBMwrbpw3wapA82cNOYCJOAxYQPoHZz0AuW-dMOIqo)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDeF9NbVZOTjdKRlU))
* The Cubic Ninja QR Code for your version    
  + [1.0.0 QR](https://i.imgur.com/7Q35Tuy.png) (<a href="https://plailect.github.io/Guide/1.0.0_qr.torrent" target="_blank">mirror</a>)    
  + [1.1.0 QR](https://i.imgur.com/vq8D7Mz.png) (<a href="https://plailect.github.io/Guide/1.2.0_qr.torrent" target="_blank">mirror</a>)    
  + [2.1.0 QR](https://i.imgur.com/VP1D8vt.png) (<a href="https://plailect.github.io/Guide/2.1.0_qr.torrent" target="_blank">mirror</a>)    
  + [2.2.0 QR](https://i.imgur.com/hGnRAq8.png) (<a href="https://plailect.github.io/Guide/2.2.0_qr.torrent" target="_blank">mirror</a>)    

#### Instructions

1. [**Set windows to show file extensions**](https://support.microsoft.com/en-us/kb/865219) (for windows users)
2. Create a blank text file named `otp.txt` on the root of your SD card
2. Rename `otp.txt` to `otp.bin` on the root of your SD card (make sure using `right click -> properties` that it is **NOT** named `otp.txt.bin`)
1. Copy `code.bin` to the root of your SD card
2. Copy `load.bin` to the root of your SD card
3. Open Cubic Ninja
4. Select "Create", then "QR Code", then "Scan QR Code"
5. Scan the QR Code in the "What you need" section for your console vesrion
6. Put your SD card in your computer
8. Ensure that `otp.bin` has changed to 256 bytes (using `right click -> properties` or something similar)
6. Copy `otp.bin` to a safe folder on your computer
8. Backup `otp.bin` to multiple locations (such as online file storage)

You can now do the following **in order**:
+ Update to 9.2.0 with one of the methods in the relevant section of the 9.2.0 Update chart [here](https://github.com/Plailect/Guide/wiki/9.2.0-Update)
+ Do [Part 1 - Homebrew](https://github.com/Plailect/Guide/wiki/Part-1-(Homebrew))
+ Do [Part 4 - 2.1.0 Downgrade](https://github.com/Plailect/Guide/wiki/Part-4-(2.1.0-Downgrade)#section-ii---injecting-fbi) (Section II - Injecting FBI **Only**, use "SysNAND Options" instead of "EmuNAND Options")
+ Do [Part 5 - arm9loaderhax](https://github.com/Plailect/Guide/wiki/Part-5-(arm9loaderhax))
    + Copy SafeA9LHInstaller's 3ds folder and dat file instead of the arm9 and arm11 bin files
    + Copy `otp.bin` to `/a9lh/`
    + Launch SafeA9LHInstaller from Homebrew menu instead of browser
    + Skip steps related to "emergency files"
    + Skip steps related to "RedNAND"
    + Skip Section IV and Section V
    + Update to the latest system version after completing Section VI