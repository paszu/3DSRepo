**Before beginning the guide, you must know the risks of 3DS hacking: EVERY time you modify your system, there is always the potential for an UNRECOVERABLE brick. They're rare, but still a possibility so make sure you follow ALL directions EXACTLY.**

Each part of this guide is designed to be able to be used independently from the other parts, so anyone can start at the part that applies to their situation. As a result, software may be listed multiple times in different "What you need" sections. You do not need to download software multiple times.

This guide is split into two major categories: New 3DS and Old 3DS / 2DS.

The New 3DS is a more complicated device to perform this installation on, since it was never designed to run 2.1.0, which we need to downgrade to as part of the arm9loaderhax process (see [OTP Info](https://github.com/Plailect/Guide/wiki/OTP-Info) for why).

The Old 3DS and 2DS are extremely similar devices internally. The only major difference that matters for this guide is that, although you are never instructed to do this, you must never perform a system format on a 2DS while it is below firmware version 6.0.0, or you will be unable to complete the initial setup and will be stuck.

**Your SD card should be [MBR, not GPT](http://www.howtogeek.com/245610/)**.

If you need to format a brand new SD card, you can use [this](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm) tool set to an Allocation Unit Size of 32K.

___

### The following applies to all devices:

**<9.0.0 [WITH BROWSER]**: You can find instructions for updating to 9.2.0-20 [here](https://github.com/Plailect/Guide/wiki/9.2.0-Update). Browserhax (used in Part 1) does not support versions below 9.0.0.

**9.0.0 - 9.2.0 (with an existing CFW)**: Change menuhax to type 1, set your menuhax trigger to D-Pad down, then start the guide at Part 4.

**9.0.0 - 9.2.0 (without an existing CFW) [WITH BROWSER]**: Start on "Part 1 - Homebrew" then skip most of "Part 2 - 9.2.0 Downgrade" (more info on that page).    
  + (9.0.0 and 9.1.0 are virtually identical to 9.2.0)

**9.3.0 - 9.8.0 [WITH BROWSER]**: Start on "Part 1 - Homebrew," but skip changing the date and time and initializing savedata in the beginning.

**9.9.0 - 10.6.0 [WITH BROWSER]**: Start on "Part 1 - Homebrew"

**\>=9.0.0 [WITHOUT BROWSER\] (indicated by the last number in the version, such as 11.0.0*-33*, being *-0*):** Use the following instructions for various alternate entrypoints in place of Part 1
  + [Ninjhax](http://smealum.github.io/ninjhax2/) (requires Cubic Ninja)    
  + [smashbroshax](https://gbatemp.net/threads/397194/) (requires Super Smash Bros. and **only works on New 3DS**)
  + [oot3dhax](https://github.com/yellows8/oot3dhax) (requires Ocarina of Time 3D and either a powersaves or another 3DS which has the HomeBrew Launcher)       
  + [supermysterychunkhax](https://smd.salthax.org/) (requires Pokemon Super Mystery Dungeon and another 3DS which has the HomeBrew Launcher)
  + [freakyhax](http://plutooo.github.io/freakyhax/) (requires Freakyforms Deluxe)
  + [basehaxx](http://mrnbayoh.github.io/basehaxx/) (requires Pokemon Omega Ruby/Alpha Sapphire ver 1.0/1.4 with the ability to have a secret base and another 3DS which has the HomeBrew Launcher)
  + [BASICSploit](https://mrnbayoh.github.io/basicsploit/) (requires SmileBASIC)
  + [smilehax](https://plutooo.github.io/smilehax/) (requires SmileBASIC)
  + [stickerhax](https://github.com/yellows8/stickerhax) (requires Paper Mario: Sticker Star and another 3DS which has the HomeBrew Launcher)\

**\>=10.7.0 [WITH BROWSER]**: Start on "Part 1 - Homebrew"
  + **Set your primary DNS to `107.211.140.065` so as not to trigger the browser version check.**
  + If on this browser version, you ever receive a message to update your browser, you will need an alternate entry point from below as your browser will have detected it is not running the latest version.
  + Once this message appears for the first time, it is impossible to get rid of it so you must get an alternate entrypoint.

**11.0.0**: [Downgrade your firmware](https://github.com/Plailect/Guide/wiki/Firmware-Downgrade), then follow the >=10.7.0 instructions above.

**If you are using a game for hax because your browser version is incompatible, you will need to enter HomeBrew Launcher using it and install menuhax. After installing menuhax, you no longer need the game to complete the rest of the guide.**
