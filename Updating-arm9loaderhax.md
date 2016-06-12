The actual installation of arm9loaderhax itself consists of payload files installed into the firmware partitions on your device's NAND chip, which is soldered to the motherboard itself. These payloads are updated rarely and only really serve the purpose of launching `arm9loaderhax.bin` from the SD Card, which is, in our case, Luma3DS.

So far, arm9loaderhax itself has only been majorly updated once.

The old version of arm9loaderhax (sometimes referred to as "v1" because it was installed using SafeA9LHInstaller v1) was the latest version of [Delebile's initial implementation](https://github.com/delebile/arm9loaderhax).

The new version of arm9loaderhax (sometimes referred to as "v2" because it is installed using SafeA9LHInstaller v2 or FIRM81 because of its use of 8.1's firmware files to make room for larger payloads) is the latest version of [AuroraWright's Fork](https://github.com/AuroraWright/arm9loaderhax) of [Delebile's initial implementation](https://github.com/delebile/arm9loaderhax).

The advantages to updating at this time are very minor and only really ensure compatibility with future `arm9loaderhax.bin` files, and is as such completely optional.

[CtrBootManager9 users, you must use [OperationNT414C's fork of CtrBootManager](https://github.com/OperationNT414C/CtrBootManager/releases/tag/V7) which is compatible with arm9loaderhax v2.

Screeninit arm9loaderhax payloads turn on the screen before handing control over to arm9loaderhax.bin (making sure it works with all arm9loaderhax.bin files), while noscreeninit arm9loaderhax payloads do not (allowing arm9loaderhax.bin to control things like brightness during boot). You can choose to use either (the guide used to only have screeninit payloads).

#### What you need

* [data_input**_v2**.zip](https://mega.nz/#!RwUDVL5T!65gKJHAAVFk3R0jCA7zRFC5q5QTsL5CLoRUoqhET-WI) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaU53U0MtSHlkTDA))
* The latest release of [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases)
* The latest release of [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases)

#### Instructions

2. Copy `arm9loaderhax.bin` from the SafeA9LHInstaller zip to the `/luma/payloads` root of your SD card
1. Rename `arm9loaderhax.bin` in `/luma/payloads` to `down_safea9lhinstaller.bin`
3. Copy the `a9lh` folder from `data_input_v2.zip` to the root of your SD Card
4. Copy `payload_stage1.bin` and `payload_stage2.bin` from the arm9loaderhax zip to `a9lh` folder on your SD card
5. Reinsert your SD card into your 3DS
6. Boot the device while holding D-Pad down
7. Press Select to update arm9loaderhax
8. Power off the device and put your SD card back in your computer
9. Delete the `a9lh` folder from the root of your SD card
10. Delete `down_safea9lhinstaller.bin` from `/luma/payloads`
11. Reinsert your SD card into your 3DS and boot
