Created by Jeremy Brown and Nikolaos Stroubos

This repository is a hacky proof of concept using MQTT to publish and read messages and cross reference a whitelist to either approve or reject a rfid card swipe. The idea is there is 1 to n devices connected to a reader or readers, and there is one central device that stores the list of approved users. It's a pretty basic implementation but I intend to do a more advanced/professional version of it as I learn and develop my skills!

### Python Modules Used:
paho.mqtt.client as mqtt
mfrc522
numpy as np
pandas as pd
time
RPi.GPIO as GPIO
os
datetime
threading

### sshfs commands:

sshfs:

    sshfs user@hostname.local: directory

unmount:

    sudo umount directory

or:

    sudo diskutil umount force directory

### mqtt server:

eclipse-mqtt server startup command:

    docker run -i -p 1883:1883 -p 9001:9001 -v /home/pi/docker/mosquitto.conf:/mosquitto/config/mosquitto.conf -v /mosquitto/data -v /mosquitto/log eclipse-mosquitto

### raspi system log check:

syslog:

    cat /var/log/syslog | grep foo

Running in `/etc/rc.local`:
 - docker eclipse-mqtt server
 - python scripts

### Misc:

    ps aux | grep python

#### Updates:
- `12-1-20`: Adding detection of unlock from a keypad (GPIO High->Low trigger)