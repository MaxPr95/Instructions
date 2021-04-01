# RFID MFRC522 on Raspberry Pi

Installation of the RFID-Reader MFRC522 on a Raspberry Pi and creating a Read.py and Write.py file.

## Update and Upgrafde
First, an update and upgrade must be carried out on the Raspberry Pi.
```
sudo apt-get update
sudo apt-get upgrade -y
```

## Installation of MFRC522
Installing the Module MFRC522
```
sudo pip3 install mfrc522
```

## Enabling SPI
Enable SPI in the Raspberry Pi configuration ``raspi-config``. Then select ``Interface Options`` - ``P4 SPI`` - ``enable``. A restart is then required.
```
sudo raspi-config
```

# Read.py
The following program can be used to read an RFID tag. To do this, create a Python file with the name Read.py
```
#!/usr/bin/env python
import RPi.GPIO as GPIO
from mfrc522 import SimpleMFRC522
reader = SimpleMFRC522()

try:
    print("Wait for Input")
    id, text = reader.read()
    print(id)
    print(text)
finally:
    GPIO.cleanup()
```

#Write.py
The following program can be used to write an RFID tag. To do this, create a Python file with the name Read.py.
#!/usr/bin/env python
import RPi.GPIO as GPIO
from mfrc522 import SimpleMFRC522
reader = SimpleMFRC522()
```
try:
    text = input('New data:')
    print("Now place your tag to write")
    reader.write(text)
    print("written")
finally:
    GPIO.cleanup()
```
