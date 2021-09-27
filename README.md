# My work with RaspberryPi4B

![rpi](https://user-images.githubusercontent.com/88953654/134862798-668056dc-7f84-4302-a6c4-d7bc866c43e5.png)

## First Step:Making Raspberry HEADLESS (SETUP)
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

#### TASK_1:Upload Rasberry OS on SD card:SUCCESSFUL
*********************************************************************************************************************************************************************************
#### TASK_2:CONNECTING Our raspberry pi to INTERNET via Wi-Fi

##### 1)Create a <ssh> named file in boot drive of SD card

##### 2)Then, create another <wpa_supplicant.conf> in boot drive of sd card.

##### 3)Paste Following command into <wpa_supplicant.conf> file:

```
#code starts
country=IN           #country=india
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="WIFI-NAME"
    psk="PASSWORD_wifi"
}
#code ends
```

##### if you want to connect more than two wifis to your raspberripi
```
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
```
##### TASK_2:CONNECTING Our raspberry pi to INTERNET via Wi-Fi:SUCCESSFUL
*********************************************************************************************************************************************************************************
##### TASK_3:Installing VNC viewer to view desktop of raspberry

1)Now, remove SD card from your laptop, put it in your Raspberri pi

2)power the raspberri and wait for 4-5 minutes to connect it to Wifi.

3)Then, ssh via putty(SSH and TELNET(TELNET is unsecure preferablly use SSH) client) or you can also use windows PowerShell to ssh(
cmmnd:
```
ssh <user_name>@<yours_raspberry_ip_address or domain_name> i.e.,ssh pi@192.168.29.40)
```
download link for putty:
[https://www.putty.org/](url)

4)open putty

5)Host Name:raspberrypi.local Port:22  (if your host name not taken then, try to find ip of your raspberry from an app<"Advance ip scanner"> )(it will tell you
the ip addresses of connected devices from wifi)

6)Now, you are entered into putty SHELL which is ssh to raspberry:
login:pi
password:raspberry

7)use <ifconfig> cmd to get ip address of your raspberry

8)enter <sudo raspi-config> then you will enter into raspian configuration window

9)now we must enable VNC viewer(For Graphical user interface(GUI)):
Interface Options>VNC>ENTER
Enable the VNC viewer.

10)Now reboot Raspberri
System options>BOOT>DESKTOP

11)VNC Viewer:VNC viewer a graphical desktop sharing system that allows a user to remotely control the desktop of a remote computer (running VNC Server) from your device, 
and it transmits the keyboard and mouse or touch events to VNC Server, so that once you are connected, you have control over the computer you’ve accessed. 

12)If VNC unable to preview your screen, then try to set resolution of sceen:
-login into putty or ssh to raspberry
sudo raspi-config
Display optios>resolution><YOUR CHOICE OF RESOLUTION>

##### TASK_3:Installing VNC viewer to view desktop of raspberry:SUCCESSFUL
*********************************************************************************************************************************************************************************

#### EXTRA:Fitting raspi sceen to lapi screen
RASPIAN startup>preferences>Screen configuration
then, set the screen resolution(1280*720) and view(1:16) accordingly.
https://www.youtube.com/watch?v=I-vCFP2jD1g

#### Wi-fi freq problem:
https://www.youtube.com/watch?v=vsHxTVtlAZ0


