# Kubernetes-Cluster

Quick and simple tutorial to create your Kubernetes-cluster out of Raspberry Pis.

![](https://github.com/JordiCorbilla/Kubernetes-Cluster/raw/master/IMG_20190216_164142.jpg)

## Material

- 4 x [Rpi 3 model B + 16Gb microSD Card bundle](https://www.modmypi.com/raspberry-pi/set-up-kits/rpi3-model-b-plus-kits/raspberry-pi-3-model-b-plus-and-16gb-microsd-bundle) = 4 x £42 = £168
- 4 x [USB to Micro USB Cable 0.5m](https://www.modmypi.com/raspberry-pi/accessories-198/usb-cables-211/usb-to-micro-usb-cable-0.5m) = 4 x £1.5 = £6
- 1 x [Raspberry Pi 3 B+ Case with Cooling Fan and Heatsink](https://www.amazon.co.uk/gp/product/B07J9VMNBL/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1) = 1 x £18.99 = £18.99
- 1 x [5 port desktop switch](https://www.amazon.co.uk/gp/product/B000FNFSPY/ref=oh_aui_detailpage_o01_s00?ie=UTF8&psc=1) = 1 x £11.99 = £11.99
- 5 x [Ethernet patch cable 0.3m](https://www.amazon.co.uk/5-Color-Meters-Ethernet-GearIt-Network/dp/B00X8EMOKE/ref=sr_1_9?s=computers&ie=UTF8&qid=1469877886&sr=1-9&keywords=ethernet+patch+cable) = 1 x £15.33 = £15.33
- 1 x [USB Hub](https://www.amazon.co.uk/Anker-4-Port-Ultra-Drives-Devices/dp/B00Y25XFGK/ref=sr_1_1?s=computers&ie=UTF8&qid=1551005210&sr=1-1&keywords=usb+hub) = 1 x £10.99 = £10.99

**Total cost: £231.3**

## Installation

### Nodes 1 to 4

- Burn [Raspbian Jesse Lite](https://downloads.raspberrypi.org/raspbian_lite/images/raspbian_lite-2018-11-15/) to each Raspberry Pi SD card. By the time of this tutorial, I used raspbian_lite-2018-11-15 which was the latest available. 

- To burn the images you can use [Win32 disk imager](https://sourceforge.net/projects/win32diskimager/) or [BalenaEtcher](https://www.balena.io/etcher/).

- I used my cool [SDXC/MicroSDXC USB adapter](https://www.modmypi.com/raspberry-pi/sd-cards-and-adaptors-232/sd-card-readers/kawau-c296-usb-sd-and-micro-sd-card-reader-512gb) to copy the images:
![](https://github.com/JordiCorbilla/Kubernetes-Cluster/raw/master/usbsdxc.jpg)

- Put the SD cards back into each pie and we'll start remoting onto them one by one to configure them.

- Configure Windows Subsystem for Linux (WSL)

Install first Ubuntu from the Microsoft App Store (only on Windows 10):

![](https://github.com/JordiCorbilla/Kubernetes-Cluster/raw/master/ubuntu.png)

once installed, you will have to enable this feature through "Turn On/Off Windows Features":

![](https://github.com/JordiCorbilla/Kubernetes-Cluster/raw/master/WSL.png)



