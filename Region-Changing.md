This is add-on section for region changing your arm9loaderhax CFW SysNAND. This is done by installing the CIAs for and injecting the SecureInfo_A file from the region you want to switch to. This assumes that you already have a way to in CFW SysNAND; if you do not you should follow [this](https://github.com/Plailect/Guide/wiki/Part-5-%28arm9loaderhax-%26-Cakes%29#installing-fbi-into-sysnand) first.

**You MUST have already completed Part 5 and installed arm9loaderhax or you will BRICK.**

**You SHOULD have confirmed functional NAND backups of your arm9loaderhax 3DS (such as `sysNAND-A9LHAX.bin`) in case something goes wrong.**

#### What you need

* [SecureInfo_A.zip](https://mega.nz/#!4wdwlZpY!yPFb8D7lAFR-dz7yVYg0HeFfak1kge7KB0BvoWe0CHw) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDMlNVa3VJT2N1UFk/view?usp=sharing))
* The latest release of [sysUpdater](https://github.com/profi200/sysUpdater/releases)
* The 9.2.0 firmware pack zip file for your device and the region you want to switch to:
 +    [New 3DS 9.2.0 - EUR](https://mega.nz/#!F4U32b4B!tPhl3G0HEmzg5Pd5zQ29ndf1icQqU_LBoogygSL13EY) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDOWpMTWdybzF3TUU))    
 +    [New 3DS 9.2.0 - JAP](https://mega.nz/#!VxcF3TIK!Bm5LgFxo5V4Nepe9ZlWnx7bichE1V7p7pR_HqwimU5M
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDU2plUWwxa2gtV0E/view?usp=sharing))    
 +    [New 3DS 9.2.0 - USA](https://mega.nz/#!gslWiIoK!SF7uFk9rzWTK6oitCDoeAdvphcCzhKWsnTAMXw7zwOU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDbEV2aTRjb1oxekE/view?usp=sharing))    
 ~
 +    [Old 3DS or 2DS 9.2.0 - EUR](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    [Old 3DS or 2DS 9.2.0 - JAP](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    [Old 3DS or 2DS 9.2.0 - USA](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))    

#### Instructions

1. Copy `sysUpdater.cia` from the sysUpdater zip to the root of your SD card
2. Copy `SecureInfo_A` from the folder of the region you want to switch to from `SecureInfo_A.zip` to the root of your SD card
2. Delete any existing `updates` folder from your SD card if there is one
3. Copy the `updates` folder from the 9.2.0 firmware zip to the root of your SD card
4. Eject your SD card and put it back in your 3DS
5. Use FBI to install `sysUpdater.cia`
6. Get back to the home menu then open sysUpdater
7. Press Y to downgrade to the region you want to switch to
11. If you get an error before installation, power off your 3DS by holding the power button and try again (this can take many tries)
13. If you freeze on the "Rebooting in 10 seconds" line for longer than 10 seconds, it is safe to power off your 3DS by holding the power button
5. Boot into arm9loaderhax Decrypt9 by holding X on CakesFW or L+R on AuReiNAND on boot (you will boot to a black screen otherwise)
6. Go to "SysNAND Options" then "File Dump..."
7. "Dump SecureInfo_A" to `sysSecureInfo_A` so you have a backup of your original SecureInfo_A
8. Go back to "SysNAND Options" then "File Inject..."
9. "Inject SecureInfo_A" from `SecureInfo_A` 
7. Press Select on the main menu to eject your SD card
8. Put your SD card in your computer, then rename `sysSecureInfo_A` to `SecureInfo_A-BACKUP`
copy over `SecureInfo_A-BACKUP` to a safe folder on your computer in case you need it in the future
9. Delete `SecureInfo_A-BACKUP` from the root of your SD card
10. Reinsert your SD card into your 3DS, then press Start to reboot
11. Update your region changed CFW SysNAND to the latest version