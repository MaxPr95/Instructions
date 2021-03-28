# Installing MySQL Database on Raspberry Pi
These instructions show how to fully install MySQL on the Raspberry Pi for Python:

* Installation of MariaDB
* Add User
* Python Connection

## Installations
The following will be installed:
* MariaDB
* MySQL Connector for Python3

# Installing MariaDB
Download and install MariaDB
```
sudo apt install mariadb-server
```

# Installing MySQL Connector
Download and install MySQL-Connector for Python
```
sudo pip3 install mysql-connector-python
```

## Changing Bind-Adress
In order to access the MySQL server from other computers, the bind address must be changed from ``127.0.0.0`` to ``0.0.0.0``. The address is changed in the ``50-server.cnf`` file. The file will open in the terminal.
```
sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
```
After the change, the file must be saved.

