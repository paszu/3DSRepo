The actual installation of arm9loaderhax itself consists of payload files installed into the firmware partitions on your device's NAND chip, which is soldered to the motherboard itself. These payloads are updated rarely and only really serve the purpose of launching `arm9loaderhax.bin` from the SD Card, which is, in our case, Luma3DS.

So far, arm9loaderhax itself has only been majorly updated once.

The old version of arm9loaderhax (sometimes referred to as "v1" because it was installed using SafeA9LHInstaller v1) was the latest version of [Delebile's initial implementation](https://github.com/delebile/arm9loaderhax).

The new version of arm9loaderhax (sometimes referred to as "v2" because it is installed using SafeA9LHInstaller v2 or FIRM81 because of its use of 8.1's firmware files to make room for larger payloads) is the latest version of [AuroraWright's Fork](https://github.com/AuroraWright/arm9loaderhax) of [Delebile's initial implementation](https://github.com/delebile/arm9loaderhax).

These steps will also update your various payloads and the AES key database.

#### What you need

* <a href="https://plailect.github.io/Guide/data_input_v2.torrent" target="_blank">data_input_v2.zip</a> ([mirror](https://mega.nz/#!RwUDVL5T!65gKJHAAVFk3R0jCA7zRFC5q5QTsL5CLoRUoqhET-WI)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaU53U0MtSHlkTDA))
* The latest release of [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest)
* The latest release of [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases/latest)
* The latest release of [Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases/latest)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest)

#### Instructions

**For all of these instructions, OVERWRITE any existing files on your SD card.**

1. Delete any existing `aeskeydb.bin` from the root of your SD card
2. Copy `aeskeydb.bin` to the `/files9/` folder on your SD card
7. Copy `Hourglass9.bin` from the Hourglass9 zip to the `/luma/payloads/` folder on your SD card and rename `Hourglass9.bin` to `start_Hourglass9.bin`
7. Copy `EmuNAND9.bin` from the EmuNAND9 zip to the `/luma/payloads/` folder on your SD card and rename `EmuNAND9.bin` to `y_EmuNAND9.bin`
7. Copy `Decrypt9WIP.bin` to the `/luma/payloads/` folder on your SD card and rename `Decrypt9WIP.bin` to `x_Decrypt9WIP.bin`
3. Copy `arm9loaderhax.bin` from the SafeA9LHInstaller zip to the `/luma/payloads` folder on your SD card
4. Rename `arm9loaderhax.bin` in `/luma/payloads` to `down_safea9lhinstaller.bin`
5. Copy the `a9lh` folder from `data_input_v2.zip` to the root of your SD Card
6. Copy `payload_stage1.bin` and `payload_stage2.bin` from the arm9loaderhax zip to `a9lh` folder on your SD card
7. Reinsert your SD card into your 3DS
8. Boot the device while holding D-Pad down
9. Press (Select) to update arm9loaderhax
10. Power off the device and put your SD card back in your computer
11. Delete the `a9lh` folder from the root of your SD card
12. Delete `down_safea9lhinstaller.bin` from `/luma/payloads`
13. Reinsert your SD card into your 3DS and boot
