#### Read all of the introductory pages before proceeding.

This is a guide designed to help a user take a completely unmodified 3DS from full stock firmware to arm9loaderhax powered custom firmware.

This guide will work on New 3DS, Old 3DS, and 2DS in the EUR, JAP, or USA regions on firmware 10.6.0 or below.

This guide uses arm9loaderhax, the newest and best method of Custom Firmware that gives us nearly full control of the system only milliseconds into boot, which is similar to the effect of BootMii for the Wii. The benefits of this are numerous, and as such it is recommended to use this guide over any other that relies on outdated software (such as Menuhax or rxTools). (We use rxTools in the 9.2.0 update guide because nothing else supports very old software versions.)

This guide will take you through the steps of getting an entrypoint into the homebrew launcher, downgrading to 9.2.0 to re-enable ARM9-kernel exploits that were blocked, downgrading to version 2.1.0 to get the console-unique OTP, restoring back to 9.2.0, and finally installing arm9loaderhax + CakesFW for permanent homebrew on SysNAND and true custom firmware.

The C, K, and T regions shipped with version 4.X which is after the OTP lockout, and as such *cannot* downgrade far enough to get their OTP or use arm9loaderhax.

C, K, and T regions may be able to switch to U, E, or J temporarily but that is outside of the scope of this guide.

This guide was written by me with the process refined and software developed by the fine folks over at [#Cakey on Freenode](http://webchat.freenode.net/?channels=%23Cakey). See the credits page for the full credits, this guide would not exist without them.