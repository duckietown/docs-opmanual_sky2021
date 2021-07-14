# Part 2: IR Sensor Checkpoint {#build-part2-checkpoint status=ready}

**Expected Time**: 30 minutes

## Overview

You will now checks to see if the IR sensor on your drone is working properly. The first check will involve reading the raw IR sensor measurements using a multimeter. Then, you will using the drone software and the web interface to see drone's height estimate.

## Reading the IR sensor using a multimeter

### Power the Sensor

Plug the battery into your drone build

### Setup Multimeter

Set the multimeter to read voltage up to 2V

<figure>
  <figcaption>Multimeter in the correct setting</figcaption>
  <img style='width:220px' src="photos/multimeter-voltage.png"/>
</figure>

### Probe

1. Insert the black probe into any hole in the **GND** rail.

1. Insert the red probe into any hole that is on the same rail as the yellow IR wire, which is connected to A0 on the ADC

Note: The ADC shown in the image is from a previous hardware version. You will use the technique shown, but not necessarily the same probe placement.

<figure>
  <figcaption>Probing the IR sensor data wire</figcaption>
  <img style='width:220px' src="photos/multimeter-pihat.png"/>
</figure>

### Test

While holding the probes in place, point the IR sensor at an object and then move the sensor closer and further to that object within the range of 10-50cm away. Check that the value on the multimeter is getting smaller when the object is further, and larger when it is closer. If this is correct, then your IR sensor is working properly!

Note: if the measurement is taken closer than 10cm or further than 50cm, the sensor will not read properly. If you're interested in why, take a look at Fig. 5 in the [datasheet](https://www.sparkfun.com/datasheets/Components/GP2Y0A21YK.pdf).

## Reading the IR sensor on the web interface

### Connect to the drone

1. Plug the battery into your drone build and connect to the drone's wifi network. By default, the network is named, *defaultdrone*, and the password is *bigbubba*.

1. Browse to the drone's code editor: [http://192.168.42.1:8081](http://192.168.42.1:8081)

1. In a new tab, browse to the web interface: [http://192.168.42.1](http://192.168.42.1). The web interface is what you will use to fly the drone. It also contains graphs that show data from the sensors.


### Start up the code

1. In the code editor, click the menu bar in the top left corner, then click Terminal > New Terminal

1. Type `./start` and press enter

1. Go back to the web interface tab, wait about 5 seconds, and refresh the page. Make sure that you see "Connected" at the top of the page. If you do not see this, wait a few more seconds and try refreshing again.

### Test

1. locate the *Height Readings* chart on the web interface

1. Use your hand to move the IR sensor closer and further to an object and check that the Height Readings chart is changing



Congrats on finishing Build Part 2!
