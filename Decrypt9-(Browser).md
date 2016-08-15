This guide relies on the new feature in Decrypt9, CTRNAND injection. As such Part 1 is now entirely based on using one of many possible entrypoints to launch Decrypt9.

If you already have a RedNAND setup, this guide deals exclusively with SysNAND and you should follow all instructions from within or applying to SysNAND.

Note that the terms EmuNAND and RedNAND refer to slightly different implementations of [the same concept](http://3dbrew.org/wiki/NAND_Redirection).

#### What you need

* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)
* The 9.2.0 ctrtransfer image for your device and region:
  +    <a href="https://plailect.github.io/Guide/9.2.0-20E_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - EUR - ctrtransfer</a> ([mirror](https://mega.nz/#!EwFk3SQC!PtYIuwMFtQmfXL4JpfW7Zx4_nz4rP1DamTHQhTOZ9vg)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDNXQ2WFBZTDU1TEE))  
  +    <a href="https://plailect.github.io/Guide/9.2.0-20J_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - JPN - ctrtransfer</a> ([mirror](https://mega.nz/#!lkcWmZAK!ZbhsFHh2o1IWofgLX4KdzlwtEXK19cZGpeNQ1YUo2D0)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDWURyZ1B3d19YSlU))    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20U_ctrtransfer_n3DS.torrent" target="_blank">New 3DS 9.2.0 - USA - ctrtransfer</a> ([mirror](https://mega.nz/#!98lh2KKK!j6sqDT6ldPKb5J1C6Cu3OtSlPakGy6Jc_YNGdCtaJys)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDaWV1TFEta1RtaFU))    
~
  +    <a href="https://plailect.github.io/Guide/9.2.0-20E_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - EUR - ctrtransfer</a> ([mirror](https://mega.nz/#!4tkg0YaR!zBPFwZnqbsQb6oYTToZhyq_XOSAYu4VPtfIdX-KyLZY)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDTWh6M1lVMTRlQVU))    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20J_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - JPN - ctrtransfer</a> ([mirror](https://mega.nz/#!Y49n2KBD!Y15682PF3gI_IQybhYDsTGtkFqj6HVhHzM_YovaNG20)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDa20zSUtleUNNcXM))    
  +    <a href="https://plailect.github.io/Guide/9.2.0-20U_ctrtransfer_o3ds.torrent" target="_blank">Old 3DS or 2DS 9.2.0 - USA - ctrtransfer</a> ([mirror](https://mega.nz/#!55kE0DyS!eazLeGCoktm-N6t_uE3y_okjMKcoL740HEIexOHKF-w)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDVlJEU2tnNW5SOHc))
  +    If your device is not from one of the three above regions, you should pick one of them, then additionally copy the corresponding [`SecureInfo_A`](https://plailect.github.io/Guide/SecureInfo_A.torrent) ([mirror](https://mega.nz/#!4wdwlZpY!yPFb8D7lAFR-dz7yVYg0HeFfak1kge7KB0BvoWe0CHw)) ([mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDMlNVa3VJT2N1UFk)) to `/files9/`

#### Instructions

1. Create a folder named `files9` on the root of your SD card if it does not already exist
2. Copy `Launcher.dat` and `Decrypt9WIP.dat` from the Decrypt9WIP zip to the root of your SD card
3. Copy the 9.2.0 ctrtransfer image `.bin` and `.bin.sha` from the ctrtransfer zip to the `/files9/` folder on your SD card
4. Reinsert your SD card into your 3DS
5. Open the browser and go to one of the following URLs on your 3DS
    + `https://dukesrg.github.io/?Decrypt9WIP.dat`
    + `http://go.gateway-3ds.com/`
    + `http://www.reboot.ms/3ds/load.html?Launcher.dat`
    + `http://dukesrg.dynu.net/3ds/rop?GW17567.dat&Launcher.dat`
    + If you get an error, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_browser)
6. If the exploit was successful, you will have booted into Decrypt9

You can now continue from [Part 2 - 2.1.0 ctrtransfer](https://github.com/Plailect/Guide/wiki/Part-2-(2.1.0-ctrtransfer)).
