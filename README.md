# Galileo Resurrection
Do you have an old Intel Galileo and thought it was for the trash as it's a dead board that nobody cares about anymore?

I thought that too! With a little help from some Intel engineers I was able to breathe some life into my old Galileo!


![image](https://user-images.githubusercontent.com/1159924/114682307-de4ec180-9d06-11eb-9cbf-6824e44cb36a.png)

![image](https://user-images.githubusercontent.com/1159924/114681955-8ca63700-9d06-11eb-85a9-0f5da03979d4.png)


## What does this project achieve?

This project supplies real Linux distros on a Mainline kernel to use on your galileo. Simple burn the chosen image onto an SD card and plug it in!

Features:

* Mainline Linux 3.10.x kernel
* Alpine Linux Image - Nice and light - suits for board well
* Arch linux (32bit) Image - Slightly heavy, rolling release and good selection of packages
* Minimal buildroot Image (console access only - only as an example)
* Networking and SSH initialised on first boot(not on buildroot image). Just find your board's IP address and ssh.
* Credentials: galileo/galileo root/root(no ssh)

## TODO:

* Provide instructions on how to build more kernel modules (this board really isn't cut out for compiling code)
* Custom kernel versions
* Custom versions of Alpine Linux (3.13 is hardcoded - latest at time of writing)
* Automatically resize the SD card - you have to do that yourself (cfdisk, resize2fs).

## Things you should know

* This is a slow board. 400mhz and 256MB of ram.
* This board does not have normal features of a modern x86 processor(no MMX for example). And Go executables will not work!
* I will not be very proactive keeping this project up-to-date - security updates won't be quick. Don't store your Bitcoin wallet on it.
* Your board will cease to work with Arduino etc, it will become an ordinary Linux machine. To revert simply remove the SD card.
* Gen1 has been tested by me, Gen2 may work.
* Haven't tested GPIO stuff.
* Some packages are affected by the "Segfault" but for Quark. Seems to affect networking applications the worst, nginx and git for example.

## Instructions

First download one of the built images from https://github.com/dmarkey/galileo-resurrection/releases/tag/Resurrection-2021-April

sdcard-alpine.img.gz -> Alpine linux 3.13

sdcard-arch.img.gz -> Arch linux

sdcard.img -> Buildroot

Uncompress the chosed image, find a Micro SD card that is 8GB+ and use dd to write the image to the SD card. Insert into your Galileo and power on. Check your router for the assigned IP address "galileo" is the configured hostname and SSH as `galileo/galileo`. `su -` to root using password `root`







