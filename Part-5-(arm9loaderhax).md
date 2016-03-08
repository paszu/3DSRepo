The final step of this guide is to install arm9loaderhax and setup AuReiNAND to run just milliseconds into the boot. This is accomplished by using a handy web compiler by [felipejfc](https://gbatemp.net/threads/416385/) to build arm9loaderhax for our device, then setting it up to work with BootCtr9, a boot manager that lets us load things on boot.

This will install [Delebile's Fork](https://github.com/delebile/arm9loaderhax) of arm9loaderhax.

We will also setup the ability to launch Decrypt9 from arm9loaderhax, giving us the ability to unbrick our SysNAND from situations that would normally brick us by restoring from backup.

#### What you need

* The latest release of [MiniPasta](https://github.com/d0k3/MiniPasta/releases)
* The latest release of [BootCtr9](https://github.com/hartmannaf/BootCtr9/releases)
* The latest release of [AuReiNAND](https://github.com/AuroraWright/AuReiNand/releases)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases)
* [boot_config.ini](https://gist.github.com/Plailect/66566928c286de6ecf61)
* *New 3DS:* AuReiNAND [firmware90 bin](https://mega.nz/#!wwtymAKJ!ebBOlc6TaWSvYpiFlv4FPSJLCKlCuGrlRr4gtjm4SaU) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDSXV3SUxrbjBaVzQ/view?usp=sharing)) zip file
* *New 3DS:* AuReiNAND NTR [firmware bin](https://mega.nz/#!p0tTDJIQ!aikEtlvB8cjq-aJG9jC6GKx4uvlwN6oI9X2m1OY_ylE) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDM016eHZBQV95anc/view?usp=sharing)) zip file
* *Old 3DS:* AuReiNAND [firmware90 bin](https://mega.nz/#!lsFEQKDa!_SgQtu1Jp-fPhkNvGm9Fv0f8-wXHtjckNc3FAzovMCk) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDWTd6aEdiNUZ6MWM/view?usp=sharing)) zip file
* *Old 3DS:* AuReiNAND NTR [firmware bin](https://mega.nz/#!04lmVQxD!7IMsl4ChzKhkEaPXhCvEPmbEq_PpD9i06EzrIjtVSIQ) ([mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDVFhnaVNzMlR4SVk/view?usp=sharing)) zip file

#### Instructions

8. Open [this](https://felipejfc.com/a9lh) link on your computer
9. Drag `otp.bin` **(not `otp0x108.bin`!)** onto the CloudA9H page
10. Wait, it can take a while
11. Copy the produced `arm9loaderhax.3dsx` to the `/3ds/` folder on your SD card
12. Copy `MiniPasta.3dsx` and `MiniPasta.smdh` to the `/3ds/` folder on your SD card
1. If you have a file named exactly `NAND.bin` on the root of your SD card for some reason, delete it or name it something else
12. Reinsert your SD card into your 3DS, then get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch MiniPasta, which will patch your SysNAND and reboot you into the home menu
14. Get into the Homebrew Launcher on SysNAND through the entrypoint of your choice
13. Launch the arm9loaderhax installer
14. If you get stuck on "exploiting arm9," restart and try again
14. Hold the power button to power off if you see a black screen with nothing on it, otherwise it will shutdown on its own
1. Put your SD card in your computer
2. Copy `arm9bootloader.bin` and `arm9loaderhax.bin` from the BootCtr9 zip to the root of your SD card
3. Copy my `boot_config.ini` from where you downloaded it to the root of your SD card
4. Create a folder called `a9lh` on the root of your SD card
7. Copy `Decrypt9WIP.bin` to the `/a9lh/` folder on your SD card
5. Copy `arm9loaderhax.bin` from the AuReiNAND zip to the `/a9lh/` folder on your SD card
6. Rename `/a9lh/arm9loaderhax.bin` to `/a9lh/ARN.bin`
5. Copy the `rei` folder and `ReiNand.dat` file from the AuReiNAND zip to the root of your SD card
4. Delete `firmware.bin` from the `/rei/` folder on your SD card
5. Copy the `firmware.bin` from the NTR frimware zip to the `/rei/` folder on your SD card
6. Copy the `firmware90.bin` from the firmware90 zip to the `/rei/` folder on your SD card
8. Reinsert your SD card into your 3DS and power it on

If everything has gone according to plan, arm9loaderhax will be installed to your device. You can now reboot and your device should automatically launch into EmuNAND.

You will no longer be able to boot without the SD card in, that is normal    
You can now hold A on boot to launch any updater bins Delebile releases in the future    
You can now hold X on boot to launch Decrypt9, a full featured NAND tool    
You can now hold L on boot to boot into SysNAND    
Do not update SysNAND, only EmuNAND    