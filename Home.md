##### I will be out of town (without internet) until July 15th. The following users (all OPs at [#Cakey on Freenode](http://webchat.freenode.net/?channels=%23Cakey)) have been given collaborator status and can edit any of these pages:    
  + [@d0k3](https://github.com/d0k3)
  + [@dark-samus](https://github.com/dark-samus/)
  + [@gemarcano](https://github.com/gemarcano)
  + [@mid-kid](https://github.com/mid-kid)

---

##[AGE (a9lh guide enhancement)](http://bob.me.tz/age/)

[Para visitar este tutorial en Español, pulsa aquí (traducido por Fernando51 e Armastan).](https://github.com/Armastan/Guia/wiki)    
[Pour visiter ce tutoriel en français, cliquez ici (traduit par Ginkyway).](https://github.com/Ginkyway/Guide/wiki/Accueil)    
[Para visitar este tutorial em português, clique aqui (traduzido por HenryLeon e asaver).](https://github.com/HenryLeonheart/Guide_Portuguese/wiki)     
[Für den Deutschen Guide klickt hier (Übersetzt von Konsolenumbau.Expert).](https://github.com/KonsoleHL/Guide/wiki)    
[Pentru traducere in limba romana click aici (tradus de DAVIDRO999000999).](https://github.com/DAVIDRO999000999/Guide/wiki/Pagina-de-Start)
[如需查看本教程的中文版，请点击这里（由majia67翻译）](
https://github.com/majia67/3DS-ARM9LoaderHax-Guide/wiki/)

#### Read all of the introductory pages before proceeding.

**Before beginning the guide, you must know the risks of 3DS hacking: EVERY time you modify your system, there is always the potential for an UNRECOVERABLE brick. They're rare, but still a possibility so make sure you follow ALL directions EXACTLY.**

This guide is designed to help a user take a completely unmodified 3DS from full stock
firmware to arm9loaderhax powered custom firmware (which allows almost full control of the device for things such as installing software to the home menu).

**There has been some confusion among users about what devices they own and their names. See [this](https://github.com/Plailect/Guide/wiki/Device-Info) page for images of each kind of 3DS.**

This guide will work on New 3DS, Old 3DS, and 2DS in the EUR, JPN, or USA regions on firmware 11.0.0 or below.

This guide uses arm9loaderhax, the newest and best method of Custom Firmware that gives us nearly full control of the system only milliseconds into boot, which is similar to the effect of BootMii for the Wii. The benefits of this are numerous, and as such it is recommended to use this guide over any other that relies on outdated software (such as menuhax or rxTools). (We use rxTools in the 9.2.0 update guide because nothing else supports very old software versions.)

This guide will take you through the steps of getting an entrypoint into the HomeBrew Launcher, downgrading to 9.2.0 to re-enable ARM9-kernel exploits that were blocked, downgrading to version 2.1.0 to get the console-unique OTP, then installing arm9loaderhax + Luma3DS for permanent homebrew on SysNAND and true custom firmware.

**If everything goes according to plan, you will lose no data and end up with everything that you started with (games, NNID, saves, etc will be preserved).**

The China, Korea, and Taiwan regions shipped with version 4.X which is after the OTP lockout, and as such *cannot* downgrade far enough to get their OTP or use arm9loaderhax.

A large part of this guide is lengthy NAND dumps and downgrades, so the entire process can take *several* hours thanks to the 3DS's slow processor.

C, K, and T regions may be able to switch to U, E, or J temporarily but that is outside of the scope of this guide.

This guide was written by me with the process refined and software developed by the fine folks over at [#Cakey on Freenode](http://webchat.freenode.net/?channels=%23Cakey). See the credits page for the full credits, this guide would not exist without them.

Sha256Sum | Zip File
:---: | :---:
<sub>5736ec8d40303b549f11c06b3811817531e17646a91ee2bb0d94afff69cf3a4e</sub> | <sub>2.1.0E(Full).zip</sub>
<sub>95520c64f3b42a13b8bf266b86edbef9e3ec5e32643ebb6c97f846c2a2647980</sub> | <sub>2.1.0J(Full).zip</sub>
<sub>919e4423a45e019b1984ca7da341ac39282e7992fae62ea37d385b37a8ac621f</sub> | <sub>2.1.0U(Full).zip</sub>
<sub>e7fbaf4ee01b81a3c2297028ef3fddc002f6933bfd20c2453bc6137bda89e5fd</sub> | <sub>9.2.0-20E(Full)_n3DS.zip</sub>
<sub>79407686741732f90db30cd591254f1c591df2dbd9787be78a03b1aceef9f2fe</sub> | <sub>9.2.0-20E(Full).zip</sub>
<sub>9ba7bc4eeab39b484e710d7ad05bfeae3b143812d85bbe128f283a79aa1ba80b</sub> | <sub>9.2.0-20J(Full)_n3DS.zip</sub>
<sub>14c74b462f2db9ba0bdcf1060bfd89345ac9cf863a35092baadd503d6040b837</sub> | <sub>9.2.0-20J(Full).zip</sub>
<sub>38ea53d81763408178d796492d6397cfc1eae422a8a2a4b1270678e1ab30043c</sub> | <sub>9.2.0-20U(Full)_n3DS.zip</sub>
<sub>ff6e7ced330120cdc34cba4536e4ec6609653234d5414f2a727263dfabfe46a3</sub> | <sub>9.2.0-20U(Full).zip</sub>
