# 3.18.23 image, update by USB
## For USB rescue  
base_image_0.94_3.18.23/lks7688.img  
dffa59d1650497662b7ea53ca41701bd  
This image seems be factory image for Linkit 7688 / 7688 Duo.  
This version is fully supportted by opkg, https://archive.openwrt.org/chaos_calmer/15.05.1/ramips/mt7688/.  
救磚   

## Caution  
### copy lks7688.img to a clean usb disk with FAT32 format.
### First boot, please wait 2minutes or run command of sync to wait all works is finished.

![pic](pic/demo.jpg)<br><br><br>
![pic](pic/demo9.jpg)<br><br><br>

Press WiFi key and power on linkit7688  
![pic](pic/demo1.png)<br><br><br>


After 10 sec and release WiFi ky, linkit7688 finds the USB disk, file, and update itself.
![pic](pic/demo2.png)<br><br><br>

Conneting type 2  
![pic](pic/demo7.jpg)<br><br><br>

Conneting type 3  
![pic](pic/demo8.jpg)<br><br><br>



# 3.18.23 image, update by mtd
mtd_update_3.18.23/LinkIt_Smart_7688_Firmware_v0.9.4.zip<br>
extract and copy the lks7688.img to USB disk.   

Boot linkut7688 to linux  

Update by :  

## mtd -r write /tmp/run/mounted/sd1/lks7688.img firmware  

Thus, if you want use this image, you maybe need to update 3.18.109 by USB or you board is ok for booting to  linux,  

then update this image by command of mtd.  

# linkit7688_3.18.109 image
usb_update_3.18.109/lks7688.img <br>
For USB rescue


# linkit7688duo MCU rescue
You can find Caterina-smart7688.hex at arduino for linkit7688duo:  
C:\Users\greatcat\AppData\Roaming\Arduino15\packages\LinkIt\hardware\avr\0.1.8\bootloaders\caterina  
<br>
copy Caterina-smart7688.hex to linkit7688duo by scp  
and run the command as below:  
avrdude -p m32u4 -c linuxgpio -v -e -U flash:w:Caterina-smart7688.hex -U lock:w:0x0f:m  

# example of uci
ONLY for owrt=15.x / k=3.18.x <br>
## sta mode
uci set dhcp.lan.ignore='0' &&\ <br>
uci set network.lan.proto='static' &&\ <br>
uci set wireless.radio0.linkit_mode='' &&\ <br>
uci set wireless.ap.ssid='xxxxxxxxx' &&\ <br>
uci set wireless.ap.key='xxxxxxxxx' &&\ <br>
uci set wireless.ap.encryption='' &&\ <br>
uci set wireless.sta.disable=0 &&\ <br>
uci set wireless.sta.network='wan' &&\ <br>
uci set wireless.sta.ssid=greatcat3 &&\ <br>
uci set wireless.sta.key=123456789 &&\ <br>
uci set wireless.sta.encryption=psk2 &&\ <br>
uci commit <br>
<br>
wifi_mode sta <br>
<br>
Mt7688 as ethernet bridge. Browser -> PC -> ethernet -> mt7688 -> WiFi -> phone <br>
![pic](pic/router_bridge_list.png)<br>
## ap mode
uci set dhcp.lan.ignore='0' &&\ <br>
uci set network.lan.proto='static' &&\ <br>
uci set wireless.radio0.linkit_mode='ap' &&\ <br>
uci set wireless.ap.ssid='LinkIt_Smart_7688_1C1497a' &&\ <br>
uci set wireless.ap.key='123456aaa' &&\ <br>
uci set wireless.ap.encryption='psk2' &&\ <br>
uci set wireless.sta.disable=1 &&\ <br>
uci set wireless.sta.network=''  &&\ <br>
uci set wireless.sta.ssid='xxxxxxxxx' &&\ <br>
uci set wireless.sta.key='xxxxxxxxx' &&\ <br>
uci set wireless.sta.encryption='psk2' &&\ <br>
uci commit<br>
<br>
wifi_mode ap<br>

## WiFi router mode
![pic](pic/wifi_router_structure.png)<br>
![pic](pic/wifi_router_structure_b.png)<br>
![pic](pic/wifi_router_a.png)<br>
![pic](pic/wifi_router_b.png)<br>
![pic](pic/wifi_router_c.png)<br>


If the document help you, how about buy street cats a fish can ?
