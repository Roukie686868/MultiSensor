# MultiSensor project for Home Automation projects
The goal of projects is to build a cheap multipurpose sensor for home automation systems to detect various environmental paramaters as well the presence of persons. 
The project is based around a breadboard with varions female headers to plug the sensors in. The automation is based around an ESP8266 (Wemos D1 mini). Power is supplied via the USB port on the Wemos and feeds all the sensors.
The breadboard will hold two more locations for additional I2C sensors (pin order = 3V3, GND, SCL, SDA) as well a header that exposes the free pins on the Wemos plus 3V3, 5V and GND for additional personal additions.
The back of the breadboard will hold a QR code leading to this GitHub Repository.
## The Breadboard
![The breadboard](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/Breadboard/Breadboardsmall.PNG)

# The following sensors are intended to be added:
## BME-280
This sensors gives the following infromation:
- Temperature [°C]
- Humidity [%]
- Air pressure [hPa]
  
![BME280](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/BME280/BME280.PNG "BME280")
## IS-1145
This sensors gives the following infromation:
- Illuminance [lux]
- Infrared [lux]
- UV Index

![GY1145 or SI1145](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/GY1145/GY1145small.PNG "GY1145 or SI1145")
## HC-SR505 or AM312
- Presence / non-presence digital signal

![HC-SR505](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/PIR/HC-SR505.PNG "HC-SR505")
![AM312](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/PIR/AM312.PNG "AM312")
## HLK-LD2410
A 24gHz presence sensor that is configurable via BlueTooth and give both a digital signal as well serial information on the activity in the room
- Presence / non-presence digital signal
- Serial port information giving more detail information about movement in the room
![HLK-LD2410 Sensor](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/mmWave/HLK-LD2410/HLK-LD2410small1.PNG "HLK-LD2410 top")
![HLK-LD2410 Sensor](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/mmWave/HLK-LD2410/HLK-LD2410small2.PNG "HLK-LD2410 bottom")

