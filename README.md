# LCD-show

# How to install 3.5in screen:

curl -o- https://raw.githubusercontent.com/Alicetech/rpi-lcd-show-improved/main/install | sudo bash /dev/stdin tft35a

# How to install 3.5in screen to SD card (before/after first boot):
curl -o- https://raw.githubusercontent.com/Alicetech/rpi-lcd-show-improved/main/install | path_root=/media/owner/rootfs path_root_boot=/media/owner/boot bash /dev/stdin tft35a

# How to run tests before bug report

curl -o- https://raw.githubusercontent.com/Alicetech/rpi-lcd-show-improved/main/units/run | bash
