# Lab-Box Raspberry Pi Touch Display Module SD Card Image
This repo contains a pipeline to build the SD card image for the [Lab-Box](https://github.com/Wardstein/Lab-Box) Raspberry Pi Touch Display Module.

Tasks this pipeline does:
* Update the base image
* Installs python and all the dependent python packages for the display python software
* Installs the boot config for the Raspberry Pi to use all the needed hardware of the Pi
* Modifies the base image with a new user, and other settings
* Clones and builds the AR1100 touch screen controller setup tool (installing my fork, but special thanks to https://github.com/tom-2015/rpi-AR1100 for the tool)
* Clones and installs the VNC proxy [noVNC websockify](https://github.com/novnc/websockify) 
* Clones the display python software
* And finally cleans and packs the image

After you flashed an SD card and let the module/RasPi boot for the first time, it will go through multiple reboots until all stuff is set up. It will also stay still for a few minutes at some steps of the boot process, so don't worry. But this usually only takes five minutes (tested on a Raspberry Pi 3B+).


# Flashing an SD card
To flash an SD card, I can recommend using [Balena Etcher](https://etcher.balena.io/). Just download the latest image from the [release page of this repo here](https://github.com/Wardstein/Lab-Box-RaspiDisplayModule-Image/releases) and select it in etcher.

TODO: test Raspiberry Pi Imager, as it can apply WiFi and locale settings


# Missing
* Clone Lab-Box Display Software repo



# Roadmap
* I would like to export a list of all installed packages with versions back to Github Actions and attach that file to the release to track the installed packages
	* But I could not figure out, how I pass something back from within CustoPiZer (chroot) to the Github Actions run environment
* Test building x64 images, here is a hint/fix how it should work: https://github.com/OctoPrint/CustoPiZer/issues/21
