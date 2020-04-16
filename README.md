# Overview
remote.itPi is an SDCard operating system image for Raspberry Pi based on the latest Raspbian OS. The remote.itPi image includes the remote.it application to enable instant remote access to Pi itself and any private network where the Pi is connected.  Once connected to the office network, the Pi will provide direct remote access for authenticated users to the computers, routers, NAS storage boxes, printers, etc. connected to the same remote network.

Download, unzip, and burn the “remote.itPi.img” image file to an SD card, insert it in a Raspberry Pi 3/4 and boot up the Pi. No HDMI display, mouse, or keyboard is needed.  The rootfs partition is automatically extended to maximize the available space on the SDCard.  SSH and VNC are both enabled by default in this image to allow you to bring up the Pi in a Headless (no monitor, no keyboard, no mouse) configuration from any other computer on the same network.  Follow the simple steps below to activate remote access to the Pi, and from there, the Pi will provide direct access to any other device, computer, router, printer, NAS storage box, etc. on the same network.

The remote.itPi OS default user is “pi“, password is “raspberry“.  SSH(port 22) and VNC(port 5900/tcp) are both enabled automatically in this SD Card image.  Make sure to change the Pi password using the “sudo raspi-config” utility after boot up as described in the detailed step-by-step instructions. In addition, root password is not set by default for security perspective. If you would like to set the password for root, you can run command "sudo passwd root".

# Getting started remote.itPi
1. Download remote.itPi.img.zip to your laptop.  
   https://github.com/remoteit/remoteitPi/releases

2. Extract .zip file.

3. Prepare a formatted SD card. Write the img to the formatted SD card. We recommend using Raspberry Pi Imager.  
   https://www.raspberrypi.org/downloads/  
   When selecting the Operating System, choose “Custom” and then select the unzipped folder remote.itPi.img in the location where you unzipped it.  
   ![readme-03](https://user-images.githubusercontent.com/42136920/79465318-2543a180-8036-11ea-8a50-a47578932725.png)
