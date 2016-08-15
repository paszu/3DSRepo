The Homebrew Launcher has many different entrypoints, or methods of launching. The most common is browserhax, which launches the Homebrew Launcher using nothing more than the included browser. This can then be used to install menuhax, which lets you hold a button while the console is booting up to launch the Homebrew Launcher before the rest of the system starts.

**9.0.0 - 9.8.0**: Skip changing the date and time and initializing savedata in the beginning.

**9.9.0 - 10.6.0**: Follow this guide as written.

<!---
This isn't needed yet since 10.7 and 11.0 already use the latest browser version and will pass the check

**10.7.0 - 11.0.0**: Start on "Part 1 - Decrypt9"
  + **Set your primary DNS to `107.211.140.065` so as not to trigger the browser version check.**
  + If on this browser version, you ever receive a message to update your browser, you will need an alternate entry point from below as your browser will have detected it is not running the latest version.
  + Once this message appears for the first time, it is impossible to get rid of it so you must use a [non-browser entrypoint](https://github.com/Plailect/Guide/wiki/Homebrew-Launcher-(No-Browser)).
-->

**11.0.0: You MUST have [downgraded your firmware](https://github.com/Plailect/Guide/wiki/Firmware-Downgrade) already.**

If you are using a game for hax because your browser version is incompatible, you will need to enter Homebrew Launcher using it and install menuhax. After installing menuhax, you no longer need the game to complete the rest of the guide.

#### What you need

+ The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
+ An internet connection setup on your 3DS

#### Instructions

1. Copy the contents of `starter.zip` to the root of your SD card, then put the SD card back into your 3DS
2. Open the theme menu, change your theme to any other theme, then switch back. This will initialize the theme data and is required
3. Launch the Settings application
4. Change the date to `January 1, 2000`
5. Change the time to `00:00`
6. Launch the browser, then open the browser settings as fast as possible
7. Scroll to the bottom and Initialize Savedata (it also may be called Clear All Save Data) as fast as possible
8. Navigate to `http://yls8.mtheall.com/3dsbrowserhax_auto.php`
    + You can also load the page by scanning the following QR code (press L + R on the home menu, then tap the QR icon on the bottom screen)     
![browserhax_auto](https://yls8.mtheall.com/3dsbrowserhax_auto_qrcode.png)
    + If you get a slider, zoom all the way in on it, then tap the very right edge of it; this can take quite a few tries
    + If you get an error, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_browser)
9. Your console should load the homebrew menu
10. Open the menuhax_manager application
11. Press A to install, it may show some errors but that's fine as long as it shows "Success" towards the end
12. Go back to the main menuhax_manager menu, then select "Configure menuhax"
13. Press A to continue, then select "Type1"
14. Hold down on the D-Pad, then tap the touch screen; this is the recommended button to use for launching menuhax in this guide because it does not interfere with any other functions of tools we will be using
15. Go back to the main menuhax_manager menu, then press Start to exit back into the Homebrew Launcher
16. Press the Start button then press A to reboot

You can now hold D-Pad down while the system is booting to launch the Homebrew Launcher

You can now continue from [9.2.0 Downgrade](https://github.com/Plailect/Guide/wiki/Part-2-(2.1.0-ctrtransfer)) *(even if you are already on a version from 9.0.0 to 9.2.0)*.
