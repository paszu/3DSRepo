This guide relies on the new feature in Decrypt9, CTRNAND injection. As such Part 1 is now entirely based on using one of many possible entrypoints to launch Decrypt9.

If you already have an EmuNAND CFW setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

The two columns of the chart refer to the last number of your version (which corresponds to the browser version installed to the system). If the version is -0 then you do not have a browser, while any number above -0 indicates a browser is installed.

In the case of "5.0.0-0U" for instance, you would follow the "No Brower" column and 5.0.0 to 5.1.0 row because the system is on the a system version in that range and has no browser installed.

##### For all versions you can [Cart Update](https://github.com/Plailect/Guide/wiki/Cart-Update) to a higher version in the same column to follow its instructions instead.

Select the specific for the version you are using here:

| From | To | No Browser | Browser |
|:-:|:-:|:-:|:-:|
| 1.0.0 | 1.1.0 | + [(4.X.X or 6.X.X) Cart Update](https://github.com/Plailect/Guide/wiki/Cart-Update) then [Decrypt9 (MSET)](https://github.com/Plailect/Guide/wiki/Decrypt9-(MSET)) | - |
| 2.1.0 | 2.2.0 | + [(4.X.X or 6.X.X) Cart Update](https://github.com/Plailect/Guide/wiki/Cart-Update) then [Decrypt9 (MSET)](https://github.com/Plailect/Guide/wiki/Decrypt9-(MSET)) | + *2.1.0-4:* [Browser OTP](https://github.com/Plailect/Guide/wiki/Browser-OTP)<br>**or**<br> + [(4.X.X to 8.X.X) Cart Update](https://github.com/Plailect/Guide/wiki/Cart-Update) then [Decrypt9 (Browser)](https://github.com/Plailect/Guide/wiki/Decrypt9-(Browser)) |
| 3.0.0 | 3.0.0 | + [(4.X.X or 6.X.X) Cart Update](https://github.com/Plailect/Guide/wiki/Cart-Update) then [Decrypt9 (MSET)](https://github.com/Plailect/Guide/wiki/Decrypt9-(MSET)) | + [(4.X.X to 8.X.X) Cart Update](https://github.com/Plailect/Guide/wiki/Cart-Update) then [Decrypt9 (Browser)](https://github.com/Plailect/Guide/wiki/Decrypt9-(Browser)) |
| 4.0.0 | 4.5.0 | + [Decrypt9 (MSET)](https://github.com/Plailect/Guide/wiki/Decrypt9-(MSET)) | + [Decrypt9 (Browser)](https://github.com/Plailect/Guide/wiki/Decrypt9-(Browser)) |
| 5.0.0 | 5.1.0 | + [(6.X.X) Cart Update](https://github.com/Plailect/Guide/wiki/Cart-Update) then [Decrypt9 (MSET)](https://github.com/Plailect/Guide/wiki/Decrypt9-(MSET)) | + [Decrypt9 (Browser)](https://github.com/Plailect/Guide/wiki/Decrypt9-(Browser)) |
| 6.0.0 | 6.3.0 | + [Decrypt9 (MSET)](https://github.com/Plailect/Guide/wiki/Decrypt9-(MSET)) | + [Decrypt9 (Browser)](https://github.com/Plailect/Guide/wiki/Decrypt9-(Browser)) |
| 7.0.0 | 7.2.0 | + [(9.0.0 to 10.7.0) Cart Update](https://github.com/Plailect/Guide/wiki/Cart-Update) | + [Decrypt9 (Browser)](https://github.com/Plailect/Guide/wiki/Decrypt9-(Browser)) |
| 8.0.0 | 8.1.0 | + *EUR / JPN / USA only:* [NTR and Cubic Ninja](https://github.com/Plailect/Guide/wiki/NTR-and-Cubic-Ninja) | + [Decrypt9 (Browser)](https://github.com/Plailect/Guide/wiki/Decrypt9-(Browser)) |
| 9.0.0 | 9.2.0 | + [Homebrew Launcher (No Browser)](https://github.com/Plailect/Guide/wiki/Homebrew-Launcher-(No-Browser)) | + [Homebrew Launcher (Browser)](https://github.com/Plailect/Guide/wiki/Homebrew-Launcher-(Browser)) then [9.2.0 Downgrade](https://github.com/Plailect/Guide/wiki/9.2.0-Downgrade)<br>**or**<br>+ *Old 3DS only:* [Decrypt9 (Browser)](https://github.com/Plailect/Guide/wiki/Decrypt9-(Browser)) |
| 9.3.0 | 10.7.0 | + [Homebrew Launcher (No Browser)](https://github.com/Plailect/Guide/wiki/Homebrew-Launcher-(No-Browser)) then [9.2.0 Downgrade](https://github.com/Plailect/Guide/wiki/9.2.0-Downgrade) | + [Homebrew Launcher (Browser)](https://github.com/Plailect/Guide/wiki/Homebrew-Launcher-(Browser)) then [9.2.0 Downgrade](https://github.com/Plailect/Guide/wiki/9.2.0-Downgrade) |
| 11.0.0 | 11.0.0 | + [Firmware Downgrade](https://github.com/Plailect/Guide/wiki/Firmware-Downgrade/) then [Homebrew Launcher (No Browser)](https://github.com/Plailect/Guide/wiki/Homebrew-Launcher-(No-Browser)) then [9.2.0 Downgrade](https://github.com/Plailect/Guide/wiki/9.2.0-Downgrade) | + [Firmware Downgrade](https://github.com/Plailect/Guide/wiki/Firmware-Downgrade/) then [Homebrew Launcher (Browser)](https://github.com/Plailect/Guide/wiki/Homebrew-Launcher-(Browser)) then [9.2.0 Downgrade](https://github.com/Plailect/Guide/wiki/9.2.0-Downgrade) |
