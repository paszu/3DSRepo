This is add-on section for region changing your arm9loaderhax CFW SysNAND. This is done by installing the CIAs for and injecting the SecureInfo_A file from the region you want to switch to. This assumes that you already have a way to in CFW SysNAND; if you do not you should follow [this](https://github.com/Plailect/Guide/wiki/Part-5-%28arm9loaderhax-%26-Cakes%29#installing-fbi-into-sysnand) first.

**You MUST have already completed Part 5 and installed arm9loaderhax or you will BRICK.**

**You SHOULD have confirmed functional NAND backups of your arm9loaderhax 3DS (such as `sysNAND-A9LHAX.bin`) in case something goes wrong.**

Region changing does not support the eShop through this method, and it will be updated when I am aware of one that does.

Note that region changing is experimental and can break several things.

Region changing is almost completely unnecessary since Luma3DS now supports Region Free game installs.

#### What you need

* [SecureInfo_A.zip](https://mega.nz/#!4wdwlZpY!yPFb8D7lAFR-dz7yVYg0HeFfak1kge7KB0BvoWe0CHw) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDMlNVa3VJT2N1UFk/view?usp=sharing))
* The latest release of [sysUpdater](https://github.com/profi200/sysUpdater/releases)
* The latest release of [downgrade_check](https://github.com/svanheulen/downgrade_check/releases)
* The 9.2.0 firmware pack zip file for your device and the region you want to switch to:    
**Note that the New 3DS 9.2.0 packs are not the same as the ones in Part 2**
 +    [New 3DS 9.2.0 (Region Change) - EUR](https://mega.nz/#!Rg8XlZaR!-q7Xe_GHyt2MEWrLzKc3rxY2fE47QMFk-VN_3PE5i4w) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDSDdEY1d1Zkg3eDg/view?usp=sharing))    
 +    [New 3DS 9.2.0 (Region Change) - JAP](https://mega.nz/#!x0c3CKBA!zJCScD9i_pVyu3s35N8ap4nLLC6M0GmDyz_VdNunGms) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDTHlWNmlKaFRBM2s/view?usp=sharing))    
 +    [New 3DS 9.2.0 (Region Change) - USA](https://mega.nz/#!1oc0XASa!kAeUYyKEKFwdnE31c2hNHjvavSkE5HThDNLpMqXHH4o) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDUURZUmc2d0VSVW8/view?usp=sharing))    
 ~
 +    [Old 3DS or 2DS 9.2.0 - EUR](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    [Old 3DS or 2DS 9.2.0 - JAP](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24
) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    [Old 3DS or 2DS 9.2.0 - USA](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))    

#### Instructions

1. Copy and merge the `3ds` folder from the downgrade_check zip to the root of your SD card
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
5. Boot into arm9loaderhax Decrypt9 by holding X on CakesFW or L+R on Luma3DS on boot (you will boot to a black screen otherwise)
6. Go to "SysNAND Options" then "File Dump..."
7. "Dump SecureInfo_A" to `sysSecureInfo_A` so you have a backup of your original SecureInfo_A
8. Go back to "SysNAND Options" then "File Inject..."
9. "Inject SecureInfo_A" from `SecureInfo_A` 
7. Press Select on the main menu to eject your SD card
8. Put your SD card in your computer, then rename `sysSecureInfo_A` to `SecureInfo_A-BACKUP`
copy over `SecureInfo_A-BACKUP` to a safe folder on your computer in case you need it in the future
9. Delete `SecureInfo_A-BACKUP` from the root of your SD card
10. Reinsert your SD card into your 3DS, then press Start to reboot
12. Get into the HomeBrew Launcher and launch Downgrade Check
13. Press A to check titles
14. Any extra titles can be removed with FBI as they are leftover from the old region (this is optional)
14. Any missing titles can be downloaded as CIAs with [3DNUS](https://github.com/zoltx23/3DNUS/releases) and installed with FBI
11. Update your region changed CFW SysNAND to the latest version