**If you somehow get yourself stuck on 2.1.0, read all information on [this](https://github.com/Plailect/Guide/wiki/2.1.0-Stuck) page before attempting anything. It could save you from a brick!**

The OTP is a console unique region from which console specific keys seem to be derived, although it is unknown how.

The OTP is a requirement to use arm9loaderhax, which gets you, among other things, 100% boot rate and very early ARM9 kernel access allowing you to unbrick yourself without a hardmod and use other awesome tools.

Since version 3.0, the OTP is locked out early in sysNAND boot. There is a New 3DS only exploit that works on 9.6, but it requires extra hardware. The solution we are using is to flash a 2.1.0 [CTRNAND](https://www.3dbrew.org/wiki/Flash_Filesystem#CTR_partition) partition and firmware to the device, allowing us to retrieve the OTP.

More info [here](https://github.com/Plailect/Guide/wiki/OTP-Info) and [here](https://3dbrew.org/wiki/OTP_Registers).

**You MUST use the correct CTRNAND for your console region or you will BRICK.**

#### Overview of steps

In this section, we will be flashing your console's [CTRNAND](https://www.3dbrew.org/wiki/Flash_Filesystem#CTR_partition) partition to 2.1.0 in order to take advantage of an oversight in 2.1.0 for the purpose of extracting the [OTP](https://github.com/Plailect/Guide/wiki/OTP-Info) unique to your console. This OTP file is required to install arm9loaderhax, and **cannot** be shared with other consoles.

This is accomplished by installing a premade ctrtransfer image containing 2.1.0, copying your console specific files (such as `moveable.sed` and `SecureInfo_A`) to it, then fixing the title databases. On New 3DS, it also swaps CTRNAND's encryption slot and installs an Old 3DS NCSD header to NAND, allowing it to boot the Old 3DS only 2.1.0 firmware.

#### What you need

* You will need to have booted into Decrypt9 via one of the [Part 1 - Decrypt9](https://github.com/Plailect/Guide/wiki/Part-1-(Decrypt9)) entrypoints
* The 2.1.0 ctrtransfer image for your device and region:
  +    <a href="https://plailect.github.io/Guide/2.1.0-4E_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 2.1.0 - EUR - ctrtransfer</a> ([mirror](https://mega.nz/#!ltsF3SwB!A_yQJ7TpkYD6OF38q4oes7dI1G3574v0wF_WXP8-_3E)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDZnp3SjhGSVFYa3c))    
  +    <a href="https://plailect.github.io/Guide/2.1.0-4J_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 2.1.0 - JPN - ctrtransfer</a> ([mirror](https://mega.nz/#!VhkGCQSQ!nnWrKUazSHRXIiPtGKCoDp9gT5yQDyo4J0x9TMNHJP4)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDMzdLM3hyVnlsVWc))    
  +    <a href="https://plailect.github.io/Guide/2.1.0-4U_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 2.1.0 - USA - ctrtransfer</a> ([mirror](https://mega.nz/#!FtshlJ5D!4GC-GUNhzzPefLGJA7wRIKaj8J-pbVQHFJFkx6MUaLA)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDa2gwRHdKczMzbWs))
  +    If your device is not from one of the three above regions, you should pick one of them, then additionally copy the corresponding [`ctrtransfer.secnfo`](https://plailect.github.io/Guide/ctrtransfer.secnfo.torrent) ([mirror](https://mega.nz/#!1xN1RRzK!rrYkYewOwkhHZ16una5wGUQcrytG-OrDGB-_jIm62dI)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDWExJaEw1ZDVQaVk)) to `/files9/`

#### Instructions

You should be in Decrypt9 for these steps. If you are not in Decrypt9, follow [Part 1 - Decrypt9](https://github.com/Plailect/Guide/wiki/Part-1-(Decrypt9))

1. Copy the 2.1.0 ctrtransfer image for your device and region to the `/files9/` folder on your SD card
2. Reinsert your SD card into your 3DS
1. Go to "SysNAND Options", then "SysNAND Transfer", then "Auto CTRNAND Transfer"
2. Select the 2.1.0 ctrtransfer image when prompted by pressing A
2. Backup SysNAND to `NANDmin.bin` when prompted by pressing A
3. Allow the transfer process to proceed automatically, this may take some time
2. Once the transfer is complete, press Select to eject your SD card
3. Put your SD card in your computer, then copy `NANDmin.bin` and `NANDmin.bin.sha` from the `/files9/` folder on your SD card to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong in the future **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
4. Delete the 2.1.0 ctrtransfer image from the `/files9/` folder on your SD card after copying it
5. Leave your SD card out of your 3DS
6. Press Start to reboot with no SD card inserted
    + You can insert the SD card on 2.1 after the device has reached the home menu, but it will not complete the bootup process if you insert it before then

*(On 2DS at 2.1.0, the screen being stretched is normal)*

**Putting a New 3DS on 2.1.0 in sleep mode is known to cause an UNRECOVERABLE brick! You should avoid closing your device and, without delay, go directly to [Part 3 - arm9loaderhax](https://github.com/Plailect/Guide/wiki/Part-3-(Decrypt9)) to prevent this!**

You can now continue from [Part 3 - arm9loaderhax](https://github.com/Plailect/Guide/wiki/Part-3-(arm9loaderhax)).