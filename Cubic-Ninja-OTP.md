This guide relies on the new feature in Decrypt9, CTRNAND injection. As such Part 1 is now entirely based on using one of many possible entrypoints to launch Decrypt9.

If you already have a RedNAND setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

#### What you need

* [Cubic Ninja](http://www.amazon.com//dp/B004SG211I)
* A [game cart](http://www.3dsdb.com/) that contains a version above 4.0.0
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
3. Rename `otp.txt` to `otp.bin` on the root of your SD card (make sure using `right click -> properties` that it is **NOT** named `otp.txt.bin`)
4. Copy `code.bin` to the root of your SD card
5. Copy `load.bin` to the root of your SD card
6. Open Cubic Ninja
7. Select "Create", then "QR Code", then "Scan QR Code"
8. Scan the QR Code in the "What you need" section for your console vesrion
9. Put your SD card in your computer
10. Ensure that `otp.bin` has changed to 256 bytes (using `right click -> properties`)
11. Copy `otp.bin` to a safe folder on your computer
12. Backup `otp.bin` to multiple locations (such as online file storage)
13. [Cart update](https://github.com/Plailect/Guide/wiki/Cart-Update) to a version above 4.0.0 and follow then appropriate steps in [Part 1 - Decrypt9](https://github.com/Plailect/Guide/wiki/Part-1-(Decrypt9))
