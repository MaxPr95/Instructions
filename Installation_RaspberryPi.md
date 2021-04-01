# SCOES - Raspberry Pi installation

* Link zum Download vom Image
* RFID-Reader verbinden (Bild)
* installation: update, RFID-Reader, Datenbank, MySQL-Connector, MQTT

## Update & Upgrade
```
sudo apt-get update
sudo apt-get upgrade
```

## Installation

### Installing RFID MFRC522
```
sudo pip3 install mfrc522
```
Enable SPI in the Raspberry Pi configuration ``raspi-config``. Then select ``Interface Options`` - ``P4 SPI`` - ``enable``. A restart is then required.
```
sudo raspi-config
```
Reboot Raspberry Pi
```
sudo reboot
```

### Installing MariaDB
Download and install MariaDB
```
sudo apt install mariadb-server
```

### Installing MySQL Connector
Download and install MySQL-Connector for Python
```
sudo pip3 install mysql-connector-python
```

### Installing MQTT
```
sudo pip3 install paho-mqtt
```

### Bind-Adress
In order to access the MySQL server from other computers, the bind address must be changed from ``127.0.0.0`` to ``0.0.0.0``. The address is changed in the ``50-server.cnf`` file. The file will open in the terminal.
```
sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
```
After the change, the file must be saved.

## Adding user for MariaDB
In order to work with MySQL, a user with a password is assigned. To do this, you first have to log into the database in the terminal. The ``-u`` command stands for user.
```
sudo mysql -u root
```

```mysql
create user ‚pi‘@‚%‘ identified by ‚pi’;
```
```mysql
grant all privileges on *.* to ‚pi‘@‚%‘ with grant option;
```

```mysql
flush privileges;
```

