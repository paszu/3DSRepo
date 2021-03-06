The Homebrew Launcher has many different entrypoints, or methods of launching. The most common is browserhax, which launches the Homebrew Launcher using nothing more than the included browser. This can then be used to install menuhax, which lets you hold a button while the console is booting up to launch the Homebrew Launcher before the rest of the system starts.

**9.0.0 - 9.8.0**: Skip changing the date and time and initializing savedata in the beginning.

**9.9.0 - 10.6.0**: Follow this guide as written.

**10.7.0 - 11.0.0**: Skip changing the date and time and initializing savedata in the beginning.

<!---
This isn't needed yet since 10.7 and 11.0 already use the latest browser version and will pass the check

**10.7.0 - 11.0.0**: Start on "Part 1 - Decrypt9"
  + **Set your primary DNS to `107.211.140.065` before launching the browser so as not to trigger the browser version check.**
  + If on this browser version, you ever receive a message to update your browser, it is because your browser has detected it is not running the latest version.
  + Once this message appears for the first time, it is impossible to get rid of it so you must use a [non-browser entrypoint](Homebrew-Launcher-(No-Browser)).
-->

**11.0.0: You MUST have [downgraded your firmware](Firmware-Downgrade) already.**

If you are using a game for hax because your browser version is incompatible, you will need to enter Homebrew Launcher using it and install menuhax. After installing menuhax, you no longer need the game to complete the rest of the guide.

#### What you need

+ The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
+ An internet connection setup on your 3DS

#### Instructions

1. Copy the contents of the `starter` folder in `starter.zip` to the root of your SD card, then put the SD card back into your 3DS
2. Open the theme menu, change your theme to any other theme, then switch back. This will initialize the theme data and is required
3. Launch the Settings application
4. Change the date to `January 1, 2000`
5. Change the time to `00:00`
6. Launch the browser, then open the browser settings as fast as possible
7. Scroll to the bottom and Initialize Savedata (it also may be called Clear All Save Data) as fast as possible
8. Navigate to `http://yls8.mtheall.com/3dsbrowserhax_auto.php`
    + You can also load the page by scanning the following QR code (press (L + R) on the home menu, then tap the QR icon on the bottom screen)     
![browserhax_auto](https://yls8.mtheall.com/3dsbrowserhax_auto_qrcode.png)
    + If you get a slider, zoom all the way in on it, then tap the very right edge of it; this can take quite a few tries
    + If you get an error, [follow this troubleshooting guide](Troubleshooting#ts_browser)
9. Your console should load the homebrew menu
10. Open the menuhax_manager application
11. Press (A) to install, it may show some errors but that's fine as long as it shows "Install finished successfully" towards the end
    + If you are prompted to "override the detected system version," press (B) to decline
12. Go back to the main menuhax_manager menu, then select "Configure menuhax"
13. Press (A) to continue, then select "Type1"
14. Hold (Down) on the D-Pad, then tap the touch screen; this is the recommended button to use for launching menuhax in this guide because it does not interfere with any other functions of tools we will be using
15. Go back to the main menuhax_manager menu, then press (Start) to exit back into the Homebrew Launcher
16. Press the (Start) button then press (A) to reboot

You can now hold D-Pad (Down) while the system is booting to launch the Homebrew Launcher

### All versions above 9.2.0 should continue to [9.2.0 Downgrade](9.2.0-Downgrade).

___

### If you are between 9.0.0 and 9.2.0, do the following:

#### What you need

* The Homebrew Launcher and an installed entrypoint (such as menuhax)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest)

#### Instructions

1. Create a folder named `files9` on the root of your SD card if it does not already exist
3. Copy the `Decrypt9WIP` folder from the Decrypt9WIP zip to `/3ds/` on your SD card
6. Reinsert your SD card into your 3DS
1. Check the system settings, you should be on 9.2.0
2. Launch the Homebrew Launcher using the entrypoint of your choice (such as menuhax)
3. Open Decrypt9WIP **(This can sometimes take a few tries)**
    + If you cannot launch Decrypt9WIP after many tries, you most likely have a partial downgrade and should redo Section II

You can now continue to [Part 2 - 2.1.0 ctrtransfer](Part-2-(2.1.0-ctrtransfer)).