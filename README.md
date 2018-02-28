## Audiophonics IR Remote

## Audiophonics 9294 IR Remote tutorial

### 1/ Install Lirc
sudo apt-get -y install lirc

### 2/ Edit /etc/modules
```
sudo nano /etc/modules
```
Add :
```
lirc_dev
lirc_rpi gpio_in_pin=26
```

### 3/ Edit /boot/config.txt
```
sudo nano /boot/config.txt
```

Add at the begining :
```
dtoverlay=lirc-rpi,gpio_in_pin=26
```

### 4/ Pull config files :

```
cd /etc/lirc/
sudo mv hardware.conf hardware.sav
sudo mv lircd.conf lircd.sav
sudo mv lircrc.conf lircrc.sav
sudo wget https://raw.githubusercontent.com/audiophonics/Audiophonics_IR_Remote/master/hardware.conf
sudo wget https://raw.githubusercontent.com/audiophonics/Audiophonics_IR_Remote/master/lircd.conf
sudo wget https://raw.githubusercontent.com/audiophonics/Audiophonics_IR_Remote/master/lircrc
```

Reboot

```
sudo /etc/init.d/lirc stop
sudo /etc/init.d/lirc start
sudo /etc/init.d/lirc status
```
Check if result of status is OK

Buttons : 

VOL+/- : Volume 
CH+/- : 
Prev / Next 
MUTE : Mute 
DSP : Seek 10s 
SET : Play / Pause 
PWR : Shutdown
