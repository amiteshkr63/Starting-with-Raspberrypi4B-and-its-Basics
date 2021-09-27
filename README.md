# My work with RaspberryPi4B

## 1)Making Raspberry HEADLESS (SETUP)
### Connecting Raspberry pi to our lapi WIRELESSLY over Wifi


#### TASK_1:Upload Rasberry OS on SD card

##### 1)Goto link below:
https://www.raspberrypi.org/software/
Download the Raspian imager for your OS i.e.,windows/mac/linux..

##### 2)Goto link below:
https://www.raspberrypi.org/software/operating-systems/
Download the raspberri OS image as per your need

##### 3)Extract the downloaded image

##### 4)Plug the sd card reader to your lapi USB.
NOTE:Make sure you formatted the SD from SD card Formatter
You can download it from:
https://www.sdcard.org/downloads/formatter/sd-memory-card-formatter-for-windows-download/

##### 5)Install the IMAGER(imager_1.6.2.exe)

##### 6)Run the Imager

##### 7)A window will open
Goto options:
CHOOSE OS>Use Custom>[Goto Location where you downloded the raspian OS]>Choose SD card>WRITE
Then,wait for to complete WRITE of SD card 

#### TASK:Upload Rasberry OS on SD card:
SUCCESSFUL

#### TASK_2:CONNECTING Our raspberry pi to INTERNET

##### 1)Create a <ssh> named file in boot drive of SD card

##### 2)Then, create another <wpa_supplicant.conf> in boot drive of sd card.

##### 3)Paste Following command into <wpa_supplicant.conf> file:

#code starts
country=IN           #country=india
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="WIFI-NAME"
    psk="PASSWORD_wifi"
}
#code ends

#if you want to connect more than two wifis to your raspberripi
#code starts
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=IN
network={
   ssid="WIFI-NAME3"
    psk="PASSWORD_wifi3"
    priority=3              #highest_priority
}
network={
   ssid="WIFI-NAME2"
    psk="PASSWORD_wifi2"
   priority=2
}
network={
   ssid="WIFI-NAME1"
    psk="PASSWORD_wifi1"
   priority=1               #lowest_priority
}
$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
##########################################################################
TASK:CONNECTING Our raspberry pi to INTERNET:
SUCCESSFUL
reference:
https://www.youtube.com/watch?v=_OPwRC8EmB0
#########################################################################


