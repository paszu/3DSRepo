+ <a name="faq_latestfw" />**Q:** *I am on the latest firmware version, is my device hackable?*    
  **A:** Normally the answer is no, but at the time of writing the latest version (10.7.0) is hackable as long as you have a compatible game.

+ <a name="faq_updatecfw" />**Q:** *How do I update CakesFW / AuReiNAND?*    
  **A:** Usually you just have to copy the latest version to your SD card and overwrite the old version, although the release notes for each may contain additional instructions.

+ <a name="faq_rednand" />**Q:** *What is the difference between RedNAND and EmuNAND?*    
  **A:** RedNAND and EmuNAND are both different types of [NAND redirection](http://3dbrew.org/wiki/NAND_Redirection) with small differences in the way they are handled behind the scenes. The main advantage to using RedNAND instead of EmuNAND is that RedNAND will *always* use the smallest [NAND size](https://github.com/Plailect/Guide/wiki/NAND-Size) the device offers, regardless of the size of the SysNAND chip. For example, a New 3DS user with a 1.8GB internal NAND chip will only have to use 1.2GB for all RedNAND backups.

+ <a name="faq_gatewaysky" />**Q:** *I heard about this thing I have to pay for (Gateway, Sky3DS, etc), is that something I need?*    
  **A:** No. Arm9loaderhax is a superior method of loading hax that runs early in boot and opens up the opportunity for things such as true custom firmware.

+ <a name="faq_need" />**Q:** *What do I need to do this guide?*    
  **A:** This guide can be completely done with free software and **(if you are on 10.6.0 or 10.7.0)** a compatible game such as **([Ocarina of Time 3D](http://www.nintendo.com/games/detail/the-legend-of-zelda-ocarina-of-time-3d-3ds) + either a [PowerSaves Pro](http://www.amazon.com/dp/B00IVJ1M7M/) or an already haxed 3DS)** OR **([Cubic Ninja](http://www.amazon.com/dp/B004SG211I) (works without any extras))**    
    *Note: If you are using a game for hacks, you will need to enter homebrew launcher using it instead of browserhax or menuhax while on 10.6.0/10.7.0. After completing the initial 9.2.0 downgrade, you no longer need the game to complete the rest of the guide.*

+ <a name="faq_risky" />**Q:** *How risky is hacking my console?*    
  **A:** Bricks are now *basically* impossible unless you ignore/circumvent all safety checks.

+ <a name="faq_piracy" />**Q:** *Can I pirate games with this?*    
  **A:** Yes.

+ <a name="faq_piracy_online" />**Q:** *Can I play online with pirated games without getting banned?*    
  **A:** If you installed the CIA file, you won't get banned. If you are using a flashcart, you might be.

+ <a name="faq_piracy_header" />**Q:** *Do I need this thing I heard about called a private header?*    
  **A:** Those are only needed for flashcarts, not CIA installed games.

+ <a name="faq_homebrew" />**Q:** *Can I run awesome homebrew and emulators with this?*    
  **A:** Yes! Custom Firmware not only enables the Homebrew Launcher, but it also will give you hacks on all versions, which means you keep it forever, even with updates.

+ <a name="faq_regionfree" />**Q:** *Can I use this to play games from other regions?*    
  **A:** AuReiNAND supports Region Free patches, which enable users to install games from any region without any extra modification or steps.

+ <a name="faq_arn2cakes" />**Q:** *How do I switch from the old guide to Updated SysNAND + Cakes?*    
  **A:** Just restore your SysNAND from a pre-arm9loaderhax SysNAND backup and follow all of Part 5.

+ <a name="faq_updates" />**Q:** *Is it safe to update CFW SysNAND?*    
  **A:** Yes, but if you are feeling apprehensive you can wait until there is confirmation it works.

+ <a name="faq_support" />**Q:** *Where should I go for support?*    
  **A:** For support, contact me or any other channel operator at [#3dshacks on Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4).

+ <a name="faq_le4gbsd" />**Q:** *Can I do this with a 4GB (or smaller) SD card?*    
  **A:** You might be able to make do with 4GB, but any smaller is pushing it, because the emuNAND itself will take up about 1GB of your card and NAND backups are large. You may have to unmount your SD to transfer files to or from your computer more frequently than the guide instructs. Do so at your own risk.

+ <a name="faq_ge128gbsd" />**Q:** *Can I use a 128 GB (or larger) SD card?*    
  **A:** Yes, but some users have reported slowdowns when using such large sizes. Note that you cannot format the card with exFAT; you need to format it with FAT32.

+ <a name="faq_movesd" />**Q:** *How do I move to a new SD card at the end of this?*    
  **A:** Just copy all the files to the new SD card.

+ <a name="faq_nnid" />**Q:** *Can I keep my NNID?*    
  **A:** If you start with an NNID and follow every step, you will end up keeping your NNID at the end.

+ <a name="faq_systransfer" />**Q:** *What about System Transfers?*    
  **A:** Once you have completed the guide, you can system transfer to and from an arm9loaderhax'd 3DS or 2DS exactly like you would a regular stock console (you will lose any non-legitimate games/themes/dlc in the transfer; saves will stay even for games that are lost).

+ <a name="faq_nopc" />**Q:** *Can I do this without a computer (e.g. an Android phone)?*    
  **A:** You may be able to complete up to part 3 of the guide (getting emuNAND running). However, part 4 as of now requires a computer to inject FBI into Health & Safety.

+ <a name="faq_problem" />**Q:** *Help! Something bad happened and now I cannot boot...*    
  **A:** Please look at the [[troubleshooting guide|Troubleshooting]].