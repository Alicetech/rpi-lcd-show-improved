# Raspberry Pi improved pin connector LCD install

This is a more stable design of the install scripts.  This project allows first boot access. After you install your Pi image to SD or USB you can also install the driver without even booting you pi!

# The original repo has these issues
The original LCD-show (https://github.com/goodtft/LCD-show) has too many issues:
* You must have HDMI, TV or SSH. You must have network access. You cant use you screen, on first boot...
* Bricks new USB boot methods on Pi4
* Bricks Berryboot (if you can't boot then you can't restore)
* Forced reboot without warning! (Reboot your own device to stop lost work in progress)
* Hijacks/delets your inittab
* Hijacks/delets your config.txt
* Hijacks/delets your cmdline.txt
* Messes up your APT depends...
* Intsalls X11 in Rasbian Light (The distro that is console only... And people want it that way... Also touch screen shoud work as mouse since console support mice..)

# This projects is in progress. Production usage is planed by Alicetech. This is supported and WIP:
- [x] Base raspbian works with console
- [ ] Test units show pass/fail
- [ ] Test units with physical camera and QR code on screen. 
- [ ] Test units with physical network SD with snaphots with a second system power cycler. VM wont work since we need pins.
- [ ] Test units with more physical screens (This project is open source and we need donations)
- [ ] Base raspbian works with X11
- [ ] Berryboot works (post boot)
- [ ] Touch works in console
- [ ] Touch works in X11
- [ ] Kernal driver imbeded for full boot including Berryboot
- [ ] Install script to system bin for root with rotate option
- [ ] Multi screen support for VR
- [ ] Add support for and test bcm2709-rpi-2-b bcm2710-rpi-3-b qddpi24.dtb

# How to install 3.5in screen:
```
curl -o- https://raw.githubusercontent.com/Alicetech/rpi-lcd-show-improved/main/install | sudo bash /dev/stdin tft35a
```
You can change "tft35a" to one of the following: mhs24, mhs32, mhs35, mhs35b, mhs395, mis35, tft35a, tft9341

# How to install 3.5in screen to SD card (before/after first boot using debian/ubuntu host):
```
curl -o- https://raw.githubusercontent.com/Alicetech/rpi-lcd-show-improved/main/install | path_root=/media/owner/rootfs path_root_boot=/media/owner/boot bash /dev/stdin tft35a
```

# How to run tests before bug report
```
curl -o- https://raw.githubusercontent.com/Alicetech/rpi-lcd-show-improved/main/units/run | bash
```
