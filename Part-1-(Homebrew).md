The Homebrew Launcher has many different entrypoints, or methods of launching. The most common is browserhax, which launches the Homebrew Launcher using nothing more than the included browser. This can then be used to install menuhax, which lets you hold a button while the console is booting up to launch the Homebrew Launcher before the rest of the system starts.

9.0.0 - 9.8.0: Follow this guide, but skip changing the date and time and initializing savedata in the beginning.

9.9.0 - 10.6.0: Follow this guide as written.

\>=10.7.0:   
Set your primary DNS to `107.211.140.065` so as not to trigger the browser version check.
  + If on this browser version, you ever receive a message to update your browser, you will need an alternate entry point from below as your browser will have detected it is not running the latest version.
  + Once this message appears for the first time, it is impossible to get rid of it so you must get an alternate entrypoint.

\>=9.0.0 but with a browser version (the last number in the version, such as 11.0.0**-33**) of less than **-20**:    
Use the following instructions for various alternate entrypoints *in place of* Part 1

+ [Ninjhax](http://smealum.github.io/ninjhax2/) (requires Cubic Ninja)    
+ [smashbroshax](https://gbatemp.net/threads/397194/) (requires Super Smash Bros. and **only works on New 3DS**)
+ [oot3dhax](https://github.com/yellows8/oot3dhax) (requires Ocarina of Time 3D and either a powersaves or another 3DS which has the HomeBrew Launcher)       
+ [supermysterychunkhax](https://smd.salthax.org/) (requires Pokemon Super Mystery Dungeon and another 3DS which has the HomeBrew Launcher)
+ [freakyhax](http://plutooo.github.io/freakyhax/) (requires Freakyforms Deluxe)
+ [basehaxx](http://mrnbayoh.github.io/basehaxx/) (requires Pokemon Omega Ruby/Alpha Sapphire ver 1.0/1.4 with the ability to have a secret base and another 3DS which has the HomeBrew Launcher)
+ [BASICSploit](https://mrnbayoh.github.io/basicsploit/) (requires SmileBASIC)
+ [smilehax](https://plutooo.github.io/smilehax/) (requires SmileBASIC)
+ [stickerhax](https://github.com/yellows8/stickerhax) (requires Paper Mario: Sticker Star and another 3DS which has the HomeBrew Launcher)

**11.0.0: You MUST have [downgraded your firmware](https://github.com/Plailect/Guide/wiki/Firmware-Downgrade) in order to successfully complete Part 2 later.**

<9.0.0: you can find instructions for updating to 9.2.0-20 [here](https://github.com/Plailect/Guide/wiki/9.2.0-Update). Browserhax does not support versions below 9.0.0.

If you are using a game for hax because your browser version is incompatible, you will need to enter HomeBrew Launcher using it and install menuhax. After installing menuhax, you no longer need the game to complete the rest of the guide.

#### Overview of steps

This section will take you through the steps of downloading [smea](https://github.com/smealum)'s Homebrew Starter Pack which includes the necessary file to run the Homebrew Launcher (`boot.3dsx`) along with some other useful utilities (the apps in `/3ds/`).

All \*hax variety entrypoints (which are the most commonly used entrypoints such as Ninjhax, oot3dhax, menuhax, and browserhax), after setting up their exploit code, launch a file named `boot.3dsx`, which is the Homebrew Launcher in this case. The file itself can be any valid `.3dsx` homebrew, but the Homebrew Launcher is prefered because it lets us launch *other* homebrew once it's running.

This guide uses browserhax, which runs the homebrew launcher through an exploit site, to install menuhax, which is an exploited theme that can run the Homebrew Launcher at boot. Browserhax does not work on some browser versions, and as a result if you are on one of these browser versions, you will need one of the alternate entrypoints described at the top.

All versions above 9.9.0 include a browser version check that will not allow you to go to any sites if you are not on the latest system version, which means you'd normally have to update to the latest to run browserhax, but that would result in patching out browserhax.

The [workaround](https://yls8.mtheall.com/3dsbrowserhax.php) for this, discovered by [yellows8](https://github.com/yellows8), is to change the clock to the date detailed below, then initialize the savedata quickly (*before* the 3DS connects to Nintendo to verify browser version). At this point, you can continue to use the browser normally until the clock hits one day later or you exit the browser using the home button.

Following this, we setup menuhax (a custom exploit theme) to launch `boot.3dsx` (in this case the Homebrew Launcher) when we hold D-Pad Down on boot.

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
8. Navigate to `http://yls8.mtheall.com/3dsbrowserhax_auto.php` or scan the QR code on your 3DS (if you get a slider, zoom all the way in on it, then tap the very right edge of it; this can take quite a few tries)    
![browserhax_auto](https://yls8.mtheall.com/3dsbrowserhax_auto_qrcode.png)
    + If you get an error, [follow this troubleshooting guide](https://github.com/Plailect/Guide/wiki/Troubleshooting#ts_browser)
9. Your console should load the homebrew menu
10. Open the menuhax_manager application
11. Press A to install, it may show some errors but that's fine as long as it shows "Success" towards the end
12. Go back to the main menuhax_manager menu, then select "Configure/check haxx trigger..."
13. Press A to continue, then select "Type1"
14. Hold down on the D-Pad, then tap the touch screen; this is the recommended button to use for launching menuhax in this guide because it does not interfere with any other functions of tools we will be using
15. Go back to the main menuhax_manager menu, then press B, followed by Start to exit back into the Homebrew Launcher
16. Use the Start button to reboot
17. You can now hold D-Pad down while the system is booting to launch the Homebrew Launcher
