# Part 4: Camera, Propellers, and Mounting Hardware Instructions {#build-part4-instructions status=ready}

## Glue USB Connector to Flight Controller

These little surface-mounted micro USB ports are prone to breaking upon impact; therefore, to minimize
the likelihood of damaging the connect, you will thoroughly cover the port with hot glue.

### Plug in the micro USB to USB cable

If it is not plugged in already, plug the 6" micro USB to USB cable into the micro USB port of the flight controller.

### Glue the port

Liberally apply hot glue over the end of the usb cable and the port on the flight controller.

Note: You will not be able to remove the USB cable. This is intentional. Also note that the flight controller shown is from a previous hardware version; use this as an example for how to glue your FC.  

<figure>
    <figcaption>Glued USB Connector</figcaption>
    <img style='width:350px' src="photos/usb_glue.png"/>
</figure>

## Attach the Pi Camera to the drone frame

### Detach the Pi Hat

Gently lift near the pin header to detach the Pi hat

### Put tape on the Pi Camera

Put foam mounting tape on the top, left, and right sides of the pi cam. Cut off any excess tape.

Note: The camera in the photo does not have the white flexible flat cable (FFC) attached. This is just for the photo; it is better to leave the FFC attached to your camera

<figure>
   <figcaption>Pi Cam with Tape</figcaption>
   <img style='width:300px' src="photos/tape_attached_to_pi_cam.jpg"/>
</figure>

### Stick camera to the drone frame

1. Peel off the back of the foam mounting tape

1. Stick the Pi Cam to the hole in the back of the drone. attach on top so camera faces downward and the FFC goes away from the drone. Ensure that the attachment is not skewed.

<figure class="flow-subfigures">  
   <figcaption>Attach the Pi Cam (bottom-up view)</figcaption>
   <figure>
       <figcaption>Pi Cam without Skew</figcaption>
       <img style='width:200px' src="photos/pi_cam_attached_no_skew.jpg"/>
   </figure>
   <figure>  
       <figcaption>Pi Cam with Skew</figcaption>
       <img style='width:200px' src="photos/pi_cam_attached_skew.jpg"/>
   </figure>
</figure>  

## Attach Battery Mount

Use zip ties to attach the battery mount to the drone frame as shown in the image.

Note: Ignore the propellers on the drone in the image. You will attach those in the final step.

<figure>
    <figcaption>Battery Mount</figcaption>
    <img style='width:350px' src="photos/battery-mount.png"/>
</figure>

This is how the battery will be attached to the drone:

<figure class="flow-subfigures">  
    <figcaption>Strapping in the Battery</figcaption>
    <figure>
        <figcaption>Battery unstrapped</figcaption>
        <img style='width:200px' src="photos/battery-not-strapped.png"/>
    </figure>
    <figure>  
        <figcaption>Battery strapped in</figcaption>
        <img style='width:200px' src="photos/battery-strapped.png"/>
    </figure>
</figure>


## Attach PiMount

Place the PiMount on top of the PDB and use the **short** black [M3 bolts](#materials-pimount-screws) from the motors box to secure the mount to the standoffs.     

Note: Ensure that the triangle shape is on the side of the camera.

<figure>
    <figcaption>Securing the PiMount</figcaption>
    <img style='width:350px' src="photos/securing_pimount_inked.jpg"/>
</figure>


## Attach Raspberry Pi

### Insert standoffs

You will now insert standoffs into the Pi that will help support the Pi Hat and keep it from bouncing during flight.

1. Screw in a pair of standoffs into bottom right hole of the Pi. It may help to first screw in a black screw into the standoffs, then use an allen wrench to screw the standoffs into the hole. Note that the hole may initially seem too small for the standoffs, but it will definitely screw in.

<figure class="flow-subfigures">  
    <figcaption>Inserting standoffs into Pi</figcaption>
    <figure>
        <figcaption>Pi Standoffs Top View</figcaption>
        <img style='width:230px' src="photos/pihat_standoffs_topview_inked.jpg"/>
    </figure>
    <figure>  
        <figcaption>Pi Standoffs Side View</figcaption>
        <img style='width:230px' src="photos/pihat_standoffs_sideview_inked.jpg"/>
    </figure>
</figure>  

### Attach Pi to Pi Mount

Leaving the Pi Hat detached (to make the next step easier), use the sliver screws included in the drone frame kit to secure the Pi to the mount. You should use [3 panhead screws](#materials-pimount-screws) as shown in picture. The Pi USB ports should face toward the front of the drone.

Note: The image below does not include the brass standoff from the previous step. Please ignore this discrepancy.

<figure>
    <figcaption>Securing the Pi</figcaption>
    <img style='width:350px' src="photos/securing_pi_inked.jpg"/>
</figure>

### Plug in the Flight Controller USB

Plug in the Flight Controller USB to any of the USB ports on the Raspberry Pi. The USB sends the autonomous flight commands from the Pi to the FC.

<figure>
    <figcaption>USB Cable Plugged into Pi</figcaption>
    <img style='width:200px' src="photos/usb_in_pi.jpg"/>
</figure>

## Connect Pi Cam

### Connect FFC to the Pi Camera

If not already done, attach the FFC to the Pi Cam.

 <figure>
     <figcaption> FFC Attachment to Pi Cam (shorter side in camera port)</figcaption>
     <img style='width:200px' src="photos/ffc_attachment_good_inked.jpg"/>
 </figure>

### Connect FFC to the Pi

Feed the flexible flat cable (FFC) from the Pi Cam through the slot in Pi Hat, then connect it to the Pi's camera port, i.e. the black port close to the HDMI port.

Note: Do not just push the FFC into the slot. [Watch this video](https://www.youtube.com/watch?v=VzYGDq0D1mw) on how to insert the camera properly.

<figure class="flow-subfigures">  
    <figcaption>Connecting Pi Cam</figcaption>
    <figure>
        <figcaption>FFC cable through Pi Hat</figcaption>
        <img style='width:230px' src="photos/pihat_camera_topview.jpg"/>
    </figure>
    <figure>  
        <figcaption>FFC cable in Pi camera port</figcaption>
        <img style='width:230px' src="photos/pihat_camera_portview_inked.jpg"/>
    </figure>
</figure>  

### Re-attach Pi Hat

Put the Pi Hat back onto the Pi. Refer to [part 1](#build-part1-attach-pihat) for detailed instructions to attach the Pi hat.

## Attach the IR Sensor

Zip tie the IR sensor at the front of the drone, facing down. It will be underneath the flight controller and the wires will go back toward the frame.

<figure class="flow-subfigures">  
    <figcaption>Attached IR Sensor</figcaption>
    <figure>
       <figcaption>Top View</figcaption>
       <img style='width:220px' src="photos/ir_attached_top_view.jpg"/>
    </figure>
    <figure>  
       <figcaption>Bottom View</figcaption>
       <img style='width:220px' src="photos/ir_attached_bottom_view.jpg"/>
    </figure>
</figure>

## Attach BEC to Drone

Attach the BEC to the top of the USB ports using some double sided tape. Alternatively, if it does not reach, then 1) place electrical tape on the Pi Hat, 2) place double sided mounting tape on the electrical tape, and 3) place the BEC upside down on double sided mounting tape.

<figure class="flow-subfigures">  
    <figcaption>Attaching BEC</figcaption>
    <figure>
        <figcaption>BEC on Pi USB ports (primary method)</figcaption>
        <img style='width:230px' src="photos/bec_attached_pi_usbports_inked.jpg"/>
    </figure>
    <figure>  
        <figcaption>BEC on Pi Hat (alternate method)</figcaption>
        <img style='width:230px' src="photos/bec_attached_pihat_inked.jpg"/>
    </figure>
</figure>  


## Ziptie ESCs and PWM Connectors to Frame Arms

Use the small zipties to secure the ESCs and motor wires to the bottom of each frame arm. To do this, thread the zip ties through the holes in each frame arm. If they do not fit, instead wrap the zip ties around the frame arm. Also, use zip ties to secure the PWM connectors to the sides of each frame arm.

<figure class="flow-subfigures">  
    <figcaption>Use Zip-ties to Secure Everything</figcaption>
    <figure>
        <figcaption>ESC and Motor Wires with Zipties</figcaption>
        <img style='width:230px' src="photos/ziptie_esc.jpg"/>
    </figure>
    <figure>  
        <figcaption>PWM Connector with Zipties</figcaption>
        <img style='width:230px' src="photos/ziptie_pwm.jpg"/>
    </figure>
</figure>  

## Propellers

Attach the propellers to the drone so that it may fly; attach CW propellers to the CW motors, and CCW propellers to the CCW motors. The motors have small arrows on them in the center to indicate which type they are.

Note: The bolts on the motors that spin CCW tighten when turned CW, and the bolts on the motors that spin CW tighten when turned CCW.

Use the [8 mm wrench](#materials-wrench-8mm) to tighten the bolts down so that the bottom of the propeller is flat on the top of the motor. Screw bolts down tightly, but not so tight that you could not remove the propellers if you had to.

<figure class="flow-subfigures">  
    <figcaption>Put on Propellers</figcaption>
    <figure>
        <figcaption>Notice Arrows Indicating the Type of Propeller</figcaption>
        <img style='width:230px' src="photos/prop.jpg"/>
    </figure>
    <figure>  
        <figcaption>Attaching Propellers</figcaption>
        <img style='width:230px' src="photos/securing_prop.jpg"/>
    </figure>
    <figure>  
        <figcaption>Propeller Flat on Motor</figcaption>
        <img style='width:250px' src="photos/prop_flat_on_motor.jpg"/>
    </figure>
</figure>  

<div class='check' markdown="1">

*Propeller Direction:*

1. The arrows on the propellers should be on visible from the top of the drone

1. The arrows should be going in the same direction as the arrows on the motors.

*Propeller Attachment:*

1. The propellers **must** be flat on the base of the motor

1. Make sure there is no gap between the propeller, the motor, and the motor nut.

1. Holding the motor still, try to spin the prop and make sure the props **cannot** spin around the motor shaft; the motors and the props should spin together.

</div>


## Attach Drone Feet

Attach the drone feet in the drone frame box to the four arms of the drone. This can be done with either electrical tape or zip ties. **DO NOT** use hot glue, as it will not work.

<figure class="flow-subfigures">  
    <figcaption>Attach Drone Feet</figcaption>
    <figure>
        <figcaption>Side View</figcaption>
        <img style='width:230px' src="photos/drone_feet_side_view.jpg"/>
    </figure>
    <figure>  
        <figcaption>Bottom View</figcaption>
        <img style='width:230px' src="photos/drone_feet_bottom_view.jpg"/>
    </figure>
</figure>  


<div class='check' markdown="1">

Make sure ESC-motor wires are ziptied down properly. If not, you risk having a short.

Spin the propellers manually with your finger. Ensure no wires are hit by the propellers.

Make sure no wires or parts are dangling from the drone frame.

</div>
