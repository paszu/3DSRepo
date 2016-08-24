The first thing this guide will do is get you running Decrypt9, which is a multipurpose toolkit that will allow us to install the version 2.1.0, which contains a vulnerability that is needed for further exploitation of the system.

If you have already hacked your 3DS before and have a RedNAND based CFW setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND. Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

The two columns of the chart refer to the last number of your version (which corresponds to the browser version installed to the system). If the version is -0 then you do not have a browser, while any number above -0 indicates a browser is installed.

**The "from" and "to" fields are inclusive. This means that, for example, the "from 9.0.0 to 9.2.0" row includes 9.0.0, 9.1.0, and 9.2.0.**
 
In the case of "5.0.0-0U" for example, you would follow the "No Browser" column and 5.0.0 to 5.1.0 row because the system is on the a system version in that range and has no browser installed.

##### For all versions you can [Cart Update](Cart-Update) to a higher version in the same column to follow its instructions instead.

Select the specific for the version you are using here:

| From | To | No Browser | Browser |
|:-:|:-:|:-:|:-:|
| 1.0.0 | 1.1.0 | + [(4.X.X or 6.X.X) Cart Update](Cart-Update) then [Decrypt9 (MSET)](Decrypt9-(MSET)) | - |
| 2.1.0 | 2.2.0 | + [(4.X.X or 6.X.X) Cart Update](Cart-Update) then [Decrypt9 (MSET)](Decrypt9-(MSET)) | + *2.1.0-4:* [9.2.0 ctrtransfer](9.2.0-ctrtransfer)<br>**or**<br> + [(4.X.X to 8.X.X) Cart Update](Cart-Update) then [Decrypt9 (Browser)](Decrypt9-(Browser)) |
| 3.0.0 | 3.0.0 | + [(4.X.X or 6.X.X) Cart Update](Cart-Update) then [Decrypt9 (MSET)](Decrypt9-(MSET)) | + [(4.X.X to 8.X.X) Cart Update](Cart-Update) then [Decrypt9 (Browser)](Decrypt9-(Browser)) |
| 4.0.0 | 4.5.0 | + [Decrypt9 (MSET)](Decrypt9-(MSET)) | + [Decrypt9 (Browser)](Decrypt9-(Browser)) |
| 5.0.0 | 5.1.0 | + [(6.X.X) Cart Update](Cart-Update) then [Decrypt9 (MSET)](Decrypt9-(MSET)) | + [Decrypt9 (Browser)](Decrypt9-(Browser)) |
| 6.0.0 | 6.3.0 | + [Decrypt9 (MSET)](Decrypt9-(MSET)) | + [Decrypt9 (Browser)](Decrypt9-(Browser)) |
| 7.0.0 | 7.2.0 | + [(9.0.0 to 10.7.0) Cart Update](Cart-Update) | + [Decrypt9 (Browser)](Decrypt9-(Browser)) |
| 8.0.0 | 8.1.0 | + [(9.0.0 to 10.7.0) Cart Update](Cart-Update) <br>**or**<br>+ *New 3DS (EUR / JPN / USA) only:* [NTR and Cubic Ninja](NTR-and-Cubic-Ninja) | + [Decrypt9 (Browser)](Decrypt9-(Browser)) |
| 9.0.0 | 9.2.0 | + [Homebrew Launcher (No Browser)](Homebrew-Launcher-(No-Browser)) | + [Homebrew Launcher (Browser)](Homebrew-Launcher-(Browser)) <br>**or**<br>+ *Old 3DS only:* [Decrypt9 (Browser)](Decrypt9-(Browser)) |
| 9.3.0 | 10.7.0 | + [Homebrew Launcher (No Browser)](Homebrew-Launcher-(No-Browser)) then [9.2.0 Downgrade](9.2.0-Downgrade) | + [Homebrew Launcher (Browser)](Homebrew-Launcher-(Browser)) then [9.2.0 Downgrade](9.2.0-Downgrade) |
| 11.0.0 | 11.0.0 | + [Firmware Downgrade](Firmware-Downgrade/) then [Homebrew Launcher (No Browser)](Homebrew-Launcher-(No-Browser)) then [9.2.0 Downgrade](9.2.0-Downgrade) | + [Firmware Downgrade](Firmware-Downgrade/) then [Homebrew Launcher (Browser)](Homebrew-Launcher-(Browser)) then [9.2.0 Downgrade](9.2.0-Downgrade) |
