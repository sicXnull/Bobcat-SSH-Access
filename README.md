# Bobcat-SSH-Access

Gain SSH Access to your Bobcat Miner.

This "exploit" allows you to gain SSH Access to your Bobcat Miner. Something that is blocked from the factory.

## Versions supported

To identify your Bobcat version, check the sticker on the bottom of the device. The serial number will start with 28/285/290 or 295

- **Bobcat 285 (Both Versions)**  
  [Download](https://github.com/sicXnull/Bobcat-SSH-Access/releases/download/1.0/Bobcat_SSH_285.img.xz)

- **Bobcat 290/295**  
  [Download](https://github.com/sicXnull/Bobcat-SSH-Access/releases/download/1.0/Bobcat_SSH_29x.img.xz)

280 not available yet, simply because I don't have access to the original OS. Will add support when I come across one. 

## How it Works

A minimal operating system is booted via SD Card.

Upon boot, a script (located at `/sbin/init`) does the following.

1) Mounts the EMMC.
2) Backs up the original files listed below.
2) Copies a modified `shadow` file (password authentication) to `/etc` directory.
3) Copies a modified `sshd_config` file to `/etc/ssh`.
4) Sets immutable permissions so an OTA Update (if one were to ever happen) does not remove the "hack".

## Install

1) Using Balena etcher or dd, burn the correct image to SD card.
2) Insert SD card into Bobcat. Power On.
3) The script will run. On 29X, a blue light will start flashing when complete, On 285 it will not, just wait 90 seconds to be safe.

That's it. Remove the SD card, and boot original OS. The SSH Username is admin and Password is bobcat

