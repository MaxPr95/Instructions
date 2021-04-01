# Networkmanager for Eduroam on a Raspberry Pi
In order to use networks like Eduroam on the Raspberry Pi, a network manager must be installed. Each step is explained below.

## Install packages

### Updates & Upgradex
```
sudo apt-get update
sudo apt-get upgrade
```
### Installing the network-manager
```
sudo apt install network-manager network-manager-gnome
````

## Ignore wlan0
Check ``/etc/network/interfaces``. This should be empty except for an include from ``/etc/network/interfaces.d``.

Edit ``dhcpcd.conf``.
```
sudo nano /etc/dhcpcd.conf
```
Add line and save the document:
```
denyinterfaces wlan0
```

## Configure Network Manager to control wlan0 and assume dhcp duties
Edit ``NetworkManager.conf``
```
sudo nano /etc/NetworkManager/NetworkManager.conf
```
Insert the following:
```
[main]
plugins=ifupdown,keyfile
dhcp=internal

[ifupdown]
managed=true
```

## Restart
```
sudo reboot
```

## Installing the eduroam profile
Download your eduroam profile from https://cat.eduroam.org/ and run the python file.
```
python name-eduroam-profile.py
```
A GUI then appears. All information must be confirmed there and the login data must be entered.

## Connecting to the Ethernet/Eduroam
Finally, the WLAN network can be selected using the new network symbol in the menu bar. Connect to the desired network there.
