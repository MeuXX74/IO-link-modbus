# IO-Link Sensors and the Industrial IoT Starter Kit

## Introduction

This tutorial will help you connecting the IO-Link master and sensors included in the **Cisco Avnet IoT Kit**, pulling data via Modbus and publishing via MQTT onto the relayr Cloud (using a Vertex-enabled gateway, or directly to the relayr Cloud).

`http://www.io-link.com/en/Technology/what_is_IO-Link.php`


## Requirements

The following hardware is required:

* [AY1020](http://www.ifm.com/products/gb/ds/AY1020.htm) (IO-Link Master)﻿
* [KQ5100](http://www.ifm.com/products/gb/ds/KQ5100.htm) (Capacitive Sensor)
* [UGT509](http://www.ifm.com/products/gb/ds/UGT509.htm) (Ultrasonic Sensor)
* [TA2105](http://www.ifm.com/products/gb/ds/TA2105.htm) (Temperature Sensor)
* 2x [EVC001](http://www.ifm.com/products/gb/ds/EVC001.htm) (Cables with M12 Connector)
* 24V Power Supply (this setup has been implemented using a [Siemens SITOP PSU100S 6EP1334-2BA20](https://mall.industry.siemens.com/mall/en/ww/Catalog/Product/6EP1334-2BA20))
* Power Cord
* Assorted Wires for 24V Supply

A computer is required to access the web server configuration menu of the IO-Link Master and to publish the Modbus data of the sensors onto the relayr Cloud.

## Installation & Configuration

### Setting Up the Hardware

**IMPORTANT:** Only qualified personnel are allowed to install the device/system and set it into operation.

Before getting started, we will have to provide power to the IO-Link Master. Most regulated 24V power supplies come without a power cord, so we will have to attach such cable first. The picture below shows how to connect an ungrounded power cord to the input wire clamps (AC 120/230V, 50/60Hz), according to the following setup:

```
POWER CORD   |   POWER SUPPLY
     Brown ----- N (Neutral)
      Blue ----- L1 (Line)
```

The other end of the power cord **MUST BE DISCONNECTED** from the mains outlet!

![](./assets/psu_mains.jpg)

For safety reasons, **DO NOT CONNECT** the power supply to the mains outlet yet.

Now, in order to provide power to the IO-Link Master, we will wire this to the 24V DC output of the power supply. In this case, a red wire was used to connect the positive clamps, and a black wire for the negative ones. 

```
 POWER SUPPLY   |   IO-LINK MASTER
V+ or OUTPUT+ ----- V+ (Red Wire)
V- or OUTPUT- ----- V- (Black Wire)
```

On the side of the regulated power supply, it should look like this:

![](./assets/psu_output.jpg)

And on the side of the IO-Link Master, like this:

![](./assets/master_power_input.jpg)

**NOTE:** For advanced settings and more detailed descriptions, please refer to the [AY1020 IO-Link Master user's manual](https://www.ifm.com/download/files/AY1020_Manual_UK/$file/AY1020_Manual_UK.pdf).

The **UGT509 (ultrasonic sensor)** will be connected to the IO-Link Master using an **EVC001 cable**, which is included in the kit. First, connect the ultrasonic sensor to the mentioned cable, and secure the nut gently.
 
In this documentation, this sensor will be connected to Port 7 of the IO-Link Master, but another port can be used if necessary. The EVC001 cable has 4x wires, each one connected to one of the pins of the sensor: Brown (1), white (2), blue (3) and black (4). These wires have to be connected to the IO-Link Master, as shown below:

```
    SENSOR   |   PORT 7
     Brown ----- Pin 1
      Blue ----- Pin 2
     White ----- NC (Not Connected)
     Black ----- Pin 4
```

Now, let's do the same with the **TA2105 (temperature sensor)**. This part will be wired to the IO-Link Master using a **cable of the same type, an EVC001**. Attach the cable to the sensor to proceed.

We'll be connecting this sensor to Port 3 of the IO-Link Master, but as happens with the ultrasonic sensor, this is up to the user. The wires of the EVC001 cable have to be connected to the IO-Link Master as follows:

```
    SENSOR   |   PORT 3
     Brown ----- Pin 1
      Blue ----- Pin 2
     White ----- NC (Not Connected)
     Black ----- Pin 4
```

The last sensor on the list is the **KQ5100 (capacitive sensor)**. It comes with its own cable already, and there's no need to attach an additional cable.

This sensor will be connected to Port 4 of the IO-Link Master, but again, it can be hooked to a different port if required. The wires of this sensor follow the the same color code as in the EVC001 cable, so the pin allocation is easy to guess:

```
    SENSOR   |   PORT 4
     Brown ----- Pin 1
      Blue ----- Pin 2
     White ----- NC (Not Connected)
     Black ----- Pin 4
```

The last step is to connect the IO-Link Master to the computer (or to the local network) via Ethernet in order to run the configuration tool, verify that the sensors are working properly, and start reading data via Modbus, so it can be published onto the relayr Cloud.

First, connect an Ethernet cable to one of the ports marked as "10/100 Network" 

# ------ [ TBC ] ------

![](./assets/master_ethernet.jpg)

### Setting Up the Software

Once we are done with the hardware, the next step is configuring the IO-Link Master. First, connect the AY1020 to your computer using an Ethernet cable. If your computer doesn't have an Ethernet port, you may use an Ethernet-to-USB converter, Open a browser and introduce 

A 192.168.2.5

## Testing

* Install Node-RED
* Install Modbus TCP for Node-RED:  
npm install node-red-contrib-modbustcp
* Run Node-RED, and paste the JSON

## License

Copyright (C) 2016 relayr GmbH, Klemen Lilija <klemen@relayr.io>, Brian Lemke
<brian@relayr.io>, Antonio Almeida <antonio@relayr.io>, Jaime González-Arintero <jaime@relayr.io>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

Except as contained in this notice, the name(s) of the above copyright holders
shall not be used in advertising or otherwise to promote the sale, use or
other dealings in this Software without prior written authorization.

THE SOFTWARE IS PROVIDED "AS IS," WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
