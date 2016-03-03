**Read all of the introductory pages before proceeding.**

This is a guide designed to help a user take a completely unmodified 3DS from full stock firmware to arm9loaderhax powered custom firmware.

This guide will work on New 3DS, Old 3DS, and 2DS in the U, E, and J regions on firmware 10.6.0 or below with hardware modification, or firmware 10.3.0 without hardware modification.

This guide will take you through the steps of downgrading 10.4.0 through 10.6.0's NATIVE_FIRM to 10.2.0's NATIVE_FIRM to re-enable ARM11-kernel exploits that were blocked (requires a hardware modification and is not needed if you are on 10.3.0 or below), getting an entrypoint into the homebrew launcher, downgrading to 9.2.0 to re-enable ARM9-kernel exploits that were blocked, downgrading to version 2.1.0 to get the console-unique OTP, restoring back to 9.2.0, and finally installing arm9loaderhax + AuReiNAND CFW.

The C, K, and T regions shipped with version 4.X which is after the OTP lockout, and as such *cannot* downgrade far enough to get their OTP or use arm9loaderhax.

C, K, and T regions may be able to switch to U, E, or J temporarily but that is outside of the scope of this guide.

This guide was written by me with the process refined and software developed by the fine folks over at [#Cakey on Freenode](http://webchat.freenode.net/?channels=%23Cakey). See the credits page for the full credits, this guide would not exist without them.

>[Next](https://github.com/Plailect/plailect.github.io/wiki/Requirements)