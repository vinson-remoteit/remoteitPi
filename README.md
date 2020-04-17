# Overview
remote.itPi is an SDCard operating system image for Raspberry Pi based on the latest Raspbian OS. The remote.itPi image includes the remote.it application to enable instant remote access to Pi itself and any private network where the Pi is connected.  Once connected to the office network, the Pi will provide direct remote access for authenticated users to the computers, routers, NAS storage boxes, printers, etc. connected to the same remote network.

Download, unzip, and burn the “remote.itPi.img” image file to an SD card, insert it in a Raspberry Pi 3/4 and boot up the Pi. No HDMI display, mouse, or keyboard is needed.  The rootfs partition is automatically extended to maximize the available space on the SDCard.  SSH and VNC are both enabled by default in this image to allow you to bring up the Pi in a Headless (no monitor, no keyboard, no mouse) configuration from any other computer on the same network.  Follow the simple steps below to activate remote access to the Pi, and from there, the Pi will provide direct access to any other device, computer, router, printer, NAS storage box, etc. on the same network.

The remote.itPi OS default user is “pi“, password is “raspberry“.  SSH(port 22) and VNC(port 5900/tcp) are both enabled automatically in this SD Card image.  Make sure to change the Pi password using the “sudo raspi-config” utility after boot up as described in the detailed step-by-step instructions. In addition, root password is not set by default for security perspective. If you would like to set the password for root, you can run command "sudo passwd root".

# Getting started remote.itPi
1. Download remote.itPi.img.zip to your laptop.  
   https://github.com/remoteit/remoteitPi/releases

2. Prepare a formatted SD card. Write the img to the formatted SD card. We recommend using Raspberry Pi Imager.  
   https://www.raspberrypi.org/downloads/  
   When selecting the Operating System, choose “Custom” and then select remote.itPi.img.zip.  
   ![readme-02](https://user-images.githubusercontent.com/42136920/79465318-2543a180-8036-11ea-8a50-a47578932725.png)

   ### TIPS  
   If you want to put the remote.itPi device to your Wi-Fi, you can just edit wpa_supplicant.conf in /boot before inserting SD card to Raspberry pi. Please edit ```ssid=”YOUR SSID”``` and ```psk=”YOUR PASSPHRASE”```. Also, set ```country=US``` to an appropriate value. (your location)
     
   File name: wpa_supplicant.conf  
   ```  
   country=US  
   ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev  
   update_config=1  

   network={
       ssid="remote.itPi"
       psk="remote.itPi"
   }

   network={
       ssid="YOUR SSID"
       psk="YOUR PASSPHRASE"
   }
   ```  
     
   ![readme-02-02](https://user-images.githubusercontent.com/42136920/79466585-be26ec80-8037-11ea-866f-b2a86358ca24.png)  
   
3. Insert the SD card into remote.itPi device and connect to a wired cable. (When using Wi-Fi, no wired cable connection is required) Connect the power cable, then Raspberry Pi will be boot.  
4. Then access the following website in web browser.  MAKE SURE ANY POP-UP BLOCKER SOFTWARE IS DISABLED ON YOUR BROWSER FOR THE DOMAIN “x.remote.it” or the web pages may not load correctly.  
http://find.remote.it (not https, at this point)  
5. The following page will be shown and start to search your remote.itPi device.  
![readme-05-01](https://user-images.githubusercontent.com/42136920/79466963-368dad80-8038-11ea-8f1b-2e678523d9ce.png)  
6. Your remote.itPi device should be found. Click CONNECT.  
If you cannot find your device, please reload your web browser or wait a few minutes and try again.  
![readme-06-01](https://user-images.githubusercontent.com/42136920/79590315-cbb0a500-8111-11ea-9764-5d217d406317.png)  
7. The following page will be shown.  
![readme-07-01](https://user-images.githubusercontent.com/42136920/79590580-306bff80-8112-11ea-88ae-19bd87faab84.png)  
Please type your remote.it account and password then click SIGN IN. If you have not created an remote.it account yet, go to “Create an account” page for one.   
8. Register your remote.itPi device. And adding 3 services by default. Enter the Device Name and click REGISTER.  
![readme-08-01](https://user-images.githubusercontent.com/42136920/79590723-7032e700-8112-11ea-8a38-7d3d4f3cca97.png)  
![readme-08-02](https://user-images.githubusercontent.com/42136920/79591959-3cf15780-8114-11ea-8d5e-c9b2c01a4edf.png)  
Device registration is now complete. Your remote.itPi device will appear in your device list of web portal.  
9. Access https://app.remote.it.  
You should see registered remote.itPi on your device list.  

    Click “Device Name”,  
    ![readme-09-01](https://user-images.githubusercontent.com/42136920/79592786-7d9da080-8115-11ea-90b6-a9280602c17f.png)  

    then, click “Service”  
    ![readme-09-02](https://user-images.githubusercontent.com/42136920/79592797-81312780-8115-11ea-8743-b432b1198b2f.png)  
    
    The information for accessing with VNC will be shown.  
    ![readme-09-03](https://user-images.githubusercontent.com/42136920/79592414-ee908880-8114-11ea-8320-6e7f0aa28449.png)  
10. Open your VNC client application and input URL for connect to remote.itPi.  
![readme-10-01](https://user-images.githubusercontent.com/42136920/79593074-e38a2800-8115-11ea-8fc6-34e3115b1283.png)
11. remote.itPi OS default user is “pi“, password is “raspberry“.
You can access VNC to this remote.itPi from anywhere!!
![readme-10-01](https://user-images.githubusercontent.com/42136920/79471171-38a63b00-803d-11ea-945c-3cb98a6a2619.png)
