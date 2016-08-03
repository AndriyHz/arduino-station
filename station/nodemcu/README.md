ESP8266 Arduino Setup Instructions
==================================

## Hardware & Accessories to Prepare in Advance

- NodeMCU
- PM Sensor
    + Currently only tested with [PMS3003][PMS3003]
- Breadboard x 1

## Prepare Software Environment

Install [Arduino IDE][arduino-download] and follow this [installation guide][esp8266-install] to install ESP8266 dependencies in Arduino IDE.

Install [WifiManger][wifi-manager] through Arduino Library Manager.

## Step 1: Configure WiFi, `API_KEY`, `SENSOR_ID` and Flash Firmware

Open Arduino IDE, paste below code into the IDE:
https://github.com/sensor-web/arduino-station/blob/master/station/nodemcu/nodemcu.ino

Change the `SSID` and `PASS` to connect to your wifi. 

Change `API_KEY` and `SENSOR_ID` to those you get from [SensorWeb dashboard][sensorweb-profile].

Click the **Upload** button and wait until it's done.

## Step 2: Connect Sensor and Get it Running

Connect your PM Sensor to NodeMCU like this:

PM Sensor Pins| NodeMCU Pins
--- | ----
RXD | TXD
TXD | RXD
VCC | VIN
GND | GND

Finally, power on your USB TTL Adapter to make it work.

## Voilà!

Go back to [SensorWeb dashboard][sensorweb-profile] to see your live data.

[PMS3003]: https://goo.gl/CIVGjF
[arduino-download]: https://www.arduino.cc/en/Main/Software
[wifi-manager]: https://github.com/tzapu/WiFiManager#quick-start
[esp8266-install]: http://esp8266.github.io/Arduino/versions/2.1.0/doc/installing.html
[sensorweb-profile]: http://sensorweb.io/profile
