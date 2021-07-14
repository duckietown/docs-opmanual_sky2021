# Part 3: Flight Controller and Cleanflight Instructions {#build-part3-fc-instructions status=ready}

**Expected Time**: 1 hour

## Attach the Flight Controller

### Trim

Trim the all of the pins on the flight controller just like the four shown in the image. This helps the flight controller sit level on the drone frame.

Note: the image shows only 4 trimmed, but you will want to trim all of the pins (updated picture coming soon).

<figure class="flow-subfigures">  
<figcaption>Trim the FC pins</figcaption>
     <figure>
           <figcaption>FC pins need trimming</figcaption>
           <img style='width:220px' src="photos/fc-trim-pin.png"/>
     </figure>
     <figure>
           <figcaption>FC with pins cut</figcaption>
           <img style='width:220px' src="photos/fc-pins-level.png"/>
     </figure>
</figure>

### Apply Tape to the Bottom of the FC

1. Put double sided mounting tape on the bottom of the FC.

1. Cut off any excess tape.

### Stick the FC to the drone frame

1. Peel off the back of the foam tape

1. Attach the FC to front of the drone. Ensure the FC is not skewed and it is pushed against the frame body. (Ignore the extra wires in the flight controller for now).

<figure>
    <figcaption>Orientation of Drone Frame</figcaption>
    <img style='width:200px' src="photos/drone_frame_labeled_orientation.jpg"/>
</figure>

Note: the white plastic tabs will need to hang off the frame for the flight controller to sit level.

<figure class="flow-subfigures">  
<figcaption>FC attached to drone frame</figcaption>
     <figure>
          <figcaption>Top View</figcaption>
          <img style='width:220px' src="fc-attached.jpg"/>
     </figure>
     <figure>
          <figcaption>Bottom View</figcaption>
          <img style='width:220px' src="fc-tabs.png"/>
     </figure>
</figure>


Note:  Try to minimize the FC skew as much as possible. (the following photos are an example of skew. ignore the difference of flight controller).

<figure class="flow-subfigures">  
     <figcaption>Attach FC (bottom-up view)</figcaption>
     <figure>
         <figcaption>FC without Skew</figcaption>
         <img style='width:220px' src="photos/fc_attached_no_skew.jpg"/>
     </figure>
     <figure>  
         <figcaption>FC with Skew</figcaption>
         <img style='width:220px' src="photos/fc_attached_skew.jpg"/>
     </figure>
</figure>


<div class='check' markdown="1">

Once the FC is attached, do a "rock test" (i.e. try to rock the FC back-and-forth by pushing the corners). If the FC rocks, then the double sided mounting tape used is too soft and is compressing under pressure. Detach the FC from the frame (e.g. _carefully_ use a flat-head screwdriver) and replace the tape with more robust tape.

</div>


## Download the required software and files

### Download the firmware

On your base station, download the [flight controller firmware](https://duckietown-public-storage.s3.amazonaws.com/brown/firmware/spracing_f3-7_27_20.hex)

Note: the file extension for this file should be **.hex**. Your computer might have added a **.txt** to the end of the file, rename the file and delete **.txt** so that the file ends in **.hex**.

### Install the USB to UART driver

A driver is software that allows your computer to talk to a hardware device. You will need a driver that allows the computer to talk to the flight controller.

1. On your base station, download [this driver](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers) . Be sure to select the correct download for your base station's operating system. If you are using a Chromebook, you will not need this driver.

1. Once downloaded, click on the file and go through the installation process

1. After the installation finishes, restart your base station.

### Install Cleanflight

Cleanflight is open-source flight controller software that allows you to flash firmware to the flight controller, and configure the settings.

On your base station, install [Cleanflight](http://cleanflight.com/) (you will need Google Chrome)

## Flash the firmware

Please follow the written instructions below to flash firmware onto your flight controller. If you are having trouble flashing, please follow [this video](https://drive.google.com/file/d/1F73czx0B381jY2ls-R7TQQ2HCC185t96/view?usp=sharing) to flash the flight controller with the boot pins shorted.

### Open the firmware flasher

1. Launch CleanFlight

1. Click on "Firmware Flasher" on the left sidebar.

<figure>
   <figcaption>Firmware Flasher </figcaption>
   <img style='width:500px' src="photos/click_on_firmware_flasher.png"/>
</figure>

### Load the firmware

Click on "Load Firmware [Local]" in the bottom right corner of the window and select the firmware file that you downloaded (the one with the .hex extension).

<figure>  
  <figcaption>Loading Custom Firmware</figcaption>
  <img style='width:500px' src="photos/load_firmware.png"/>
</figure>

### Connect the FC

With the battery **disconnected,** connect the FC to the base station via a USB to micro USB cable. Click the flash firmware button at the bottom right of the screen. Flashing will be complete once the bar at the bottom of the screen says "Programming: SUCCESSFUL".

Note: If the bar instead reaches halfway and then says "Verifying: FAILED", do not worry - it has flashed successfully.     

<figure>
   <figcaption>Flashing</figcaption>
   <img style='width:500px' src="photos/flashing.png"/>
</figure>

## Configure the Cleanflight settings

Now that the FC has been flashed with firmware, it can be configured.

### Disconnect and Reconnect

1. Disconnect the FC from the base station and close Cleanflight.

1. Launch Cleanflight

1. Reconnect the FC to the workstation

1. Click the "Connect" button in the top right corner of the screen (this is not needed if "auto-connect" is toggled on).

<figure>
   <figcaption>Connecting FC to Cleanflight</figcaption>
   <img style='width:500px' src="photos/connect.png"/>
</figure>

Now you will configure each of the settings that need to be changed.


### "Ports"

1. Go to "Ports" tab on the left side of cleanflight

1. make sure SerialRX for UART2 is disabled and click "Save and Reboot." UART2 is a pin on the flight controller, and we want to make sure it only uses the USB.

<figure>
   <figcaption>Ports Configuration</figcaption>
   <img style='width:500px' src="photos/ports.png"/>
</figure>


### "Configuration" {#build-cleanflight-config}

Go to "Configuration" tab on the left side of cleanflight

- Change the ESC/Motor protocol to "MULTISHOT".

<figure>
   <figcaption>Set Multishot</figcaption>
   <img style='width:500px' src="photos/multishot.png"/>
</figure>

- Set the Minimum Throttle to 1100.

<figure>  
   <figcaption>Set Minimum Throttle</figcaption>
   <img style='width:500px' src="photos/minimum_throttle.png"/>
</figure>

- Flip the yaw by 180&deg; (because the FC is rotated by 180&deg; when attached to the drone frame).

<figure>
   <figcaption>Flip Yaw</figcaption>
   <img style='width:500px' src="photos/flip_yaw.png"/>
</figure>

- Change the receiver to "MSP RX input" (by default it is configured to receive data from an RC receiver, but we want it to take commands over MSP).

<figure>  
   <figcaption>MSP RX Input</figcaption>
   <img style='width:500px' src="photos/msprx.png"/>
</figure>

- Finally, click "Save and Reboot."    

Note: On the configuration page, Cleanflight might show that the direction of your motors are reversed. This is a UI bug and can be ignored. You will ensure that your motors are spinning in the correct direction in later steps.    

### "Modes"

The FC needs to be in Angle mode for its entire available range - not just the range of acrobatic mode.

Go to the "Modes" tab on the left side of cleanflight

- Under the "Angle" option, click "Add Range".

<figure>
   <figcaption>Angle Mode Option</figcaption>
   <img style='width:500px' src="photos/add_range.png"/>
</figure>

- Drag the sliders so that the range spans from 900 to 2100 (i.e. entire range).

<figure>  
   <figcaption>Modes Configuration</figcaption>
   <figure>
       <figcaption>Expand Range</figcaption>
       <img style='width:500px' src="photos/angle_range.png"/>
   </figure>
   <figure>  
       <figcaption>Expanded Range</figcaption>
       <img style='width:500px' src="photos/angle_range_2.png"/>
   </figure>
</figure>

- Finally, click "Save".

### PID Tuning

The FC PID parameters need to be changed to work better with our drone. Go to the "PID Tuning" tab. Change the "ROLL" and "PITCH" PID terms to match the image. For reference: Roll should be (Proportional: 60, Integral: 40, Derivative: 50, RC Rate: 1.00, Super Rate: 0.00, Max Vel: 200). Pitch should be (Proportional: 60, Integral: 40, Derivative: 50, RC Rate: curly bracket, Super Rate: 0.00, Max Vel: 200). Change angle limit to 50. Finally, click "Save".

<figure>  
   <figcaption>PID Tuning Configuration</figcaption>
   <figure>
       <figcaption>PID Params</figcaption>
       <img style='width:500px' src="photos/pid_settings.png"/>
   </figure>
   <figure>  
       <figcaption>Set Angle Limit</figcaption>
       <img style='width:500px' src="photos/angle_limit.png"/>
   </figure>
</figure>

<div class='check' markdown="1">

Double check that all of the settings in cleanflight match up to the ones above. Make sure to save the settings when possible.

</div>

### Verify

To make sure that the settings were properly saved, you will verify just one of the changes.

1. navigate to the configuration tab

1. Scroll down to box that's labelled "Receiver"

1. Make sure the input says "MSP RX Input"

<figure>  
   <figcaption>MSP RX Input</figcaption>
   <img style='width:500px' src="photos/msprx.png"/>
</figure>


## Connecting the ESCs to the Flight Controller {#build-part3-fc-connect-esc}

Now that the FC has been configured, it can be connected to the ESCs via the PWM wires (i.e. the white and black wires on the ESCs). Take a moment not find the numbers **1-8** on the flight controller, adjacent to the pins that your soldered in. We will be connecting the PWM wires to number **1-4** because we have 4 motors. These numbers on the flight controller indicate which PWM wire should be connected to which set of pins on the flight controller. For example, in the image below, motor 1 is in the bottom right; therefore you will take the PWM wire from the ESC connected to the motor in the bottom right of your drone, and connect this to the pins labelled **1** on the flight controller.

<figure>
    <figcaption>Motors Diagram</figcaption>
    <img src="photos/correct_motors_diagram.jpg" width="200"/>
</figure>  

Where the red arrow indicates the front direction of the drone. Recall that for your drone, the FC is on the front and the camera is on the back.

Note: There is a correct way to connect an ESC to the Flight Controller. Make sure the white wire of the ESC signal wire pair is facing toward the board, and the black wire is facing away.

<figure>
    <figcaption>Connecting ESCs. White wire on the inside. </figcaption>
    <img src="photos/fc-pwm.png" width="350"/>
</figure>  

1) Plug each PWM wire into its corresponding ESC signal wire pair.

## Test the Motors

With the ESCs connected to the FC, your drone's motors can be tested. In this section, you will verify that the motors are spinning correctly.

### Remove Propellors

**Make sure no propellers are attached to your drone's motors!** You will be spinning the motors and you don't want your drone to fly off your desk!

### Launch Cleanflight

1. Open up Cleanflight on your base station.

### Connect your drone

1. Plug your drone's FC into a computer (via the USB to micro USB cable)

1. Press connect in the top right corner of Cleanflight. (You won't need to do this if "autoconnect" was selected)

1. Plug the battery into your drone.

### Navigate to Motors tab

Go to the **Motors** tab in Cleanflight. Read the safety notice and check the box that says **“I understand the risks, propellers are removed - Enable motor control”**.

### Test each motor

1. Slowly spin up the first motor by slowly dragging the **1** slider up

1. Use the motors diagram to verify that:

- the correct motor spins. If the correct motor does not spin, [reconnect the ESC wires to the FC](#build-part3-fc-connect-esc) in the correct order.

- the motor spins in the correct direction.  If the motor spins in the incorrect direction, take note and you will correct it later on.  Read the following Remark and Note before continuing.

Remark: One way to find out which direction the motor is spinning is to put a piece of tap on the motor to create a flap. Then, use a pencil or other object and touch it to the tape while the motor is spinning to see which direction it is pushed.

Note: **DO NOT** follow the incorrect motors diagram. If Cleanflight shows the incorrect motors diagram, then ignore it - the diagram is a UI bug and does not affect the spin directions of the motors.

<figure class="flow-subfigures">  
   <figcaption>Motors Diagram</figcaption>
   <figure>
       <figcaption>Correct Motors Diagram</figcaption>
       <img style='width:200px' src="photos/correct_motors_diagram.jpg"/>
   </figure>
   <figure>  
       <figcaption>Incorrect Motors Diagram. **DO NOT FOLLOW**.</figcaption>
       <img style='width:200px' src="photos/incorrect_motors_diagram.jpg"/>
   </figure>
</figure>

Repeat this process for all of the motors.

### Change the Motor Directions

Power your drone off by disconnecting the power supply.

For each motor that is spinning in the **incorrect** direction:

1. Disconnect any 2 of the 3 ESC pad wires from the motor, e.g. disconnect the red and yellow ESC pad wires from their corresponding motor wires. Keep track of which wires used to be connected together.

1. Swap the connections, e.g. plug the socket bullet connector of the red ESC pad wire into the plug bullet connector of the motor wire previously connected to the yellow ESC pad wire and vice-versa.

### Verify

Re-connect a power supply to your drone and check that the motors are now spinning in the correct direction. If not, repeat the swapping process.

## Calibrate the ESCs

By this point, your drone's FC should be able to spin up each of the 4 motors. This is possible because the FC is sending *PWM signals* to each of the 4 ESCs, which in turn sends electrical signals to each of the 4 motors.

A **PWM signal** is a signla that communicates at how much RPM an ESC should spin a motor. For example, the PWM signal "1000" might correspond to 2300 RPM.

However, note that your drone has not 1, but 4 ESCs - which may not all have the same PWM-to-RPM understanding. For example, ESC 1 might think the PWM signal "1100" from the FC means 2300 RPM while ESC 2 might think the PWM signal "1000" means 2300 RPM.

The solution to this problem is to *calibrate* the ESCs with the FC. In this context, **calibration** means getting all the ESCs to have the same PWM-to-RPM understanding from the FC. In this section, you will calibrate your ESCs.

Note that symptoms of no calibration include: scorching hot motors, a drone that lifts to one side during flight, motors that appear to spin at different speeds.

### Remove propellors

**Make sure no propellers are attached to your drone's motors**!   

### Disconnect Power

Unplug the battery from your drone.

### Launch Cleanflight

1. On your base station, open cleanflight

1. Connect the FC to a computer and click "Connect" in the top right of the screen

### Navigate to the Motors tab

1. Go to the Motors tab on the left side of Cleanflight.

1. Read the safety notice and check the box that says **“I understand the risks, propellers are removed - Enable motor control”**.

### Calibrate

1. Drag the master slider up to full. All 4 motor sliders should automatically move up to full accordingly (e.g. 2000).

1. Plug the battery into your drone.

The ESCs will make an interesting set of sounds, kind of like music. If they do not, stop and try the previous steps again.

1. After the music stops, drag the master slider to the bottom of the bar. Correspondingly, all 4 motor sliders should automatically be at the bottoms of their bars (e.g. 1000). The motors will make another set of sounds.

1. After the sounds stop, spin up each motor and verify it is spinning in the correct direction (i.e. according to the motors diagram in this doc).

<div class='check' markdown="1">

- Make sure the motors spin in the correct direction, i.e. according to the motors diagram in this doc.

- When you connect the drone to power, the ESCs should make a "boop boop boop" sound, followed by a "beep BEEEEEP" sound.

</div>
