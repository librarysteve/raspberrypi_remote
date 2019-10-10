# raspberrypi_remote
How to connect to a Raspberry PI from another computer using just an ethernet cable.


## Burn the OS image
1) Visit https://www.raspberrypi.org/downloads/raspbian/ and grab the latest copy of Raspbian (I'm using lite)
2) Unzip the file to decompress the ".img" file
3) Insert your SD card into your computer
4) Burn the image to the SD card (I prefer to use Balena Etcher https://www.balena.io/etcher/)
  a) Click "Select Image" and select the .img file.
  b) Click Select targe and select the SD card (normally it will be the only option)
  c) Click "Flash" and wait

## Enable SSH before first boot
*The next steps depend on your OS*

### For Windows
1) Remove and reinsert the SD card in your windows computer
2) Open the file browser and look for the driver labeled "boot"
3) Right click in the file area of the boot drive to bring up the context menu
4) Select "New > Text File" and name the file "ssh" without a file extension
5) If you recieve a warning message that is noraml, select "YES" and eject the SD card
6) Insert the SD card into the PI, connect the pi to your PC with an ethernet cable and wait no less than 5 minutes
7) Grab a copy of PuTTY from [The PuTTY Official Website](https://www.putty.org/)
      Alternatively you can grab the portable version [here](https://the.earth.li/~sgtatham/putty/latest/w64/putty.exe)
8) Open putty and type "raspberrypi.local" in the "HOSTNAME(or IP address)" box
9) Click "open" to launch a connection attempt
10) Use the username 'pi' and the password 'raspberry' to log in 


### For OSX/Linux
1) Remove and reinsert the SD card into your computer
2) Open the file browser/finder to the 'boot' drive of the SD card
3a) In OSX finder, click the 'Finder' menu on menu bar. Select "Services > New Terminal as Folder"
3b) In Linux (Debian or Ubuntu) open the file browser and right click on the background, select "Open terminal here" or a similar option
4) In your OSX or Linux terminal use the following command:
```sh
touch ssh
```
5) Eject the SD card, and insert it into the Pi
6) Connect the Pi to your computer via ethernet and power on the Pi
7) Wait at least 5 minutes
8) In the terminal (either linux or OSX) use the following command:
```sh
sudo ssh pi@raspberrypi.locl
```
9) type "yes" to respond to the security question and log in with the password "raspberry"


