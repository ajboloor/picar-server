# picar-server
Small crash course on setting up and using the Raspberry Pi (as a server, ftp storage, home-base, etc.)

### What is a Raspberry Pi?
A [Raspberry Pi](https://www.raspberrypi.org/) is a credit card sized computer that can run Linux (and other OS) to do almost anything your computer can do. It can be simply connected to a monitor/TV, keyboard and mouse and be used as a regular computer. Because of its low power consumption, it is used as a web-server, file storage system, home automation system, etc. It can also be connected to an Arduino to aid in robotics such as the PiCar.

### Setting it up
#### What you need:
- Raspberry Pi 3 B+ (older models will also work)
- Pi compatible power adapter
- Micro SD Card (with alteast 16GB of memory; you may need an SD card adapter to connect it to your computer) 
- USB keyboard and mouse
- Access to a monitor + HDMI cable
- Access to your router, or a new router
- A laptop for remote access to the Pi

#### Steps:
1. Download the [RASPBIAN STRETCH WITH DESKTOP](https://www.raspberrypi.org/downloads/raspbian/) image.
2. Download [Etcher](https://etcher.io/)
3. Install Raspbian OS to the Raspberry Pi:
    * Insert SD card into your computer. 
    * Run Etcher. 
    * In Etcher, choose the downloaded Raspbian zip or image file. 
    * Choose the SD Card (note: please be very careful to choose the correct drive, it will be formatted). 
    * Flash the image. 
    * Eject SD card and put it into the Raspberry Pi. 
4. Connect the mouse, keyboard and monitor to the Raspberry Pi. Finally connect the power cable to turn on the Raspberry Pi.
5. The default login credentials for the Raspberry Pi are:
    * username: pi
    * password: raspberry
6. Change the password to your liking by opening the terminal and typing:
```
sudo passwd pi
```
7. Use the following command to enable SSH (Secure Shell) which will be used to communicate to your computer wirelessly.
```
sudo raspi-config
```
   * Go to Networking >> SSH >> Enable
8. Connect the Pi to your router (which is connected to your company/university internet port) and reboot the Pi using:
```
sudo reboot now
```
9. Get the local ip address of your Pi using:
```
ifconfig
```
   * Under eth0 >> inet, you will find your Pi's local IP (eg: 192.168.1.123, not the 127.0.0.1 one)
   * Alternatively you can navigate to the router admin page to check the IP addresses of connected devices.
10. On your laptop, use the following instructions based on your OS:
* Windows:
   * Download [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
   * Run Putty
   * For the hostname, use the IP address you got for the Pi, and click Open
* Mac/Linux:
   * Open terminal and type (using the Pi's IP address):
```
ssh pi@192.168.1.123
```
11. Doing 10 will prompt you to enter the Pi's new password. Enter it.
Note: The default port used by Pi for SSH is 22. As long as your router and Pi password are strong, the security risk is minimized. 
