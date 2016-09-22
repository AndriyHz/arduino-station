# Particle Photon Station Setup Instructions

## Hardware & Accessories to Prepare in Advance

- Particle Photon
- PM Sensor
    + Currently only tested with [PMS3003][PMS3003]
- Breadboard x 1 (Optional)
- Jump wires

## Prepare Software Environment

Recommended way to setup your photon is via [Particle Mobile App][particle-app], you'll have to create a particle account in order to manage your particle boards.

If you prefer command line tools, you'll need to have [node.js][nodejs] and [particle-cli][particle-cli] installed on your computer.

## Step 1: Setup Your Photon

Follow the [quickstart instruction][photon-setup] on photon website to create an particle account, connect your photon to wifi, and claim it under your account.

## Step 2: Connect Sensors

Take the PM Sensor for example, connect it to your photon like this:

PM Sensor Pins| Photon Pins
---------- | ----------
VCC (PIN1) | VIN (5V+ when powered via USB) 
GND (PIN2) | GND
RXD (PIN4) | TXD
TXD (PIN5) | RXD

## Step 3: Configure `API_KEY` and `SENSOR_ID`

Go to https://build.particle.io, and create an new app `SENSORWEB-STATION`.

Click on **Libraries** button, and find `HTTPCLIENT` in **Community Libraries**

Get in `HTTPCLIENT` library detail, and click on **INCLUDE IN APP**.

Go back to the app you just created, and paste following code inside the ino file.

https://github.com/sensor-web/arduino-station/tree/master/station/particle-photon/particle-photon.ino

Change the `SENSOR_ID` and `API_KEY` to those you get from [SensorWeb][sensorweb].

## Step 4: Flash Firmware and Get it Running

Make sure your photon is connected and breathing cyan.

Click on **Devices** button in https://build.particle.io, and star the device you want to flash.

Click **Flash** button, if it's blinking purple, and reboot to breathing cyan after a while, it should be working properly.

## Step 3-4 Alternative: Flash with Command Line Tools

Login particle with your email and password if you haven't.
```
particle login
```

Make sure you `cd` into the `arduino-station/station/particle-photon` directory,
change the `SENSOR_ID` and `API_KEY` in `arduino-station/station/particle-photon/SensorWebCnfig.h`
and flash code with following command:
```
particle flash {your_photon_name} ./*
```

If it's blinking purple, and reboot to breathing cyan after a while, it should be working properly.

## Voilà!

Go back to [SensorWeb][sensorweb] to see your live data.

[PMS3003]: https://goo.gl/CIVGjF
[photon-setup]: https://docs.particle.io/guide/getting-started/start/photon/#step-1-power-on-your-device
[sensorweb]: https://sensorweb.io/pm25/
[nodejs]: https://nodejs.org/
[particle-cli]: https://github.com/spark/particle-cli
[particle-app]: https://docs.particle.io/guide/getting-started/start/photon/#prerequisites-for-setup
