# Overview
remote.itPi is an SDCard operating system image for Raspberry Pi based on the latest Raspbian OS. The remote.itPi image includes the remote.it application to enable instant remote access to Pi itself and any private network where the Pi is connected.  Once connected to the office network, the Pi will provide direct remote access for authenticated users to the computers, routers, NAS storage boxes, printers, etc. connected to the same remote network.

Download, unzip, and burn the “remote.itPi.img” image file to an SD card, insert it in a Raspberry Pi 3/4 and boot up the Pi. No HDMI display, mouse, or keyboard is needed.  The rootfs partition is automatically extended to maximize the available space on the SDCard.  SSH and VNC are both enabled by default in this image to allow you to bring up the Pi in a Headless (no monitor, no keyboard, no mouse) configuration from any other computer on the same network.  Follow the simple steps below to activate remote access to the Pi, and from there, the Pi will provide direct access to any other device, computer, router, printer, NAS storage box, etc. on the same network.

The remote.itPi OS default user is “pi“, password is “raspberry“.  SSH(port 22) and VNC(port 5900/tcp) are both enabled automatically in this SD Card image.  Make sure to change the Pi password using the “sudo raspi-config” utility after boot up as described in the detailed step-by-step instructions. In addition, root password is not set by default for security perspective. If you would like to set the password for root, you can run command "sudo passwd root".

# What You'll Need Before Installing
- Download [remote.itPiImg.zip](https://github.com/remoteit/remoteitPi/releases)
- Formatted microSD card (8GB minimum)
- microSD card reader
- [Raspberry Pi Imager](https://www.raspberrypi.org/downloads/ ) (To write the remote.itPi image onto the microSD)

# Getting started remote.itPi

## Preparing the remote.itPi Image 
1. Download [remote.itPi.img.zip](https://github.com/remoteit/remoteitPi/releases) onto your laptop/desktop if you haven't done so already.

2. Extract the contents of the .zip file.

3. Connect your microSD card reader (with the formatted microSD inserted) to your computer. (If you haven't formatted your microSD, you can use Raspberry Pi Imager to do so.)

4. Launch Raspberry Pi Imager. 
- Under "Operating System," click **CHOOSE OS**. When prompted, select the <**Use custom** option. Locate and select **remote.itPi.img** that you extracted from the .zip file.
- Under "SD Card," click **CHOOSE SD CARD**. When prompted, select your formatted microSD.
- Click **WRITE** to begin writing the remote.itPi image onto the microSD. This process will take a few minutes. 

![readme-02](https://user-images.githubusercontent.com/42136920/79465318-2543a180-8036-11ea-8a50-a47578932725.png)

5. If you plan on connecting the remote.itPi device to the internet via Ethernet, you can skip this step and continue to Step 6. If you plan on connecting the remote.itPi device to the internet via Wi-Fi, follow the instructions below:
- Navigate to the microSD's file directory and open **wpa_supplicant.conf** in a text editor.
- On the line that says ```ssid="YOUR SSID"```, replace ```YOUR SSID``` with the name of your Wi-Fi network. (Example: ```ssid="MyWiFi123"```)
- On the line that says ```psk="YOUR PASSPHRASE"```, replace ```YOUR PASSPHRASE``` with the password to your Wi-Fi network.(```psk="P@ssword"```
- On the line that says ```country=US```, replace ```US``` with your country code. 
- Save the file.
     
   ![readme-02-02](https://user-images.githubusercontent.com/42136920/79466585-be26ec80-8037-11ea-866f-b2a86358ca24.png)  
   
## Installing the Image
6. Remove the microSD from the card reader and insert it into the remote.itPi. If you are connecting the remote.itPi to the internet via Ethernet, plug the cable into the remote.itPi. 
7. Connect the power cable to the remote.itPi to power on the device. 
8. From your computer, open your browser and navigate to: http://find.remote.it. **(Note: Make sure you disable any pop-up blocker extensions or software for the domain "x.remote.it" or this webpage may not load properly.)**  
9. The webpage will start to search for your remote.itPi device. If your device isn't detected after the initial search, wait a minute, then click **Search again**.
- Note: If your device isn't detected after a few search attempts, make sure your Wi-Fi credentials are correct in the **wpa_supplicant.conf** file (if the device is connected Wi-Fi) or that the Ethernet is connected properly. 
![readme-05-01](https://user-images.githubusercontent.com/42136920/79466963-368dad80-8038-11ea-8f1b-2e678523d9ce.png)  
10. Once your remote.itPi is detected, click **CONNECT** to connect to it.    
![readme-06-01](https://user-images.githubusercontent.com/42136920/79590315-cbb0a500-8111-11ea-9764-5d217d406317.png)  
11. You will be prompted to log in to your remote.it account. If you have not created a remote.it account, click "Create an account" to create one.  
![readme-07-01](https://user-images.githubusercontent.com/42136920/79590580-306bff80-8112-11ea-88ae-19bd87faab84.png)  
12. Once you log in, you will be prompted to register your remote.itPi by providing a name for it. Enter a name, then click **REGISTER**.
![readme-08-01](https://user-images.githubusercontent.com/42136920/79590723-7032e700-8112-11ea-8a38-7d3d4f3cca97.png)  
![readme-08-02](https://user-images.githubusercontent.com/42136920/79591959-3cf15780-8114-11ea-8d5e-c9b2c01a4edf.png)  
13. Congratulations! Your remote.itPi is now registered to remote.it! You can now connect to your remote.itPi from any device with remote.it installed.

## Using the remote.it Web Portal
You can also use the [remote.it web portal](https://app.remote.it) to connect to your remote.itPi device. You can view it on the web portal's "Devices" page. 

1. Find and click on your remote.itPi device name.
    ![readme-09-01](https://user-images.githubusercontent.com/42136920/79592786-7d9da080-8115-11ea-90b6-a9280602c17f.png)  

2. You will be prompted with a dialog window that shows all the available services on your remote.itPi device. Click on a service name to start a connection.
    ![readme-09-02](https://user-images.githubusercontent.com/42136920/79592797-81312780-8115-11ea-8743-b432b1198b2f.png)  
    
3. When a connection is established, you will see information on how to access the service. Here is an example of the information for accessing the device via VNC service:
    ![readme-09-03](https://user-images.githubusercontent.com/42136920/79592414-ee908880-8114-11ea-8320-6e7f0aa28449.png)  
4. Open your VNC client application and input the provided URL to connect to your remote.itPi.
![readme-10-01](https://user-images.githubusercontent.com/42136920/79593074-e38a2800-8115-11ea-8fc6-34e3115b1283.png)
5. You will be prompted to enter a username and password. The default login information for remote.itPi is:
- Username: pi
- Password: raspberry
![readme-10-01](https://user-images.githubusercontent.com/42136920/79471171-38a63b00-803d-11ea-945c-3cb98a6a2619.png)
6. You can now access VNC to this remote.itPi from anywhere!
