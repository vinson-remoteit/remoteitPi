# Overview
remote.itPi is an SDCard operating system image for Raspberry Pi based on the latest Raspbian OS. The remote.itPi image includes the remote.it application to enable instant remote access to Pi itself and any private network where the Pi is connected.  Once connected to the office network, the Pi will provide direct remote access for authenticated users to the computers, routers, NAS storage boxes, printers, etc. connected to the same remote network.

Download, unzip, and burn the “remote.itPi.img” image file to an SD card, insert it in a Raspberry Pi 3/4 and boot up the Pi. No HDMI display, mouse, or keyboard is needed.  The rootfs partition is automatically extended to maximize the available space on the SDCard.  SSH and VNC are both enabled by default in this image to allow you to bring up the Pi in a Headless (no monitor, no keyboard, no mouse) configuration from any other computer on the same network.  Follow the simple steps below to activate remote access to the Pi, and from there, the Pi will provide direct access to any other device, computer, router, printer, NAS storage box, etc. on the same network.

The remote.itPi OS default user is “pi“, password is “raspberry“.  SSH(port 22) and VNC(port 5900/tcp) are both enabled automatically in this SD Card image.  Make sure to change the Pi password using the “sudo raspi-config” utility after boot up as described in the detailed step-by-step instructions. In addition, root password is not set by default for security perspective. If you would like to set the password for root, you can run command "sudo passwd root".

# What You'll Need Before Installing
- [remote.itPiImg.zip](https://github.com/remoteit/remoteitPi/releases)
- Formatted MicroSD card (8GB minimum)
- MicroSD card reader
- [Raspberry Pi Imager](https://www.raspberrypi.org/downloads/ ) (To write the Pi Image onto SD card)

# Getting started remote.itPi

## Preparing the remote.itPi Image 
1. Download [remote.itPi.img.zip](https://github.com/remoteit/remoteitPi/releases) onto your laptop/desktop if you haven't done so already.

2. Unzip the downloaded .zip file. You should see **remote.itPi.img**. 

3. Connect the microSD card reader with the formatted microSD into your laptop or desktop. (If you haven't formatted your microSD, you can use **Raspberry Pi Imager** to do so.)

4. Launch **Raspberry Pi Imager**. 
- Under "Operating System," click the <b>CHOOSE OS</b> button. When prompted, select <b>Use custom</b>, then locate and select the the remote.itPi.img you extracted back in Step 2.
- Under "SD Card," click the <b>CHOOSE SD CARD</b> button. When prompted, select your formatted microSD.
- Click the <b>WRITE</b> button to begin writing the Pi Image onto the microSD. This process will take a few minutes. 

![readme-02](https://user-images.githubusercontent.com/42136920/79465318-2543a180-8036-11ea-8a50-a47578932725.png)

5. If you plan on connecting the Raspberry Pi to the internet via Ethernet, you can skip this step. If you plan on connecting the Raspberry Pi to the internet via Wi-Fi, please follow the instructions below:
- Navigate to the microSD's file directory and open <b>wpa_supplicant.conf</b> in a text editor.
- Edit ```ssid="YOUR SSID""``` with the name of your Wi-Fi network and ```psk=""YOUR PASSPHRASE``` with the password to your Wi-Fi network.
- Edit ```country=US``` to your country location. 
     
   ![readme-02-02](https://user-images.githubusercontent.com/42136920/79466585-be26ec80-8037-11ea-866f-b2a86358ca24.png)  
   
## Installing the Image
6. Insert the microSD card into Raspberry Pi and connect it to the internet via Ethernet (If you configured the Wi-Fi to the Raspberry Pi from Step 5, you don't need an Ethernet). 
7. Connect the power cable to the Raspberry Pi to power on the device. 
8. From your computer, open your browser and navigate to the following: http://find.remote.it. **(Note: Make sure you disable any pop-up blocker extensions or software for the domain "x.remote.it" or this webpage may not load properly.)**  
9. The webpage will start to search for your Raspberry Pi. If your Raspberry Pi isn't detected after the initial search, wait a few minutes and before clicking **Search again**.
![readme-05-01](https://user-images.githubusercontent.com/42136920/79466963-368dad80-8038-11ea-8f1b-2e678523d9ce.png)  
10. Once your Raspberry Pi is detected, click **CONNECT**.    
![readme-06-01](https://user-images.githubusercontent.com/42136920/79590315-cbb0a500-8111-11ea-9764-5d217d406317.png)  
11. You will be prompted to log in to your remote.it account. If you have not created a remote.it account, click "Create an account" to create one.  
![readme-07-01](https://user-images.githubusercontent.com/42136920/79590580-306bff80-8112-11ea-88ae-19bd87faab84.png)  
12. Register your Raspberry Pi by confirming the device name and clicking **REGISTER**. You also have the option to choose which services to register to your device.
![readme-08-01](https://user-images.githubusercontent.com/42136920/79590723-7032e700-8112-11ea-8a38-7d3d4f3cca97.png)  
![readme-08-02](https://user-images.githubusercontent.com/42136920/79591959-3cf15780-8114-11ea-8d5e-c9b2c01a4edf.png)  
13. Congratulations! Your Raspberry Pi is now registered to remote.it! You should see your remote.itPi device appear on the Devices tab.

## Using the remote.it Web Portal
You can also use the [remote.it web portal](https://app.remote.it) to connect to your remote.itPi device. You can view it on the Devices page. 

1. Find and click on your remote.itPi device name.
    ![readme-09-01](https://user-images.githubusercontent.com/42136920/79592786-7d9da080-8115-11ea-90b6-a9280602c17f.png)  

2. You will be prompted with a dialog window that shows you all the available services on your remote.itPi device. Click on a service name to start a connection.
    ![readme-09-02](https://user-images.githubusercontent.com/42136920/79592797-81312780-8115-11ea-8743-b432b1198b2f.png)  
    
3. When a connection is made, you will see information for accessing the service. Here is an example of the information for accessing the device via VNC:
    ![readme-09-03](https://user-images.githubusercontent.com/42136920/79592414-ee908880-8114-11ea-8320-6e7f0aa28449.png)  
4. Open your VNC client application and input the provided URL to connect to your remote.itPi.
![readme-10-01](https://user-images.githubusercontent.com/42136920/79593074-e38a2800-8115-11ea-8fc6-34e3115b1283.png)
5. You will be prompted to enter a username and password. The default login information for remote.itPi is:
- Username: pi
- Password: raspberry
![readme-10-01](https://user-images.githubusercontent.com/42136920/79471171-38a63b00-803d-11ea-945c-3cb98a6a2619.png)
6. You can now access VNC to this remote.itPi from anywhere!
