The Homebrew Launcher has many different entrypoints, or methods of launching. The most common is browserhax, which launches the Homebrew Launcher using nothing more than the included browser. This can then be used to install menuhax, which lets you hold a button while the console is booting up to launch the Homebrew Launcher before the rest of the system starts.

If you are between versions 9.0.0 and 9.8.0, you should follow this guide, but you can skip changing the date and time in the beginning.

If you are between versions 9.9.0 and 10.5.0, you should follow this guide as written.

If you are between versions 10.6.0 and 10.7.0, you can find instructions for     
+ [Ninjhax](http://smealum.github.io/ninjhax2/) (requires Cubic Ninja)    
+ [oot3dhax](https://github.com/yellows8/oot3dhax) (requires Ocarina of Time 3D and either a powersaves or another 3DS which has the HomeBrew Launcher)    
+ [~~supermysterychunkhax~~](https://smd.salthax.org/) ~~(requires Pokemon Super Mystery Dungeon and either a powersaves or another 3DS which has the HomeBrew Launcher)~~ **supermysterychunkhax is, for now, [incompatible](http://gbatemp.net/threads/supermysterychunkhax-savegame-exploit-for-super-mystery-dungeon.423926/page-9#post-6303617) with downgrading**    

Browserhax and menuhax were patched with 10.6.0 and will no longer work.

If you are below version 9.0.0, you can find instructions for updating to 9.2.0-20 [here](https://github.com/Plailect/Guide/wiki/9.2.0-Update). Browserhax does not support versions below 9.0.0.

If you are using a game for hacks, you will need to enter HomeBrew Launcher using it instead of browserhax or menuhax while on 10.6.0/10.7.0. After completing the initial 9.2.0 downgrade, you no longer need the game to complete the rest of the guide.

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
8. Navigate to `http://yls8.mtheall.com/3dsbrowserhax_auto.php` on your 3DS (if you get a slider, zoom all the way in on it, then tap the very right edge of it; this can take quite a few tries)
9. Your console should load the homebrew menu
10. Open the menuhax_manager application
11. Press A to install, it may show some errors but that's fine as long as it shows "Success" towards the end
12. Go back to the main menuhax_manager menu, then select "Configure/check haxx trigger..."
13. Press A to continue, then select "Type1"
14. Hold down on the D-Pad, then tap the touch screen; this is the recommended button to use for launching menuhax in this guide because it does not interfere with any other functions of tools we will be using
15. Go back to the main menuhax_manager menu, then press B, followed by Start to exit back into the Homebrew Launcher
16. Use the Start button to reboot
17. You can now hold D-Pad down while the system is booting to launch the homebrew menu
