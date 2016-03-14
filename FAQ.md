+ <a name="faq_latestfw" />**Q:** *I am on the latest firmware version, is my device hackable?*    
  **A:** Normally the answer is no, but at the time of writing the latest version (10.6.0) is hackable as long as you have a compatible game.

+ <a name="faq_risky" />**Q:** *How risky is hacking my console?*    
  **Short answer**

  This guide is well tested and everything is as safe as it can possibly be. Issues can arise occasionally, but most are due to user error and can be avoided by following all instructions.

  **Long answer**

  Parts 1 and 3 are completely safe. There is no risk of bricking your console. If you accidentally update SysNAND in part 3, you may render your console unhackable until new exploits are found, but your console will still be operational.

  Part 2 involves downgrading your SysNAND. You may brick your console if the downgrade fails. In most cases if the downgrader crashes you will only get a softbrick i.e. you can still boot and continue the downgrade, but there is still the possibility that you hardbrick. At this stage, you likely do not yet have a SysNAND backup, and as such if you hardbrick, you will probably need to send it to Nintendo for repair.

  Part 4 also involves downgrading your SysNAND by flashing your EmuNAND that has been downgraded to 2.1, followed by flashing your 9.2 SysNAND backup back to SysNAND. At the time of writing we have no way of booting a 2.1 EmuNAND because of the lack of a FIRM patch for that version, so we cannot verify that the downgrade was completely successful and boots. You may thus brick either because something went wrong during the downgrade and you flashed to it, or either of the two flashes were unsuccessful. At this stage, you have a SysNAND backup and so you can fix your system with a hardmod. This part is the probably most risky, both theoretically and from experience, especially on New 3DSes.

  Part 5 involves installing arm9loaderhax which is essentially corrupting your SysNAND FIRM partitions in such a way that it loads our own code at boot time. It also involves flashing your EmuNAND to your SysNAND. If the flash fails, you may brick. If the installation of arm9loaderhax fails, or you used the wrong `otp.bin` to compile arm9loaderhax, you will brick. At this stage, you have a SysNAND backup and so you can fix your system with a hardmod.

+ <a name="faq_piracy" />**Q:** *Can I pirate games with this?*    
  **A:** Unfortunately, yes.

+ <a name="faq_piracy_online" />**Q:** *Can I play online with pirated games without getting banned?*    
  **A:** If you installed the CIA file, you won't get banned. If you are using a flashcart, you might be.

+ <a name="faq_homebrew" />**Q:** *Can I run awesome homebrew and emulators with this?*    
  **A:** Yes! Custom Firmware not only enables the Homebrew Launcher, but it also will give you hacks on all versions, which means you keep it forever, even with updates.

+ <a name="faq_arn2cakes" />**Q:** *How do I switch from the old guide to Updated SysNAND + Cakes?*    
  **A:** Just restore your SysNAND from a pre-arm9loaderhax SysNAND backup and follow all of Part 5.

+ <a name="faq_support" />**Q:** *Where should I go for support?*    
  **A:** For real time support, contact me or any other channel operator at [#3dshacks on Rizon IRC](https://qchat.rizon.net/?channels=3dshacks&uio=d4).

+ <a name="faq_le4gbsd" />**Q:** *Can I do this with a 4GB (or smaller) SD card?*    
  **A:** You might be able to make do with 4GB, but any smaller is pushing it, because the emuNAND itself will take up about 1GB of your card and NAND backups are large. You may have to unmount your SD to transfer files to or from your computer more frequently than the guide instructs. Do so at your own risk.

+ <a name="faq_ge128gbsd" />**Q:** *Can I use a 128 GB (or larger) SD card?*    
  **A:** Yes, but some users have reported slowdowns when using such large sizes. Note that you cannot format the card with exFAT; you need to format it with FAT32.

+ <a name="faq_nopc" />**Q:** *Can I do this without a computer (e.g. an Android phone)?*    
  **A:** You may be able to complete up to part 3 of the guide (getting emuNAND running). However, part 4 as of now requires a computer to inject FBI into Health & Safety.

+ <a name="faq_problem" />**Q:** *Help! Something bad happened and now I cannot boot...*    
  **A:** Please look at the [[troubleshooting guide|Troubleshooting]].
