# MultiSensor project for Home Automation projects
The goal of projects is to build a cost effective multipurpose sensor board for home automation systems to detect various environmental parameters and presence of persons as well give local feedback about the status for the various sensors via Neo-Pixels. 
The project is based around a breadboard with varions female headers to plug the sensors in. The automation is based around an ESP8266 (Wemos D1 mini). Power is supplied via the USB port on the Wemos and feeds all the sensors and Neo-Pixels alternatively 5volt can be supplied via a dedicated terminal.
The intent is to have 2 sensors using I2C headers with an option to add 2 more I2C sensors (pin order = 3V3, GND, SCL, SDA). The 10-pin female header  exposes the free pins on the Wemos plus 3V3, 5V and GND for personal additions.
The back of the breadboard will hold a QR code leading to this GitHub Repository. [Click here for detailed installation and PCB building instruction](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/HowToInstallTheMultiSensor.pdf). 
## The Breadboard
- 4 headers (4-pin female) for I2C devices (BME280, GY1145 and 2 spare slots)
- 1 header (3-pin female) for the PIR sensor (HC-SR505 or AM312)
- 1 header (5-pin female 1.27 mm spacing) for the 24GHz sensor (HLK-LD2410)
- 1 header (3-pin female) for a microwave motion sensor (RCWL-0516) (The HLK-LD2410 & the RCWL-0516 share the same space and only one can be placed)
- 1 header (10-pin female) to expose all the residual ports A0, D0, D3, D4, D7 & D8 on the Wemos plus 5V, 3V3 and GND
- 2 jumpers (2-pin male) to turn on or off the TX & RX signal from the 24GHz sensor
- 1 optional capacitor [100-1000µF]
- 1 Header (3-pin female) for the addition of WS2812 Neo-Pixel strip to locally indicate sensor status
- 1 resistor [220-470Ω] to protect the Neo-Pixel input signal
![The breadboard](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/Breadboard/Breadboard-V2%20small.PNG)
![Breadboard with units](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/Breadboard/complete-v2.jpg)

# The following sensors are intended to be added:
## BME-280
This sensors gives the following information:
- Temperature [°C] [Range -40°C...85°C]
- Humidity [%] [Range 0-100% +/- 3%]
- Air pressure [hPa] [300...1100 hPa]
- [Further details for the Bosch BME280](https://www.bosch-sensortec.com/products/environmental-sensors/humidity-sensors-bme280/)
  
![BME280](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/BME280/BME280.PNG "BME280")
## IS-1145 (replaced by GY-302 due to availability/price reasons)
This sensor gives the following information:
- Illuminance [lux]
- Infrared [lux]
- UV Index
- [Further details for the Si1145](https://www.silabs.com/documents/public/data-sheets/Si1145-46-47.pdf)  
![GY1145 or SI1145](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/GY1145/GY1145small.PNG "GY1145 or SI1145")  

## GY-302 (or HB1750)
This sensor gives the following information:
- Illuminance [lux]  
![GY-302](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/GY302/GY302.PNG)  


## HC-SR505 or AM312
- Presence / non-presence digital signal

![HC-SR505](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/PIR/HC-SR505.PNG "HC-SR505")
![AM312](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/PIR/AM312.PNG "AM312")
## HLK-LD2410
A 24GHz presence sensor that is configurable via Bluetooth and give both a digital signal as well serial information on the activity in the room
- Presence / non-presence digital signal
- Serial port information giving more detail information about movement in the room
- [Further details for the HLK-LD2410](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/mmWave/HLK-LD2410/HLK-LD2410.user.manual.V1.02%20(1).pdf)

![HLK-LD2410 Sensor](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/mmWave/HLK-LD2410/HLK-LD2410small1.PNG "HLK-LD2410 top")
![HLK-LD2410 Sensor](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/mmWave/HLK-LD2410/HLK-LD2410small2.PNG "HLK-LD2410 bottom")

## RCWL-0516
The RCWL-0516 is an active sensor, not a passive one like the HC-SR505 Passive Infrared (PIR). It sends out microwaves at a frequency of about 3.18 GHz and measures the radiation that is reflected back. The sensor has a 360-degree detection area without blind spots. The detection distance is about 5-7 meters.
[More information on this sensor can be found here](https://lastminuteengineers.com/rcwl0516-microwave-radar-motion-sensor-arduino-tutorial/)  
![RCWL-0516 Sensor](https://github.com/Roukie686868/MultiSensor/blob/main/Documents/RCWL-0516/RCWL-0516.PNG "RCWL-0516")

##Tasmota setting
- Decouple the digital input from any attached output like the Neo-Pixels with the ```SetOption114 1``` command from the console.
- If the switches are not seen by Home Assistant right away go to the Tasmota console and toggle the Setoption19 to 1 and back. ```SetOption19 1``` and ```SetOption19 0```
