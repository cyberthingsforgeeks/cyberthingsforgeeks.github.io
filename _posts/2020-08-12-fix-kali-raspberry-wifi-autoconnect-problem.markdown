---
layout: post
title:  "How to fix Kali Raspberry Pi 0W WiFi boot autoconnect problem"
date:   2020-08-12 15:00:00
categories: stuff
---

You continue to boot and you have to manually connect to your wifi, right? You already configured the autoconnect and autologin but it still doesn't work? Here is the fix.

To fix this annoying problem, you just need to add one line in file /etc/network/interfaces.

Line to add:
allow-hotplug wlan0






My interfaces file:

auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

allow-hotplug usb0
iface usb0 inet dhcp

auto wlan0
allow-hotplug wlan0
iface wlan0 inet dhcp
wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf




Hope this helps :)
