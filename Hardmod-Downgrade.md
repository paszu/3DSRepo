The version of autofirm used in this guide was modified from [Raugo](https://gbatemp.net/members/356694/)'s original autofirm by [Reboot.ms](https://www.reboot.ms/forum/threads/2403/), it is being rehosted [with permission](http://archive.is/KOrWp).

If you are on 11.0.0, you must follow this guide to downgrade your NATIVE_FIRM using a hardmod in order to directly dump and restore your NAND.    

**An excellent guide to getting a hardmod can be found [here](https://gbatemp.net/threads/414498/).**

This is a currently working implementation of the "FIRM partitions known-plaintext" exploit detailed [here](https://www.3dbrew.org/wiki/3DS_System_Flaws).

This will work on both a New and Old 3DS.

#### What you need

* Your 11.0.0 NAND extracted using your [hardmod](https://gbatemp.net/threads/414498/)
* <a href="https://plailect.github.io/Guide/autofirm_Reboot_11.0.torrent" target="_blank">Autofirm 11.0 - Reboot edition</a> ([mirror](https://mega.nz/#!dl8ASTjB!2jsKbAYTAlspHhxYCt9Wzvia74xEvgtzGQxGLe3TJiM)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDRTlwYUQ1NDJoVlk))
* The 10.4.0 and 11.0.0 decrypted NATIVE_FIRM CIAs for your device:
    + <a href="https://plailect.github.io/Guide/o3DS%2010.4.torrent" target="_blank">Old 3DS 10.4.0 - 0004013800000002 v23341</a> ([mirror](https://mega.nz/#!I5EmyCZC!pU-bG9Esg30LINlasTP43Sei6aDNnTIzh1ojwECKOrU)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDUGxYbmkwVThSUHc))    
    + <a href="https://plailect.github.io/Guide/o3DS%2011.0.torrent" target="_blank">Old 3DS 11.0.0 - 0004013800000002 v24368</a> ([mirror](https://mega.nz/#!AgUGAbKD!0iNXI1ioLM7mBzACfBrPLotYk8g-LzcdTgcuTsQCmHQ)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaG1jbERyQ1BGcHc))    
    + <a href="https://plailect.github.io/Guide/n3DS%2010.4.torrent" target="_blank">New 3DS 10.4.0 - 0004013820000002 v23341</a> ([mirror](https://mega.nz/#!1xcEAApQ!anu5UenuD-uEm6z14n680rQThEgViAsytWh5ZuTa_hc)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDRHlOTWJZNGtxVkk))
    + <a href="https://plailect.github.io/Guide/n3DS%2011.0.torrent" target="_blank">New 3DS 11.0.0 - 0004013820000002 v24368</a> ([mirror](https://mega.nz/#!dk8BgZaJ!8EM0Wk4NHl6-_O4hhcatIpAx-vfkjMKZs7uQh__OKRw)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDeVhnUU1semtNQjQ))

#### Instructions

1. Extract the `autofirm_Reboot_11.0.zip` file to a folder called `autofirm_Reboot_11.0`
2. Place a copy of your NAND backup (named `nand.bin`) in the `autofirm_Reboot_11.0` folder
3. Place both NATIVE_FIRM CIAs that correspond to your device in the `autofirm_Reboot_11.0` folder
4. Run "autofirm_ENG.bat" and select which device the NAND backup is for
5. Wait while the script runs
6. If everything worked, then your original NAND will have been renamed to `backup_nand.bin` and you will have a modified `nand.bin` containing the 10.4.0 NATIVE_FIRM on version 11.0.0
7. Flash this `nand.bin` to your device with your hardmod

Your version number will *not* have changed in the settings, but the exploit has worked.

You can now continue from either [Homebrew Launcher (No Browser)](Homebrew-Launcher-(No-Browser)) or [Homebrew Launcher (Browser)](Homebrew-Launcher-(Browser)), depending on what the [Part 1 - Decrypt9](Part-1-(Decrypt9)) chart specified for your version.
