[**All** variations of sysUpdater, *not* just PlaiSysUpdater, has a *very* small chance of causing a "soft brick" once the downgrade is complete and the device reboots. This will cause the system to boot directly to the Nintendo error screen instructing users to power off the device.](https://github.com/Plailect/PlaiSysUpdater/issues/8#issuecomment-218588857)

[The reason for this is unknown, but can be prevented by performing a system format *before* downgrading. It seems to happen very often on systems with ambassador status or who have DSiWare installed.](https://github.com/Plailect/PlaiSysUpdater/issues/8#issuecomment-218588857)

[Once this error happens, it can *only* be fixed by using recovery mode (A + R + L + Up on the D-Pad) to update to the latest system version.](https://github.com/Plailect/PlaiSysUpdater/issues/8#issuecomment-218588857)

[As of the time this is written, the latest version (11.0.0) has completely blocked all software downgrading, and if someone encounters this error they will be locked out of any further downgrading unless they downgrade their firmware.](https://github.com/Plailect/PlaiSysUpdater/issues/8#issuecomment-218588857)

---

*If you encounter this error and cannot use recovery mode, you can edit the connection settings as long as the 3DS completely fails to connect to any access point (such as if the point being out of range).*

This version of PlaiSysUpdater (which is compatible with >9.2.0 systems) uses an unstable exploit, and because of this it may take many tries just to load the button prompts.

If PlaiSysUpdater crashes at any point during the downgrade (which can happen occasionally), you can power off the system by holding the power button. You will be left with what's called a "partial downgrade" or "partial", which is recoverable.

Although a partially downgraded system may show 9.2.0 as the system version, you are not done. You must restart from the beginning and downgrade a second time to install any files that were not installed. Browserhax will work for partial downgrades as long as you are using the recommended version of PlaiSysUpdater.

**You MUST downgrade with the correct pack for your console/region or you will BRICK.**

**If you are on version 11.0.0, you MUST have [downgraded your firmware](https://github.com/Plailect/Guide/wiki/Firmware-Downgrade) to successfully complete this part.**

#### Overview of steps

The 3DS has two different embedded processors, the arm9 and arm11. The arm11 processor is what runs all game and user intractable applications, while the arm9 handles the main security features such as managing cryptographic keys and verifying signatures.

In getting access to the Homebrew Launcher, we have successfully breached the outer layer of [the 3DS's security system](https://smealum.github.io/3ds/32c3/#/19), the arm11 userland. This means that we can now operate with the same privileges as any other regular game or application. Let's take it further.

The last arm9 kernel exploit that works without extra install steps or hardware was patched with the release of 9.3.0, meaning that in order for us to gain the highest levels of access, which enable arm9loaderhax's installation, we must downgrade to a version below 9.3.0.

In this case, we take advantage of an arm11 kernel exploit, nicknamed ["svchax"](https://github.com/aliaspider/svchax), to gain the ability to install and uninstall system titles, which are components of the OS. This allows us to uninstall current system title versions and replace them with older ones to reopen previously fixed exploits, such as the <9.2.0 arm9 kernel exploit.

For a more detailed explanation of the 3DS's security, see [this](http://yifan.lu/2016/04/06/the-3ds-cryptosystem/) blog post by [yifanlu](https://github.com/yifanlu/).

#### What you need

* The Homebrew Launcher and an installed entrypoint (such as menuhax)
* The latest release of [PlaiSysUpdater](https://github.com/Plailect/PlaiSysUpdater/releases/)
* The latest release of [EmuNAND9](https://github.com/d0k3/EmuNAND9/releases)
* The 9.2.0 firmware pack zip file for your device and region:
 +    <a href="magnet:?xt=urn:btih:4e22cf8bc71c99a70bb846c7cf416d4caafbe58e&dn=9.2.0-20E%28Full%29_n3DS.zip" target="_blank">New 3DS 9.2.0 - EUR</a> ([mirror](https://mega.nz/#!F4U32b4B!tPhl3G0HEmzg5Pd5zQ29ndf1icQqU_LBoogygSL13EY)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDOWpMTWdybzF3TUU))    
 +    <a href="magnet:?xt=urn:btih:c8630ed31b53637b9023bd4dc1ce38362bb8ecd9&dn=9.2.0-20J%28Full%29_n3DS.zip" target="_blank">New 3DS 9.2.0 - JPN</a> ([mirror](https://mega.nz/#!VxcF3TIK!Bm5LgFxo5V4Nepe9ZlWnx7bichE1V7p7pR_HqwimU5M)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDU2plUWwxa2gtV0E/view?usp=sharing))    
 +    <a href="magnet:?xt=urn:btih:1e670b71b7f26f2765bbe55d0f6cb8c0459d2e8c&dn=9.2.0-20U%28Full%29_n3DS.zip" target="_blank">New 3DS 9.2.0 - USA</a> ([mirror](https://mega.nz/#!gslWiIoK!SF7uFk9rzWTK6oitCDoeAdvphcCzhKWsnTAMXw7zwOU)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDbEV2aTRjb1oxekE/view?usp=sharing))        
~    
 +    <a href="magnet:?xt=urn:btih:844006eb64474c115bd5b847f6c59d333be3397a&dn=9.2.0-20E%28Full%29.zip" target="_blank">Old 3DS or 2DS 9.2.0 - EUR</a> ([mirror](https://mega.nz/#!xh0wCRYQ!AaxVlej5jG4YPthojiI403alEtYfrkqq4FfdTy10EcU)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDT0oxaGxPSmJ5Rlk/view?usp=sharing))    
 +    <a href="magnet:?xt=urn:btih:bb27a53a524276b6527d3b139395b2afc7affe1a&dn=9.2.0-20J%28Full%29.zip" target="_blank">Old 3DS or 2DS 9.2.0 - JPN</a> ([mirror](https://mega.nz/#!dxMUgTDL!sWvpVP4yWL_H66sOMG9VCJh3xMGG0_GgaX22gTpRE24)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDNnNrXzh4UlFPNzQ/view?usp=sharing))    
 +    <a href="magnet:?xt=urn:btih:940d6479a3972a99daeb85c499f0d6e4e24a2c8b&dn=9.2.0-20U%28Full%29.zip" target="_blank">Old 3DS or 2DS 9.2.0 - USA</a> ([mirror](https://mega.nz/#!VsMTFDIR!-TfpWoCcCNEky-EfWHFDb1Cf6Ob0VJL0oF01J2YD2Cs)) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDRVY4YWVsMjVqTkU/view?usp=sharing))

#### Instructions

**If you are already on 9.2.0-20, do up to step 3 then skip to step 22.**

1. **Right now is a good time to use a [save manager](https://github.com/J-D-K/JKSM/releases) to backup any saves you care about (just in case something goes wrong unexpectedly)**
1. Copy and merge the `3ds` folder from the PlaiSysUpdater zip to root of your SD card
2. Copy and merge the `3ds` folder from the EmuNAND9 zip to root of your SD card
2. Delete any existing `updates` folder from your SD card if there is one
3. Copy the `updates` folder from the 9.2.0 firmware zip to the root of your SD card
4. Eject your SD card and put it back in your 3DS
5. Boot into the Homebrew Launcher (if you followed the previous part, you can do this by holding D-Pad down on boot)    
**If you are using supermysterychunkhax or smashbroshax as your entrypoint, you should open any homebrew application (such as menuhax_manager) then close it back to the Homebrew Launcher (which will fix memory contents). If you do not, svchax will not init properly.**
6. Open PlaiSysUpdater
7. If you do not see the button prompts, power off your 3DS by holding the power button and try again (this can take many tries)
8. If you see button prompts, proceed
9. Press Y to downgrade to 9.2.0
7. If you are stuck on "HAX INIT", power off your 3DS by holding the power button and try again (this can take many tries)
10. Wait; do not touch anything even if it appears to freeze
10. If, after around 30 seconds, it is still frozen, it is safe to power off and try again
11. If you get an error before installation, power off your 3DS by holding the power button and try again (this can take many tries)
12. If you get an error in the middle of installation, follow the instructions in the beginning for partial downgrades
13. If you freeze on the "Rebooting in 10 seconds" line for longer than 10 seconds, it is safe to power off your 3DS by holding the power button
14. If you get a black screen after downgrading, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_sys_down)
14. When you have booted, change your theme to anything else, then change it back to remove the old menuhax version
14. Reinstall menuhax using browserhax and the HomeBrew Launcher (you do not need to reconfigure, just press install in menuhax_manager)
15. Check the system settings, you should be on 9.2.0
16. Launch the Homebrew Launcher using the entrypoint of your choice (such as menuhax)
17. Open EmuNAND9 **(This can sometimes take a few tries)**
18. Go to EmuNAND Manager Options, then backup SysNAND to `sysNAND.bin`
20. Press Select on the main menu to eject your SD card
21. Put your SD card in your computer, then copy `sysNAND.bin` and `sysNAND.bin.sha` to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong in the future **(Your backup should match one of the sizes on [this](https://github.com/Plailect/Guide/wiki/NAND-Size) page; if it does not, you should delete it and make a new one!)**
22. You can delete `sysNAND.bin` and `sysNAND.bin.sha` from your SD card after copying it
23. Reinsert your SD card into your 3DS, then press Start to reboot
