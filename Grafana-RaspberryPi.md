# Installing Grafana
These instructions show how to fully install Grafana on the Raspberry Pi and how to get started.

## Update Raspberry Pi
First, an update and upgrade must be carried out on the Raspberry Pi.

```
sudo apt update
```
```
sudo apt upgrade -y
```

## Installing Grafana
Please always download the latest version from the manufacturer: [Grafana.com](https://grafana.com/grafana/download?pg=get&plcmt=selfmanaged-box1-cta1&platform=arm). It should be noted that it is the ``ARM`` version that is optimized for Raspberry Pi. This can also be recognized by the file name included with ``grafana-rpi``.

```
sudo apt-get install -y adduser libfontconfig1
wget https://dl.grafana.com/oss/release/grafana-rpi_7.5.1_armhf.deb
sudo dpkg -i grafana-rpi_7.5.1_armhf.deb
```

After the installation you will be asked to carry out further commands. These can also be taken directly from the terminal.
```
Sudo-Befehle aufschreiben.
```

## Get Started

### Access Grafana
Open a browser tab and go to the IP address with port 3000 to log in.

```
localhost:3000
```

### Login
Username and password are identical and are called ``admin``.