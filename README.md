# PiHeadUnit

## Screen Rotation

### /boot/cmdline.txt

```
video=HDMI-A-1:1024x800M@60,margin_right=0,margin_left=0,margin_top=0,margin_bottom=0,rotate=180
```

### /usr/share/X11/xorg.conf.d/40-libinput.conf

Add the `TransformationMatrix` option.
```
Section "InputClass"
        Identifier "libinput touchscreen catchall"
        MatchIsTouchscreen "on"
        Option "TransformationMatrix" "-1 0 1 0 -1 1 0 0 1" 
        MatchDevicePath "/dev/input/event*"
        Driver "libinput"
EndSection
```

## TP-Link Nano Driver

### https://github.com/brektrou/rtl8821CU.git

## CAN Bus Shield

### Install libraries

```
tar zxvf bcm2835-1.60.tar.gz
cd bcm2835-1.60
sudo ./configure
sudo make
sudo make check
sudo make install
```