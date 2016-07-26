The version of autofirm used in this guide was modified from [Raugo](https://gbatemp.net/members/356694/)'s original autofirm by [Reboot.ms](https://www.reboot.ms/forum/threads/2403/), it is being rehosted [with permission](http://archive.is/KOrWp).

If you are on 11.0.0, you must follow this guide to downgrade your NATIVE_FIRM using a hardmod in order to directly dump and restore your NAND.    

If you are below version 9.0.0 then you should follow [this](https://github.com/Plailect/Guide/wiki/9.2.0-Update) guide instead to update.    

If you are between 9.0.0 and 10.7.0 you can just follow the instructions [here](https://github.com/Plailect/Guide/wiki/Get-Started).    

**An excellent guide to getting a hardmod can be found [here](https://gbatemp.net/threads/414498/).**

This is a currently working implementation of the "FIRM partitions known-plaintext" exploit detailed [here](https://www.3dbrew.org/wiki/3DS_System_Flaws).

This will work on both a New and Old 3DS.

**After following these instructions on version 11.0.0, you must have an alternate entrypoint such as one of the ones detailed in [Get Started](https://github.com/Plailect/Guide/wiki/Get-Started) in order to enter the homebrew launcher and downgrade.**

#### What you need

* Your 11.0.0 NAND extracted using your [hardmod](https://gbatemp.net/threads/414498/)
* <a href="magnet:?xt=urn:btih:233fd2c61bbd6f90f6f4761a7fb822f02f442e5d&dn=autofirm_Reboot_11.0.zip">Autofirm 11.0 - Reboot edition</a> ([mirror](https://mega.nz/#!dl8ASTjB!2jsKbAYTAlspHhxYCt9Wzvia74xEvgtzGQxGLe3TJiM)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDRTlwYUQ1NDJoVlk))
* The 10.4.0 and 11.0.0 decrypted NATIVE_FIRM CIAs for your device:
    + <a href="magnet:?xt=urn:btih:60b86dec3757c0707037c7f2e0e7db0892044606&dn=o3DS+10.4.cia">Old 3DS 10.4.0 - 0004013800000002 v23341</a> ([mirror](https://mega.nz/#!I5EmyCZC!pU-bG9Esg30LINlasTP43Sei6aDNnTIzh1ojwECKOrU)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDUGxYbmkwVThSUHc))    
    + <a href="magnet:?xt=urn:btih:4466d82b06aff18c9f4a438281f6389d565fdb9a&dn=o3DS+11.0.cia">Old 3DS 11.0.0 - 0004013800000002 v24368</a> ([mirror](https://mega.nz/#!AgUGAbKD!0iNXI1ioLM7mBzACfBrPLotYk8g-LzcdTgcuTsQCmHQ)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaG1jbERyQ1BGcHc))    
    + <a href="magnet:?xt=urn:btih:0cd996818e3edb0dd2cad1e5b44f80c1b5a876f4&dn=n3DS+10.4.cia">New 3DS 10.4.0 - 0004013820000002 v23341</a> ([mirror](https://mega.nz/#!1xcEAApQ!anu5UenuD-uEm6z14n680rQThEgViAsytWh5ZuTa_hc)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDRHlOTWJZNGtxVkk))
    + <a href="magnet:?xt=urn:btih:81875690d5bb03e9e7038b4948130be94eeaa681&dn=n3DS+11.0.cia">New 3DS 11.0.0 - 0004013820000002 v24368</a> ([mirror](https://mega.nz/#!dk8BgZaJ!8EM0Wk4NHl6-_O4hhcatIpAx-vfkjMKZs7uQh__OKRw)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDeVhnUU1semtNQjQ))

#### Instructions

1. Extract the `autofirm_Reboot_11.0.zip` file to a folder called `autofirm_Reboot_11.0`
2. Place a copy of your NAND backup (named `nand.bin`) in the `autofirm_Reboot_11.0` folder
4. Place both NATIVE_FIRM CIAs that correspond to your device in the `autofirm_Reboot_11.0` folder
7. Run "autofirm_ENG.bat" and select which device the NAND backup is for
8. Wait while the script runs
8. If everything worked, then your original NAND will have been renamed to `backup_nand.bin` and you will have a modified `nand.bin` containing the 10.4.0 NATIVE_FIRM on version 11.0.0
9. Flash this `nand.bin` to your device with your hardmod

Your version number will *not* have changed in the settings, but the exploit has worked.

**You can now follow the rest of this guide from [here](https://github.com/Plailect/Guide/wiki/Part-1-(Homebrew)). Remember that you will still need an alternate entrypoint such as one of the ones detailed in [Get Started](https://github.com/Plailect/Guide/wiki/Get-Started) in order to enter the homebrew launcher and downgrade.**
