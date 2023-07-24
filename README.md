# MultiSensor project for Home Automation projects
The goal of projects is to build a cheap multipurpose sensor for home automation systems to detect various environmental parameters as well the presence of persons. 
The project is based around a breadboard with varions female headers to plug the sensors in. The automation is based around an ESP8266 (Wemos D1 mini). Power is supplied via the USB port on the Wemos and feeds all the sensors.
The breadboard will hold two more locations for additional I2C sensors (pin order = 3V3, GND, SCL, SDA) as well a header that exposes the free pins on the Wemos plus 3V3, 5V and GND for additional personal additions.
The back of the breadboard will hold a QR code leading to this GitHub Repository.
## The Breadboard
- 4 headers (4pin) for I2C devices (BME280, GY1145 and 2 spare slots)
- 1 header (3pin) for the PIR sensor (HC-SR505 or AM312)
- 1 header (5pin 1.27 mm spacing) for the 24GHz sensor (HLK-LD2410)
- 1 header (10pin) to expose all the residual ports A0, D0, D3, D4, D7 & D8 on the Wemos plus 5V, 3V3 and GND
- 1 jumper (2pin) to turn on or off the TX signal from the 24GHz sensor
- 1 optional capacitor [100-100µF]
- 1 Header (3pin) for the addition of WS2812 Neo-Pixel strip to locally indicate sensor status
- 1 resitor [220-470Ω] to protect the Neo-Pixel input signal
![The breadboard](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/Breadboard/Breadboardsmall.PNG)

# The following sensors are intended to be added:
## BME-280
This sensors gives the following information:
- Temperature [°C] [Range -40°C...85°C]
- Humidity [%] [Range 0-100% +/- 3%]
- Air pressure [hPa] [300...1100 hPa]
- [Further details for the Bosch BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/)
  
![BME280](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/BME280/BME280.PNG "BME280")
## IS-1145
This sensors gives the following information:
- Illuminance [lux]
- Infrared [lux]
- UV Index
- [Further details for the Si1145](https://www.silabs.com/documents/public/data-sheets/Si1145-46-47.pdf)
  
![GY1145 or SI1145](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/GY1145/GY1145small.PNG "GY1145 or SI1145")

## HC-SR505 or AM312
- Presence / non-presence digital signal
- 

![HC-SR505](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/PIR/HC-SR505.PNG "HC-SR505")
![AM312](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/PIR/AM312.PNG "AM312")
## HLK-LD2410
A 24GHz presence sensor that is configurable via Bluetooth and give both a digital signal as well serial information on the activity in the room
- Presence / non-presence digital signal
- Serial port information giving more detail information about movement in the room
- [Further details for the HLK-LD2410](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/mmWave/HLK-LD2410/HLK-LD2410.user.manual.V1.02%20(1).pdf)

![HLK-LD2410 Sensor](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/mmWave/HLK-LD2410/HLK-LD2410small1.PNG "HLK-LD2410 top")
![HLK-LD2410 Sensor](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/mmWave/HLK-LD2410/HLK-LD2410small2.PNG "HLK-LD2410 bottom")

