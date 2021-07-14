# Part 4 Checkpoint {#build-part4-checkpoint status=ready}

## Overview

You will now make sure the the camera is working properly by viewing the camera data on the web interface.

## Connect to the drone

### Connect to the WiFi

Plug the battery into your drone build and connect to the drone's wifi network, **defaultdrone**

### Open the web interface

Browse to the web interface: [http://192.168.42.1](http://192.168.42.1)

### Open the code editor

In a new tab, browse to the drone's code editor: [http://192.168.42.1:8081](http://192.168.42.1:8081)

## Start up the code

### Open a terminal

If there is not a terminal at the bottom of your screen already, then:

In the code editor, click the menu bar in the top left corner, then click Terminal > New Terminal

### Run the start command

Type this command and hit enter: `./start`

### Start the flight controller node

1. Identify the "tick" key on your keyboard. It looks like this: \`  and is typically the key to the left of the '1' key. It is also typically located on the same key as the tilde `~`.

1. Navigate to the flight controller node by pressing \`  followed by the number `1`. Note that nothing will appear in the terminal when you type these keys.

1.  Press enter to start the node

1. When prompted, "Are you ready to fly?" Type `n` and press enter (we do not want to fly at this point.)

### Locate the x and y velocity graphs

1. Go back to the web interface tab, wait about 5 seconds, and refresh the page. Make sure that you see "Connected" at the top of the page

1. Find the x and y velocity graphs on the web interface

### Test

1. Orient your drone so that the flight controller is facing away from you

1. While using your hand to move the drone to the **right**, verify that the **x velocity** graph shows **positive** reading

1. While using your hand to move the drone to the **left**, verify that the **x velocity** graph shows **negative** readings

1. While using your hand to move the drone **forward**, verify that the **y velocity** graph shows **positive** readings

1. While using your hand to move the drone **backward**, verify that the **y velocity** graph shows **negative** readings


Congrats on finishing your build!

## Debugging

If you do not see anything on the velocity graphs:

1. navigate to the terminal in the code editor

1. go to the camera node by typing "tick" 4: \` `4`

If you see an error printed that says something like "out of resources other than memory" the the issue is that your camera cable is not connected properly.

- make sure there are no holes or tears in your camera cable

- unplug the batter and then reinsert the camera cable into the camera and into the Pi

- repeat the steps of this checkoff again
