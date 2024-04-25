# Lab-Box Raspberry Pi Touch Display Module SD Card Image
This repo contains a pipeline to build the SD card image for the [Lab-Box](https://github.com/Wardstein/Lab-Box) Raspberry Pi Touch Display Module.

Tasks this pipeline does:
* Update the base image
* Installs python and all the dependent python packages for the display python software
* Installs the boot config for the Raspberry Pi to use all the needed hardware of the Pi
* Modifies the base image with a new user, and other settings
* Clones and builds the AR1100 touch screen controller setup tool
* Clones the display python software
* And finally cleans and packs the image

# Missing
* Clone Lab-Box Display Software repo
* Install VNC proxy


# Roadmap
* I would like to export a list of all installed packages with versions back to Github Actions and attach that file to the release to track the installed packages
	* But I could not figure out, how I pass something back from within CustoPiZer (chroot) to the Github Actions run environment
* Test building x64 images, here is a hint/fix how it should work: https://github.com/OctoPrint/CustoPiZer/issues/21
