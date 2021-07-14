# Diagnostic {#part:diagnostic}

## Is your battery charged?

use the multimeter to check the battery voltage by inserting the probes into the battery terminals. A full battery is 12.6 V, an empty battery is around 10.5 V. If your battery voltage is below this, especially below 9V, the battery may be permanently damaged and needs to be recycled.

### Yes
continue on

### No
charge or replace the battery

## Does the BEC have a solid green light?

### Yes
continue on

### No

- check the voltage going into the BEC from the PDB

- make sure that the BEC is wired the correct way (red wire goes to positive (+), black wire goes to negative (-))

- Make sure that the OUT side of the BEC is soldered to the Pi Hat, and the IN side is soldered to the PDB

- Make sure there are no stray wire hairs that are shorting out the 5V and the GND rails on the Pi Hat

## Does the red light of the Pi stay on solid

This is the small led near the SD card

### Yes
continue on

### No

If the light is blinking, then the Pi is not receiving enough power. Check the voltage coming out of the BEC. It should be a constant 5V

If the light does not turn on, then the Pi is not receiving any power.

- Make sure that the Pi Hat is attached to the Pi all the way (there is no gap between the GPIO pins and the Pi Hat pin header).

- Make sure that the OUT side of the BEC is soldered to the Pi Hat, and the IN side is soldered to the PDB

- Make sure that there is not a short between the power and ground rails on the Pi Hat.

- Make sure there are no stray wire hairs that are shorting out the 5V and the GND rails on the Pi Hat

## Can you connect to your drone's WiFi?

### Yes
continue

### No

- Make sure that you have flashed your SD card

- Make sure that the green LED on the Pi near the SD card is blinking. If this light is not on, then the SD card is not flashed properly. Re-flash the SD card, and if this does not work try a new SD card.

## Can you access your drone's code editor?

### Yes
continue

### No

If the drone is in access mode (you're connected to the drone's WiFi):

- make sure that the link is opening to the right address. Try manually typing `192.168.42.1:8081` and press enter in your browser

- try another browser. Google Chrome is the browser and know to work correctly

If the drone is in managed mode (the drone is connected to your network):

- make sure that you're using the drone's new ip address (it will no longer be `192.168.42.1`). If you are trying to access the drone via hostname instead of ip, make sure that you append `.local`, so it would be `duckie-drone.local:8081`

## Can you access you drone's web interface?
Does the web interface show up when you browse to `192.168.42.1`? Don't worry for now if the interface connected or not, just whether or not the interface appears

### Yes
continue

### No

same steps as the code editor, but the address should be `192.168.42.1`, or `duckiesky-drone.local`, or `new-ip-address` if the drone is in managed mode.

## Does the flight code start?

use `roscd pidrone_pkg` and then run `./start`. Does the terminal look different?

### Yes
continue

### No

- make sure you're running the start script in the correct directory: `~/ws/src/pidrone_pkg`

## Does roscore startup?
After running the start code, typ \` 0, where \` is the key to the left of the `1` on your keyboard, and is on the same key as the `~`. Does the last line on this screen say `started core service [/rosout]` ?

### Yes
continue to [check the FC node](#troubleshoot-diagnostic-node-fc)

### No
Quit the screen by typing the tick (\`) followed by colon (`:`) and the type the word `quit` and press enter. You will not see the tick and colon typing, but you will see "quit" as you type at the bottom of the screen. continue on to the next checks.

## Are there multiple screens running?
In the terminal, type `screen -ls`. Were any sockets found?

### Yes
You will need to quit each socket found so that only one screen session is running. To do so:
For each socket found, there is a name that looks like `2503.pts-0.duckiesky-drone`. The four numbers at the beginning, `2503` are the session id. Run this command for each session id:

`screen -S [session id] -X quit`

For example, for this session it would be `screen -S 2503 -X quit`
Be sure that the 'S' and 'X' are capitalized.

## No
continue

## Is the ROS_MASTER_URI set
In the terminal, type `echo $ROS_MASTER_URI`. Did the terminal print out `http://localhost:11311`?

### Yes
If you're on the drone's network, continue on.

If you're drone is managed mode, then type `export ROS_MASTER_URI=[ip address]:11311` where `[ip address]` is the ip address of the drone on your network.

## Is the Flight controller node running? {#troubleshoot-diagnostic-node-fc}

Navigate to the flight controller node using "tick 1": \` 1. Press enter to start the node, and then type `y` and press enter when prompted if you're ready to fly. Is the last line printed out "/pidrone/battery"?

### Yes
continue

### no
If the last line printed out says that the USB is not plugged in:

- make sure that the USB is plugged into any one of the four USB ports on the Pi.

- make sure that the micro USB is plugged into the flight controller. (it should be hot glued in)

- rerun  `python flight_controller_node.py`.

If you get the error again:

- make sure that the flight controller is lighting up in some way. If it is not, the micro USB port on the flight controller may be broken. Was it glued down?

- try wiggling the micro USB end or using a different USB port on the Pi. If the flight controller never lights up, it may need to be replaced.

## Is the PID controller running?

Navigate to the PID controller node using "tick 2": \` 2. Is the last line printed out `PID Controller Started` ?

### Yes
continue

### No

- Try quitting the script with ctrl-c and rerunning it

## Is the state estimator running?

Navigate to the state estimator using "tick 3": \` 3. Is the last line printed out `Starting filter`?

### Yes
continue

### No

- make sure the flight controller node is running, as data is needed from the imu to start the filter.

- continue with the checks to make sure the other sensors are working, then try rerunning this script

## Is the vision node running?

Navigate to the vision node using "tick 4": \` 4. Is the last line printed out `Vision started` ?

### Yes
continue

### No

If the last few lines say something like: "out of resources other than memory", then the issue is the physical connection from the camera to the Pi.

- make sure that the sunny flap is shut (push on the small silver rectangle on the front of the camera and make sure it's attached firmly)

- make sure that the camera cable, or FFC (flexible flat cable) is fully inserted into the camera and the Pi.

- On the Pi, make sure the blue side of the FFC is facing towards the USB cables

- On the camera, make sure the blue side of the FFC is facing up

- Make sure that there are no holes or rips in the FFC. This is a common issue: a crash could have caused a tear, or a hole could have been made when soldering. If this is the case, you will need a new FFC

- rerun the vision script

## Is the IR node running?

Navigate to the IR node using "tick 5": \`5. Is the last line printed out `Publishing IR` ?

### Yes

continue

### No

- make sure that the IR sensor wire is firmly plugged into the IR sensor

check the connections on the ADC:

- make sure there are no shorts between adjacent pins

- make sure there are no stray wire hairs causing shorts

- make sure the yellow signal wire of the IR sensor connected to "A0" on the ADC

- make sure there is 5V across the "V" and "G" pins

- Try rerunning the node. If it still does not work, go back through Build Part 2 to check all of the wiring.

## Is rosbridge running?

Navigate to the rosbridge node using "tick 6": \` 6. Does the last line printed out include the phrase `Rosbridge websocket server started on port 9090` ?

### Yes
continue

### No

- make sure you have no other programs using the same port as the Rosbridge server (9090)

try rerunning this script.

## Does the web interface say connected?

Open up or refresh the drone's web interface: [192.168.42.1](http://192.168.42.1). Does the interface say "Connected" at the top?

### Yes
continue

### No

- make sure you are not using Microsoft Edge browser. Chrome is the preferred browser

wait another 10 seconds and try refreshing again.

## Is there data on the height readings graph?
When you move the drone up and down, does the height reading graph change?

### Yes
continue

### No
recheck the IR node. rerun the node if needed and then refresh the browser.

## Is there data on the x and y velocity graphs?
Move the drone to the left and right over a textured surface. Do the X and Y velocity graphs change?

### Yes
continue

### No
recheck the vision node. rerun the node if needed and refresh the browser.

## Is the data on the graphs lagging?
Is there a long delay between when you move the drone and when the graphs change?

### Yes
If you are running the drone in access mode, then try quitting the screen with tick colon quit: \` `:quit`. rerun the flight code with `./start` and start up the flight controller again. If this does not help, unplug and plug back in the battery to the drone and try again.

If you are running the drone in managed mode, this is probably due to latency in your home network. Take some of the devices offline, or restart the drone and fly in access mode.

### No
continue

## Does the drone arm?

Click on the web interface and then press the semicolon: `;`. Do the motors on the drone start spinning?

### Yes
continue

### No
Plug the USB into a computer with Cleanflight and verify that the settings in cleanflight from Build Part 3 FC.

When going back through the settings, double check that:

- the yaw is flipped 180 degrees in the "Configuration" tab

- the receiver is set to MSP RX Input (so that the FC can receive commands from the Pi over USB) in the "Configuration" tab

- the ESC/Motor protocol is set to multishot in the "Configuration" tab.



## Does the drone get off the ground?

### Yes
continue

### No

- make sure that the arrows inscribed on the propellers are visible from the top of the drone

- make sure that the arrows on the props are in the same direction as the arrows on the motors

-  Take off the propellers from your motors and plug the battery into your drone. In cleanflight, navigate to the motors tab, click "I agree to the risks", and try to spin up each motor. Make sure that each motor spins in the correct direction.

- Make sure that when you spin up motor 1, the correct motor spins (the bottom right). Do this for all of the motors
