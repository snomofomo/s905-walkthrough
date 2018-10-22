# s905-walkthrough
Walk through for install Arch Linux on s905

Information and files:  https://github.com/150balbes/Amlogic_s905/wiki/s905_LInux_SD_USB

Direct Download for Arch File: https://yadi.sk/d/5_32km_EsCV2A/ArchLinux

    S905X_5912_ArchLinux_20170519_4_9_26.img.xz (at the time of writing)

- Burn the image and make the non-BOOT partition as big as possible  (https://gparted.org/liveusb.php)

- insert sd card and boot the linux box

### default login

root:

### Change root password

  `passwd`

### Connect to internet
_ensure the device is plugged in to ethernet_

`ip addr`

If you see an address similar to 192.168.*.* you are connected to your network.  If not, see: https://wiki.archlinux.org/index.php/Network_configuration



### Configure Date/Time  
_(change zoneinfo/Region/City to match your own)_

  `ln -sf /usr/share/zoneinfo/America/New_York /etc/localtime`

  `hwclock --systohc`

  `timedatectl set-ntp true`
  
  _confirm with `date`_
  
### Update OS and Install Deps

`pacman -Syu`

`pacman -S base-devel mongodb wget sudo`

### Create User and Configure for sudo

