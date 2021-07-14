# Part 3: Flight Controller and Cleanflight Checkpoint {#build-part3-FC-checkpoint status=ready}

**Expected Time**: 20 minutes

## Check the ESC ordering

Ensure the PWM wires are connected to the correct pins on the flight controller. Do this by following the PWM wires from the flight controller back to which motor the ESC is connected to. Make sure that this matches up with the image below.

<figure>
    <figcaption>Motors Diagram</figcaption>
    <img src="photos/correct_motors_diagram.jpg" width="200"/>
</figure>  

## Check the motor attachment

Make sure the arrows on the motors match up with the diagram above. It is important that the correct motors are in the correct spot because the motor bolts are threaded so that the propeller will not loosen the nut and fly off the drone.

## Check the motor direction

Make sure the motors are spinning in the correct direction. To do this, connect your flight controller to cleanflight with the **propellers off** and the battery plugged in, and spin up each motor to make sure it is spinning in the same direction as the arrow on the motor, which is the same direction as shown in the image above. It helps to put a small piece of tape on the side of the motor to know which way it is spinning.

## Arm your drone

You will now test out arming your motors using the drone software. To arm the motors, the software sends out a sequence of PWM values that let's the flight controller know that the operator is ready to fly. After arming the motors, the software sends out a low PWM value that leaves the motors idling at speed much slower than what would be needed for takeoff.

In this checkpoint, you go through the process of setting up your drone to fly, and then will arm the motors and make sure they are spinning. Then you will disarm the motors and make sure they stop spinning. Then you will be done with build part 3!

### Power up your drone

1. Make sure the propellers are off of the motors

1. Connect the flight controller USB to the Raspberry Pi

1. Plug in the battery

### Connect to your drone

1. Connect to your drone's wifi

1. Browse to the drone's code editor: [http://192.168.42.1:8081](http://192.168.42.1:8081)

### Start up the flight code

1. If a terminal is not already open at the bottom of the code editor, then open a terminal: Menu (top left button) > Terminal > New Terminal

1. Start up the flight code by typing in the command `./start` and press enter

### Connect to the web interface

1. In a new tab, browse to the web interface: [http://192.168.42.1](http://192.168.42.1)

1. Refresh this page and ensure it says "Connected" at the top. If not, wait a few more seconds and try refreshing the page again.

### Start the flight controller node

1. Navigate back to the terminal in the code editor

1. Identify the "tick" key on your keyboard. It looks like this: \` and is typically the key to the left of the '1' key. It is also typically located on the same key as the tilde `~`.

1. Navigate to the flight controller node by typing "tick" and then 1: \` `1`

1. Press enter to start the node

1. When prompted "Are you ready to fly?", type `y` and press enter since we want to spin the motors

### Get a safety failure message!

1. Navigate back to the web interface

1. Attempt to arm your drone by pressing the semicolon (`;`) button on your keyboard. (Nothing should happen at this point, continue on)

1. Navigate back to the code editor and read the message in the terminal. It should look like the image below:

<figure>
    <figcaption>Camera Error</figcaption>
    <img src="photos/checkpoint3-fc-error-camera.png" width="400"/>
</figure>  

Better: Explanation: The drone code contains safety checks that stop the drone from flying if there is a technical problem. Based on the message in the terminal, the issue is that the drone is not receiving data from the camera. This makes sense, because we haven't even attached the camera, yet! You will temporarily disable this safety check for the purpose of this checkoff, and then reenable it afterwords. This is useful to practice because you may want to adjust other safety thresholds later on as you fly your drone.

### Change the safety threshold

1. On the left side of your code editor, locate the "params" folder.

1. Open the `thresholds.yaml` file.

1. Locate the `camera` paremeter underneath `heartbeat`, and change the value from `0.25` to `60`. This means the code will check for camera errors every 60 seconds, which is plenty of time for this checkoff.

1. Close the file to avoid accidentaly editing it by clicking the small "x" near the file name at the top of the editor. The file change is saved automatically

<figure>
    <figcaption>Camera Error</figcaption>
    <img src="photos/checkpoint3-fc-camera-threshold.png" width="400"/>
</figure>  

### Arm your drone for real!

1. Restart the flight controller: click in the terminal, press the up arrow on your keyboard, type "y" and press enter.

1. Navigate back to the web interface

1. Arm your drone by pressing the semicolon (`;`) button on your keyboard. 

1. Verify that the motors start spinning. If not, navigate back to the code editor and see if any errors were printed out in the terminal. If there are no errors and the motors are not spinning, it is recommended that you check your cleanflight settings and make sure they're exactly like ours.

1. Observe how the flight controller automatically adjusts to disturbances by tilting up one side of the drone and noticing how the motors that are lower are spinning faster than the motors that you've tilted up.

1. Disarm your drone by pressing the **spacebar**.

### Revert the safety threshold

1. On the left side of your code editor, locate the "params" folder.

1. Open the `thresholds.yaml` file.

1. Locate the `camera` paremeter and change the value from `60` back to `0.25`.

1. Close the file to avoid accidentaly editing it (the file saves automatically).

Congrats on finishing build part 3!
