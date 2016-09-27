# ifm electronic IO-Link Sensors
## Introduction

The

## Requirements

The following hardware is required:

* [AY1020](http://www.ifm.com/products/us/ds/AY1020.htm) (IO-Link Master)﻿
* [KQ5100](http://www.ifm.com/products/uk/ds/KQ5100.htm) (Capacitive Sensor)
* [UGT509](http://www.ifm.com/products/gb/ds/UGT509.htm) (Ultrasonic Sensor)

Open a browser and introduce 

A 192.168.2.5

## Installation & Configuration

### Setting Up the Hardware

**NOTE:** For advanced settings and more detailed descriptions, please refer to the [AY1020 IO-Link Master user's manual](https://www.ifm.com/download/files/AY1020_Manual_UK/$file/AY1020_Manual_UK.pdf).

The UGT509 (Vibration sensor) will be connected to the IO-Link Master using an EVT402 cable, which is included in the kit. In this documentation, this sensor will be connected to Port 7 of the IO-Link Master, but another port can be used if necessary. The EVT402 has 4x wires, each one connected to one of the pins of the sensor: Brown (1), white (2), blue (3) and black (4). These wires have to be connected to the IO-Link Master, as shown below:

```
SENSOR  < >  PORT 7
 Brown ----- Pin 1
  Blue ----- Pin 2
 White ----- NC (Not Connected)
 Black ----- Pin 4

```

### Setting Up the Software

Once we are done with the hardware, the next step is configuring the IO-Link Master. Connect the AY1020 to your computer using a , Open a browser and introduce 

A 192.168.2.5

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
