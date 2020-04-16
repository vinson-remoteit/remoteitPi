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

   ### TIPS  
   If you want to put the remote.itPi device to your Wi-Fi, you can just edit wpa_supplicant.conf in /boot before inserting SD card to Raspberry pi. Please edit ```ssid=”YOUR SSID”``` and ```psk=”YOUR PASSPHRASE”```.  
     
   File name: wpa_supplicant.conf  
   ```  
   country=US  
   ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev  
   update_config=1  
   network={  
       ssid="YOUR SSID"  
       psk="YOUR PASSPHRASE"  
   }
   ```  
     
   ![readme-03-02](https://user-images.githubusercontent.com/42136920/79466585-be26ec80-8037-11ea-866f-b2a86358ca24.png)  
   
4. Insert the SD card into remote.itPi device and connect to a wired cable. (When using Wi-Fi, no wired cable connection is required) Connect the power cable, then Raspberry Pi will be boot.  
5. Then access the following website in web browser.  MAKE SURE ANY POP-UP BLOCKER SOFTWARE IS DISABLED ON YOUR BROWSER FOR THE DOMAIN “x.remote.it” or the web pages may not load correctly.  
http://find.remote.it (not https, at this point)  
6. The following page will be shown and start to search your remote.itPi device.  
![readme-06-01](https://user-images.githubusercontent.com/42136920/79466963-368dad80-8038-11ea-8f1b-2e678523d9ce.png)  
7. Your remote.itPi device should be found. Click CONNECT.  
If you cannot find your device, please reload your web browser or wait a few minutes and try again.  
![readme-07-01](https://user-images.githubusercontent.com/42136920/79467097-6046d480-8038-11ea-8984-53e02791d3b3.png)  
8. The following page will be shown.  
![readme-08-01](https://user-images.githubusercontent.com/42136920/79467205-810f2a00-8038-11ea-9628-6c0558c2322d.png)  
Please type your remote.it account and password then click SIGN IN. If you have not created an remote.it account yet, go to “Create an account” page for one.   
9. For the first time, register the your remote.itPi. Enter the Device Name and click REGISTER.  
![readme-09-01](https://user-images.githubusercontent.com/42136920/79467604-e7944800-8038-11ea-8202-29c9b233578d.png)  
10. Next, click ADD+ for adding the service you would like to connect to remotely. For example, add the VNC service on remote.itPi. After typing the information for VNC service, click the check mark.  
![readme-10-01](https://user-images.githubusercontent.com/42136920/79467685-02ff5300-8039-11ea-9582-2e6b618a5113.png)  
![readme-10-02](https://user-images.githubusercontent.com/42136920/79470407-4e673080-803c-11ea-8d17-bc17ea5fc978.png)  
11. Access https://app.remote.it.  
You should see registered remote.itPi on your device list.  

    Click “Device Name”,  
    ![readme-11-01](https://user-images.githubusercontent.com/42136920/79470678-ab62e680-803c-11ea-92da-8cb55104981c.png)  

    then, click “Service”  
    ![readme-11-02](https://user-images.githubusercontent.com/42136920/79470941-f250dc00-803c-11ea-87a0-5dcbe12d07b8.png)  
    
    The information for accessing with VNC will be shown.  
    ![readme-11-03](https://user-images.githubusercontent.com/42136920/79471026-0ac0f680-803d-11ea-8084-4f395ffc4d79.png)  
12. remote.itPi OS default user is “pi“, password is “raspberry“.
You can access VNC to this remote.itPi from anywhere!!
![readme-12-01](https://user-images.githubusercontent.com/42136920/79471171-38a63b00-803d-11ea-945c-3cb98a6a2619.png)
