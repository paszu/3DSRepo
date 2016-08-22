**You cannot use another console's OTP or you will brick GUARANTEED.**

The final Step of this guide is to install arm9loaderhax and setup Luma3DS to run just milliseconds into the boot. This is accomplished by using SafeA9LHInstaller by [AuroraWright](https://github.com/AuroraWright/).

This will install [AuroraWright's Fork](https://github.com/AuroraWright/arm9loaderhax) of arm9loaderhax.

This guide uses "Updated SysNAND" mode, in which we copy our RedNAND to SysNAND (to keep games and such) and install arm9loaderhax to have permanent SysNAND hax with no RedNAND required at all.

We will also setup the ability to launch payloads from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.

#### Overview of steps

In this section, we will go through the process that all the other steps have led up to: actually installing arm9loaderhax.

This is nearly the best possible kind of device exploit because it is permanently installable into the NAND firm partitions, and runs before most of the OS loads, allowing it to not only work on *all* versions once installed, but also protect itself and recover from most situations that would brick a non-a9lhax 3DS such as a nonfunctional home menu or bad title install.

The file `arm9loaderhax.bin` is what is launched by arm9loaderhax itself after it finishes loading off of NAND, and can be any valid arm9 payload. This file can be replaced at any time, although Luma3DS allows for the launch of other arm9 payloads by holding buttons on boot.

In this case, we use Luma3DS by [AuroraWright](https://github.com/AuroraWright/) to boot a patched SysNAND directly, allowing us to completely bypass the need for any kind of RedNAND, vastly simplifying the usage of a hacked 3DS in addition to saving SD card space.

Once arm9loaderhax is installed and Luma3DS is setup with the correct options, we then restore our previous backup.

During this process, we also setup programs such as the following:
+  **FBI** *(installs CIA formatted games and applications)*
+  **Luma3DS Updater** *(updates our CFW installation easily)*
+  **Decrypt9** *(decryption tool which can also convert physical cartridge games to digital CIA files)*
+  **Hourglass9** *(allows us to restore NANDs and such before boot to recover from bricks and do many other miscellaneous functions)*

#### What you need

* <a href="https://plailect.github.io/Guide/data_input_v2.torrent" target="_blank">data_input_v2.zip</a> ([mirror](https://mega.nz/#!RwUDVL5T!65gKJHAAVFk3R0jCA7zRFC5q5QTsL5CLoRUoqhET-WI)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaU53U0MtSHlkTDA))
* <a href="https://plailect.github.io/Guide/aeskeydb.torrent" target="_blank">aeskeydb.bin</a> ([mirror](https://mega.nz/#!Y5UEyIJb!_FLHUUqjtfLaez8FNEM3tG7NHWrkkwmyj93ZNUeOUxI)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDTm5VZW1ZcHZ1NzQ))
* The latest release of [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases) *(noscreeninit)*    
* The latest release of [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases)
* The latest version of [Universal Inject Generator](https://github.com/d0k3/Universal-Inject-Generator/archive/master.zip)
* The latest release of [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases)
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases)
* The latest release of [Hourglass9](https://github.com/d0k3/Hourglass9/releases)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* The latest release of [Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases)
* The latest release of [DspDump](https://github.com/Cruel/DspDump/releases)
* The latest release of [FBI](https://github.com/Steveice10/FBI/releases/)
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)_

#### Instructions

##### Section I - Prep work

1. **Copy the `/files9/` folder on your SD card to a safe location on your computer and back them up to multiple locations (such as online file storage); the files inside could save you from total data loss if your break your system**
2. Delete the contents of the `/files9/` folder on your SD card
1. Create a folder named `cias` on the root of your SD card if it does not already exist
3. Delete the `3ds` folder from the root of your SD card if it exists
1. Copy the contents of `starter.zip` to the root of your SD card    
2. Copy `NANDmin.bin` and `NANDmin.bin.sha` to the `/files9/` folder on your SD card
3. Copy the `a9lh` folder from `data_input_v2.zip` to the root of your SD Card
3. Copy `payload_stage1.bin` and `payload_stage2.bin` from the arm9loaderhax zip to `a9lh` folder on your SD card
2. Copy `arm11.bin` and `arm9.bin` from the SafeA9LHInstaller zip to the root of your SD card
3. Copy `hblauncher_loader.cia` from the hblauncher_loader zip to the `/cias/` folder on your SD card
4. Copy `lumaupdater.cia` from the Luma3DS Updater zip to the `/cias/` folder on your SD card
2. Copy `FBI.cia` from the FBI zip to the `/cias/` folder on your SD card
1. Copy `arm9loaderhax.bin` from the Luma3DS zip to the root of your SD card
2. Create a folder named `luma` on the root of your SD card
3. Create a folder named `payloads` in the `luma` folder on your SD card
7. Copy `Hourglass9.bin` from the Hourglass9 zip to the `/luma/payloads/` folder on your SD card and rename `Hourglass9.bin` to `start_Hourglass9.bin`
7. Copy `Decrypt9WIP.bin` to the `/luma/payloads/` folder on your SD card and rename `Decrypt9WIP.bin` to `x_Decrypt9WIP.bin`
1. Copy `aeskeydb.bin` to the `/files9/` folder on your SD card
2. Copy `DspDump.3dsx` to the `/3ds/` folder on your SD card

##### Section II - Installing arm9loaderhax

12. Reinsert your SD card into your 2.1.0 3DS
14. Go to `http://dukesrg.github.io/2xrsa.html?arm11.bin` on your 3DS
    + If you get an error, [follow this troubleshooting guide](Troubleshooting#ts_browser)
    + If you get a glitched screen, [follow this troubleshooting guide](Troubleshooting#ts_safe_a9lh_screen)
14. Press (Select) to Full Install
15. The installer will now install arm9loaderhax on your device (this is very fast)
18. Following this, booting to a black screen is normal (Luma3DS cannot boot a 2.1.0 NAND).
18. Copy your console specific `OTP.bin` from the `/a9lh/` folder on your SD card to a safe location on your computer and back it up to multiple locations (such as online file storage)

##### Section III - Configuring Luma3DS

1. Hold select on boot to enter the Luma3DS menu.     
  + If you get a black screen, [follow this troubleshooting guide](Troubleshooting#ts_sys_a9lh).    
  + If you boot to SafeA9LHInstaller, [follow this troubleshooting guide](Troubleshooting#ts_safe_a9lh).
1. Use the (A) button and the D-Pad to turn on the following:    
 + "Autoboot SysNAND"
 + "Show current NAND in System Settings"
 + "Show GBA boot screen in patched AGB_FIRM"
2. If you are using a New 3DS, you should *also* enable the following:
 + Toggle "New 3DS CPU" to "Clock+L2(x)" for improved game performance
2. Press Start to save and reboot
18. Following this, booting to a black screen is normal (Luma3DS cannot boot a 2.1.0 NAND).

##### Section IV - Restoring the System

**If, before following this guide, you already had an EmuNAND or RedNAND setup and would like to move the contents of your previous EmuNAND or RedNAND to your new SysNAND CFW, now is the time to [follow Move RedNAND](Move-RedNAND).**

1. Open Hourglass9 from arm9loaderhax by holding Start on boot
1. Go to "SysNAND Backup/Restore..."
2. Select "SysNAND Restore"
3. Confirm and restore from `NANDmin.bin`
4. Your device should now be able to boot properly once more.
  + If you get a black screen, [follow this troubleshooting guide](https://github.com/AuroraWright/Luma3DS/wiki/FAQ-and-Troubleshooting#i-get-a-black-screen-on-boot-with-an-old-3ds-which-has-been-downgraded-from-the-gateway-menu-in-the-past)
  + If you do not have any usable NAND backups, [follow 9.2.0 ctrtransfer](9.2.0-ctrtransfer) starting on Step 4

##### Section V - Injecting FBI

**If you restored an EmuNAND or RedNAND that already contains FBI as part of the last section, you can skip this section.**

1. Open Hourglass9 from arm9loaderhax by holding (Start) on boot
11. Go to "SysNAND Backup/Restore", then select the "Health&Safety Dump" option to dump Health & Safety to `hs.app` **(you can use Up and Down / Left and Right to change the name)**
12. Press (Select) to eject your SD card, then put it in your computer
13. Extract Universal Inject Generator, then copy both `hs.app` from your SD card and `FBI.cia` from the FBI zip to the `input` folder
14. Double click `go.bat` *(or execute `go.sh` with Terminal on Linux, or double click `Mac_inject_launcher.app` on Mac)*
15. Copy `FBI_inject_with_banner.app` to the `/files9/` folder on your SD card and reinsert your SD card into your 3DS
16. Press (B), then go to "SysNAND Backup/Restore", then select the "Health&Safety Inject" option
17. Press down once to select `FBI_inject_with_banner.app`, then press (A) and confirm to inject
18. Go to the main menu, then press (Start) to reboot

##### Section VI - Finalizing setup

6. Update your CFW SysNAND to the latest version using system settings (if it is not already)
8. Open Health and Safety (which is now FBI)
9. Select "SD"
9. Select "cias"
9. Navigate to `FBI.cia` and press (A) to install
9. Navigate to `hblauncher_loader.cia` and press (A) to install
9. Navigate to `lumaupdater.cia` and press (A) to install
10. Exit with the home button
10. Launch the Homebrew Launcher from the home menu
12. Select "DSP Dump"
13. Press (Start) when prompted to exit
14. Reboot while holding Start to launch Hourglass9
15. Go to "SysNAND Backup/Restore", then select "Health&Safety Inject"
16. Select `hs.app` (the original one that doesn't contain FBI), then press (A) and confirm to inject
17. Press (Start) on the main menu to reboot!

You can now use Luma3DS Updater to update your Luma3DS to the latest version just by opening it and pressing (A). *(This is not the same thing as a System Update; it just downloads and extracts the newest Luma3DS files)*

You will no longer be able to boot without the SD card in, that is normal.    
You will now boot a Custom Firmware based SysNAND by default.    
You can now hold (Select) on boot to launch the Luma3DS configuration menu.    
You can now hold (Start) on boot to launch Hourglass9, an arm9loaderhax safe NAND tool.    
You can now hold (X) on boot to launch Decrypt9, a full featured NAND + decryption tool which can also be used to convert a physical game cart to an installable file *(Gamecard Dumper Options -> Dump Cart to CIA)*.    

You can update your arm9loaderhax installation in the future by following the instructions on the [Updating arm9loaderhax](Updating-arm9loaderhax/) page.

To use [NTR CFW](https://github.com/44670/BootNTR/), get `ntr.bin` from the appropriate zip on [this](https://github.com/44670/BootNTR/releases) page and copy it to the root of your SD card, then install `BootNTR.cia` from [this](https://github.com/astronautlevel2/BootNTR/releases/) page.

Keep your `NANDmin.bin` file, it can be restored by Hourglass9 to save you from a brick in the future.

You can remove any extra files from the root of the SD card that are not in the image.    

![SD Card](http://i.imgur.com/TbXejSM.png)
