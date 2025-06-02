xbps-src
====================
xbps-src used to build and install packages from source which is not in offical repo.

download template of the packages
    git clone --depth=1 https://github.com/void-linux/void-packages
    cd void-packages

Install build tools 
    ./xbps-src binary-bootstrap

NOTE: Build tools doesn't installed system-wide. The eviroment is chroot like env.

Build packages
    sudo xbps-src pkg <pkg_name>

Install package
    sudo xbps-install -R hostdir/binpkgs <only_package_name>


Services
========
List of all services
    ls /etc/sv

List of enabled services 
    ls /var/service/

Enable a service
    ln -s /etc/sv/<service_name> /var/service/

Remove(disable) a service
    sudo rm /var/service/<service-name>

Delete some ttys
    sudo rm /var/service/agetty-tty[3-6]

Service status
    sudo sv status <service-name>

Sound
=====
Record voice
    arecord -d 5 -f cd test.wav
    aplay test.wav


Package Management
==================

xbps-query
----------
Query list
    sudo xbps-query -l

Package deps
------------
what are the dependecies of the <pkg-name>
    sudo xbps-query -x <pkg-name>`

Packages require the package
----------------------------
what packages are depend on <pkg-name>
    sudo xbps-query -X <pkg-name>

Package Deps on void repo
--------------------------
    sudo xbps-query -Rx <pkg-name>

Doas instead of sudo
--------------------
install doas
sudo xbps-install doas

Config doas
-------------
    nvim /etc/doas.conf

add this to doas.conf
    permit persist :wheel

Force to remove sudo
    sudo xbps-remove -F sudo

Recommended way to delete sudo
    sudo touch 00-xbps-settings.conf
    nvim /etc/xbps.d/00-xbps-settings.con

Add this line to the file
    ignorepkg=sudo

Then remove sudo
    sudo xbps-remove sudo



Connect to wifi network
-----------------------
Check avaiable wifi interface : like wlp9s0
    ip link

Scan for Wi-Fi Networks
    sudo iw dev wlp9s0 scan | grep "SSID:"

Generate a wpa_supplicant config
    sudo nvim /etc/wpa_supplicant/wpa_supplicant.conf

Add 
    network={
        ssid="Your-WiFi-Name"
        psk="Your-WiFi-Password"
    }

Connect
    sudo wpa_supplicant -B -i wlp9s0 -c /etc/wpa_supplicant/wpa_supplicant.conf

Get an ip address
    sudo dhcpcd wlp9s0

Connect a network with no password
    sudo iw dev wlp9s0 connect "xiom"

Check device ip address
    ip addr show <device-interface>  # wlp9s0

Check for connect wifi SSID
    iw dev wlp9s0 link


Prevent overwrite /etc/resolv.conf
==================================
Method 1
    sudo vim /etc/dhcpcd
    nohook resolv.conf
    sudo sv restart dhcpcd

Method 2: Make resolv.conf immutable
    sudo chattr +i /etc/resolv.conf
