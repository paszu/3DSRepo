**Before beginning the guide, you must know the risks of 3DS hacking: EVERY time you modify your system, there is always the potential for an UNRECOVERABLE brick. They're rare, but still a possibility so make sure you follow ALL directions EXACTLY.**

Each part of this guide is designed to be able to be used independently from the other parts, so anyone can start at the part that applies to their situation. As a result, software may be listed multiple times in different "What you need" sections. You do not need to download software multiple times.

This guide is split into two major categories: New 3DS and Old 3DS / 2DS.

The New 3DS is a more complicated device to perform this installation on, since it was never designed to run 2.1.0, which we need to downgrade to as part of the arm9loaderhax process (see [OTP Info](https://github.com/Plailect/Guide/wiki/OTP-Info) for why).

The Old 3DS and 2DS are extremely similar devices internally. The only major difference that matters for this guide is that, although you are never instructed to do this, you must never perform a system format on a 2DS while it is below firmware version 6.0.0, or you will be unable to complete the initial setup and will be stuck.

If you need to format a brand new SD card, you can use [this](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm) tool set to an Allocation Unit Size of 32K.

*The following applies to all devices:*

**If you already have a CFW setup on any version between 9.0.0 and 9.2.0, change menuhax to type 1, set your menuhax trigger to D-Pad down, then start the guide at Part 4. Note that anywhere "RedNAND" is mentioned, you can pretend it says "EmuNAND" instead as they are very similar and the instructions will be the same other than that.**

If your version is below 9.0.0, follow the instructions on the "9.2.0 Update" page to update directly to 9.2.0. 

If you are on 9.0.0 or 9.1.0 you are fine where you are as both are almost identical to 9.2.0.

If your version is between 9.0.0 and 9.2.0, start on "Part 1 - Homebrew" then skip most of "Part 2 - Downgrading" (more info on that page).

If your version is between 9.3.0 and 10.7.0, start on "Part 1 - Homebrew" and follow all instructions.

**If you followed an old version of this guide that did not include Updated SysNAND and want to switch to Updated SysNAND + Luma3DS, just restore your SysNAND from a pre-arm9loaderhax SysNAND backup *(such as `sysNAND_original.bin`)* using Decrypt9 and follow all of Part 5.**