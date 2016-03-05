The Homebrew Launcher has many different entrypoints, or methods of launching. The most common is browserhax, which launches the Homebrew Launcher using nothing more than the included browser. This can then be used to install menuhax, which lets you hold a button while the console is booting up to launch the Homebrew Launcher before the rest of the system starts.

If you are between versions 9.0.0 and 9.8.0, you should follow this guide, but you can omit changing the date in the beginning.

If you are between versions 9.9.0 and 10.3.0, you should follow this guide as written.

If you are between versions 10.4.0 and 10.5.0 and have downgraded NATIVE_FIRM with a hardmod, you should follow this guide as written.

If you are on version 10.6.0 and have downgraded NATIVE_FIRM with a hardmod, you can find instructions for using ninjhax (requires Cubic Ninja) [here](http://smealum.github.io/ninjhax2/), OOTHax (requires Ocarina of Time 3D and either a powersaves or another 3DS which has the homebrew launcher) [here](https://github.com/yellows8/oot3dhax).

If you are below version 9.0.0 or you have an old browser version (you must have a -20 or highter at the end of your version number to follow this guide; the -XX indicates browser version; i.e: 9.2.0-15U is incompatible), you can find instructions for updating or downgrading to 9.2.0-20U [here](https://github.com/Plailect/Guide/wiki/9.2.0-Update).

#### What you need

+ The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
+ An internet connection setup on your 3DS

#### Instructions

1. Copy the contents of `starter.zip` to the root of your SD card
2. Open the theme menu, change your theme to any other theme, then switch back. This will initialize the theme data and is required
3. Launch the Settings application
4. Change the date to `January 1, 2000`
5. Change the time to `00:00`
6. Launch the browser, then open the browser settings as fast as possible
7. Scroll to the bottom and Initialize Savedata as fast as possible
8. Navigate to `http://yls8.mtheall.com/3dsbrowserhax_auto.php` on your 3DS without closing the browser
9. If you are running an older version (10.1.0 or below) you will have to tap the right edge of the slider that appears
9. Your console should load the homebrew menu
10. Open the menuhax_manager application
11. Press A to install, it may show some errors but that's fine as long as it shows "Success" towards the end
12. Go back to the main menuhax_manager menu, then select "Configure/check haxx trigger..."
13. Press A to continue, then select "Type1"
14. Hold down on the dpad, then tap the touch screen; this is the recommended button to use for launching menuhax in this guide because it does not interfere with any other functions of tools we will be using
15. Go back to the main menuhax_manager menu, then press B, followed by Start to exit back into the Homebrew Launcher
16. Use the Start button to reboot
17. You can now hold dpad down while the system is booting to launch the homebrew menu