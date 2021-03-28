# Installing MySQL Database on Raspberry Pi
These instructions show how to fully install MySQL on the Raspberry Pi:

* Installations
* Adding User

## Installations
The following will be installed:
* MariaDB
* MySQL Connector for Python3

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

### Changing Bind-Adress
In order to access the MySQL server from other computers, the bind address must be changed from ``127.0.0.0`` to ``0.0.0.0``. The address is changed in the ``50-server.cnf`` file. The file will open in the terminal.
```
sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
```
After the change, the file must be saved.

## Adding User for MariaDB
In order to work with MySQL, a user with a password is assigned. To do this, you first have to log into the database in the terminal. The ``-u`` command stands for user.
```
sudo mysql -u
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