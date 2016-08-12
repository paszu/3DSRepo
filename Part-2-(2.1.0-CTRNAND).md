**If you somehow get yourself stuck on 2.1.0, read all information on [this](https://github.com/Plailect/Guide/wiki/2.1.0-Stuck) page before attempting anything. It could save you from a brick!**

The OTP is a console unique region from which console specific keys seem to be derived, although it is unknown how.

The OTP is a requirement to use arm9loaderhax, which gets you, among other things, 100% boot rate and very early Arm9 access allowing you to unbrick yourself without a hardmod and use other awesome tools.

Since version 3.0, the OTP is locked out early in sysNAND boot. There is a New 3DS only exploit that works on 9.6, but it requires extra hardware. The solution we are using is to flash a 2.1.0 [CTRNAND](https://www.3dbrew.org/wiki/Flash_Filesystem#CTR_partition) partition and firmware to the device, allowing us to retrieve the OTP.

More info [here](https://github.com/Plailect/Guide/wiki/OTP-Info) and [here](https://3dbrew.org/wiki/OTP_Registers).

**You MUST use the correct CTRNAND for your console region or you will BRICK.**

#### Overview of steps

In this section, we will be flashing your console's [CTRNAND](https://www.3dbrew.org/wiki/Flash_Filesystem#CTR_partition) partition to 2.1.0 in order to take advantage of an oversight in 2.1.0 for the purpose of extracting the [OTP](https://github.com/Plailect/Guide/wiki/OTP-Info) unique to your console. This OTP file is required to install arm9loaderhax, and **cannot** be shared with other consoles.

This is accomplished by installing a premade ctrtransfer image containing 2.1.0, copying your console specific files (such as `moveable.sed` and `SecureInfo_A`) to it, then fixing the title databases.

On New 3DS, it also swaps CTRNAND's encryption slot and installs an Old 3DS NCSD header to NAND, allowing it to boot the Old 3DS only 2.1.0 firmware.

#### What you need

* You will need to have booted into Decrypt9 via one of the [Part 1 - Decrypt9](https://github.com/Plailect/Guide/wiki/Part-1-(Decrypt9)) entrypoints
* The 2.1.0 ctrtransfer image for your device and region:
  +    <a href="https://plailect.github.io/Guide/2.1.0-4E_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 2.1.0 - EUR - ctrtransfer</a> ([mirror]()) ([mirror]())    
  +    <a href="https://plailect.github.io/Guide/2.1.0-4J_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 2.1.0 - JPN - ctrtransfer</a> ([mirror]()) ([mirror]())    
  +    <a href="https://plailect.github.io/Guide/2.1.0-4U_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 2.1.0 - USA - ctrtransfer</a> ([mirror]()) ([mirror]())

#### Instructions

##### Section I - Prep Work

You should be in Decrypt9 for these steps. If you are not in Decrypt9, follow [Part 1 - Decrypt9](https://github.com/Plailect/Guide/wiki/Part-1-(Decrypt9))

1. Go to SysNAND Options, then SysNAND Backup/Restore, then backup **(min size)** SysNAND to `NANDmin.bin`
2. Press Select on the main menu to eject your SD card
3. Put your SD card in your computer, then copy `NANDmin.bin` and `NANDmin.bin.sha` from the `/files9/` folder on your SD card to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong in the future **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
4. Delete `NANDmin.bin` and `NANDmin.bin.sha` from the `/files9/` folder on your SD card after copying it
5. Copy the 2.1.0 ctrtransfer image to the `/files9/` folder on your SD card
5. Reinsert your SD card into your 3DS

##### Section II - Injecting CTRNAND

// ???

*(On 2DS at 2.1.0, the screen being stretched is normal)*

**Putting a New 3DS on 2.1.0 in sleep mode is known to cause an UNRECOVERABLE brick! You should avoid closing your device and, without delay, go directly to [Part 3 - arm9loaderhax](https://github.com/Plailect/Guide/wiki/Part-3-(Decrypt9)) to prevent this!**

You can now continue from [Part 3 - arm9loaderhax](https://github.com/Plailect/Guide/wiki/Part-3-(arm9loaderhax)).