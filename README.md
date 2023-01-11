# linkit7688_3.18.109.img
For USB rescue  
救磚  

## Caution , copy lks7688.img to a clean usb disk with FAT32 format.

![pic](pic/demo.jpg)<br><br><br>

Press WiFi key and power on linkit7688  
![pic](pic/demo1.png)<br><br><br>


After 10 sec and release WiFi ky, linkit7688 finds the USB disk, file, and update itself.
![pic](pic/demo2.png)<br><br><br>

Conneting type 2  
![pic](pic/demo7.jpg)<br><br><br>

Conneting type 3  
![pic](pic/demo8.jpg)<br><br><br>


# 3.18.23 image, update by mtd
This image seems be factory image for Linkit 7688 / 7688 Duo.  

This version is fully supportted by opkg, https://archive.openwrt.org/chaos_calmer/15.05.1/ramips/mt7688/.  

But, this image only supports update by mtd and does not support by USB.  

I don't know why, also.  

copy the lks7688.img to USB disk.   

Boot linkut7688 to linux  

Update by :  

## mtd -r write /tmp/run/mounted/sd1/lks7688.img firmware  

Thus, if you want use this image, you maybe need to update 3.18.109 by USB or you board is ok for booting to  linux,  

then update this image by command of mtd.  
