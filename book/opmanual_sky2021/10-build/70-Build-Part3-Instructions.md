# Part 3: Motors, and ESCs Instructions {#build-part3-instructions status=ready}

**Expected Time**: 5 hours


Note: Sometimes parts will have wires already tinned out-of-the-box by the manufacturer (i.e. pre-tinned). You can identify this by: 1) the "shininess" of the tip of a wire and 2) the inability to fray the wire strands of the tip of a wire. However, such tinning is often ineffective. Cut off any pre-tinned tips, then strip and tin the part yourself.

## Solder wires onto ESC pads

In this section, you will prepare your ESCs. Each ESC has 3 pads labeled A, B, and C. The labels are on the bottom of the ESC:

<figure>
    <figcaption>Pad Letters</figcaption>
    <img style='width:400px' src="photos/ABC_pads_on_ESC.jpg"/>
</figure>

### Cut ESC wires to length

1. Cut four pieces of the blue wire, 3 inch lengths

1. Cut four pieces of the yellow wire, 3 inch lengths

1. Cut four pieces of the red wire, 3 inch lengths

### Tin the ESC wires

1. Strip about 5mm from both ends of the each wire that you just cut (12 wires in total)

1. Tin both ends of the wires

### Prepare the ESC:

Use your fingers (or small wire cutters) to *very carefully* remove excess material from each ESC pad.

<figure class="flow-subfigures">  
    <figcaption>Clean ESC Pads</figcaption>
    <figure>
        <figcaption>Excess Material on ESC Pads</figcaption>
        <img style='width:200px' src="photos/ESC_pads_unclean_inked.jpg"/>
    </figure>
    <figure>  
        <figcaption>After Removing the Excess Material</figcaption>
        <img style='width:200px' src="photos/ESC_pads_clean_inked.jpg"/>
    </figure>
</figure>

### Tin the ESC pads

Tin all three metal pads on each of the four ESCs

### Solder the ESC wires to the ESCs

1. Review the [wire-to-pad soldering technique](#prereq-solder-wire-to-pad)

1. Use the helping hands to hold one ESC in place for solder

1. Solder the yellow wire to the middle pad (pad "B")

1. Solder the red wire to pad "A"

1. Solder the blue wire to pad "B"

1. Lightly pull the wire soldered to the pad and verify it stays on.

1. Do a [connectivity check](https://docs.duckietown.org/daffy/opmanual_sky/out/build_multimeter.html) between each pair of soldered wires (recommend doing this now instead of in checkoff later). The multimeter *should* **not** beep, otherwise there is a short between the pair; if the multimeter does hold a continuous beep, then you will need to fix the short by removing any excess solder forming a bridge between the problematic pair of wires.

<figure>  
    <figcaption>Connectivity Check on Wires</figcaption>
    <figure>
        <figcaption>RY Check</figcaption>
        <img style='width:300px' src="photos/conn_check_RY.jpg"/>
    </figure>
    <figure>  
        <figcaption>RB Check</figcaption>
        <img style='width:300px' src="photos/conn_check_RB.jpg"/>
    </figure>
    <figure>  
        <figcaption>YB Check</figcaption>
        <img style='width:300px' src="photos/conn_check_YB.jpg"/>
    </figure>
</figure>


### Insulate the ESC wires

Put a heat shrink over the ESC. The heat shrink should cover (length-wise) the exposed soldered wires on one end and half the ESC on the other end. Apply heat to shrink the heat shrink.

<figure class="flow-subfigures">  
    <figcaption>Put Heat Shrinks on ESCs</figcaption>
    <figure>
        <figcaption>A Prepared ESC</figcaption>
        <img style='width:220px' src="photos/colorful_esc.jpg"/>
    </figure>
    <figure>  
        <figcaption>A Prepared ESC with Heat Shrinks</figcaption>
        <img style='width:220px' src="photos/colorful_esc_shrinkwrap2.jpg"/>
    </figure>
</figure>  

Repeat the above steps for each ESC

## ESC bullet connectors

In this step you will solder bullet connectors onto the ESC wires and the motor wires so that you can easily connect them later on.

### Review soldering tutorial

Before beginning this section, please refer to a bullet connector soldering [tutorial](https://youtu.be/3oBy-jV9ajE).    

Note: You can use any setup to hold the bullet connector, so long as the setup is not thermally conductive. Also, if you have trouble soldering the bullet connectors, you may need to use a smaller soldering iron tip. Wait at least 15 minutes or longer for the soldering iron to completely cool down after unplugging before attempting to swap the soldering iron tip.

### Strip and Tin the ESC power wires

1. Strip about 5mm from the ends of the red and black wires on each ESC

1. Tin the red and black wires on each ESC

### Solder the socket bullet connectors to the ECS wires

For each ESC:

1. Solder a socket bullet connector to the end of each of the 3 ESC wires (i.e. red, yellow, blue).

1. Put a heat shrink over each solder joint. For socket connectors: the heat shrink should cover the solder joint on one end and run the entire length of the bullet connector. Apply heat to shrink the heat shrink.

<figure>  
    <figcaption>Put Heat Shrinks on Socket Bullet Connectors</figcaption>
    <figure>
        <figcaption>Socket Bullet Connectors on ESCs</figcaption>
        <img style='width:250px' src="photos/bullet_connectors_in_esc.jpg"/>
    </figure>
    <figure>  
        <figcaption>Socket Bullet Connector with Heat Shrinks</figcaption>
        <img style='width:250px' src="photos/ESC_bullet_connectors_heat_shrinked.jpg"/>
    </figure>
</figure>  

## Motor bullet connectors

### Strip the motor wires

1. Strip about 5mm from the ends of the three black wires on each motor

### Tin the motor wires

1. Tin the ends of the three black wires on each motor

### Solder the plug bullet connectors to the motor wires

For each motor:

1. Solder a plug bullet connector to each of the motor's wires.

1. Put a heat shrink over each solder joint. For male connectors: the heat shrink should cover the solder joint on one end and run only the short length of the cylindrical part. Apply heat to shrink the heat shrink.

<figure>  
    <figcaption>Put Heat Shrinks on Plug Bullet Connectors</figcaption>
    <figure>
        <figcaption>Plug Bullet Connectors on Motor wires</figcaption>
        <img style='width:250px' src="photos/motor_with_bullet_connectors.jpg"/>
    </figure>
    <figure>  
        <figcaption>Plug Bullet Connector with Heat Shrinks</figcaption>
        <img style='width:250px' src="photos/motor_bullet_connector_heat_shrinked.jpg"/>
    </figure>
</figure>     


<div class='check' markdown="1">

Visually inspect each ESC and verify that the heat shrinks are on properly; there should be no exposed wires and each heat shrink should be a tight fit.

- Visually inspect that each of the following is stripped and tinned: 4 ESCs, 4 motors

- Do a [connectivity check](https://docs.duckietown.org/daffy/opmanual_sky/out/build_multimeter.html) on the XT60 connector cable; verify there is no short between the red and black wire.

- Do a [connectivity check](https://docs.duckietown.org/daffy/opmanual_sky/out/build_multimeter.html) on each ESC; for each ESC, verify there are no shorts between any two wires you soldered.

</div>


## Solder ESCs to the PDB

An ESC (i.e. Electronic Speed Control) is a component which requires power. It takes this power and provides a variable amount of it to a motor; since a motor's RPM depends on how much power it gets, an ESC can control how fast a motor spins by controlling how much power it supplies the motor.

### Solder each of your 4 ESCs to the PDB.   

<figure>
    <figcaption>ESCs Soldered to PDB</figcaption>
    <img style='width:400px' src="photos/added_bec.jpg"/>
</figure>


Note: Do **not** solder the wires flat against the PDB - solder them at ~20&deg; angle. If you solder them flat, then you will not be able to fit the PDB into the drone frame.   


## Solder battery monitor leads to the PDB

### Solder leads to PDB

Solder the 6 inch red and black wires to the PDB. Due to limited PDB pads, you will need to solder onto another pair of wires, e.g. BEC wires. The red wire should connect to a positive (+) pad and the brown wire should connect to a negative (-) pad.

Note: these wires are soldered so they go across the PDB, toward where the flight controller will be mounted. Also, please ignore that in this photo, the PDB is in the drone frame.

<figure>
    <figcaption>Battery Monitor Lead Soldered to PDB</figcaption>
    <img style='width:300px' src="photos/battery-wires.png"/>
</figure>


Note: While trying to solder on these wires, you may accidentally unsolder the existing wires from the PDB. We recommend temporarily holding down the existing wires with long-nose pliers, tape, or helping hands.  


## Solder to the flight controller

### Solder the pins to the flight controller

Solder the short edge of the straight pins to the flight controller.

Note: Be sure that direction you solder the pins into the board is exactly as shown in the images

<figure class="flow-subfigures">  
    <figcaption>Solder FC Pins</figcaption>
    <figure>
        <figcaption>View 1</figcaption>
        <img style='width:250px' src="photos/fc-view-1.png"/>
    </figure>
    <figure>  
        <figcaption>View 2</figcaption>
        <img style='width:250px' src="photos/fc-view-2.png"/>
    </figure>
</figure>

### Solder the battery monitor leads to the flight controller

Tin and solder the battery leads to the flight controller as shown in the image

<figure>  
    <figcaption>View 2</figcaption>
    <img style='width:250px' src="photos/battery-leads.png"/>
</figure>


## Attach parts to drone frame

This section will cover attaching the first set of items to the drone frame.

Before beginning, verify the PDB is completely soldered with all necessary parts (as covered in previous sections).

Note: the flight controller is not shown in these images; however, don't be alarmed that your build is incorrect. For now, just move the flight controller as you are working so it is not in the way. In the next section, you will attach the flight controller to the drone frame.

For reference, here are the motor directions with respect to the frame:

<figure>
    <figcaption>Motor Directions on Drone</figcaption>
    <img style='width:400px' src="photos/motor_directions.png"/>
</figure>

### Materials

Gather the following:

- Drone frame
- Completed PDB
- 4 motors (2 CW, 2 CCW)
- Velcro
- 4 standoffs
- 12 black screws (in motors box, **not** drone frame box)

### Align the frame

Place the drone frame on a flat surface so that the back is facing you.

<figure>
    <figcaption>Orientation of Drone Frame</figcaption>
    <img style='width:350px' src="photos/drone_frame_labeled_orientation.jpg"/>
</figure>

### Insert the velcro strap

Feed the velcro through the center of the drone frame. Make sure rough side is facing up.

Note: The strap in the image is from a previous hardware version. You will want this to strap down around the battery on the bottom of the drone frame. Try doing so without the battery to make sure the strap is on in the correct direction.

<figure>
    <figcaption>Velcro through Drone Frame</figcaption>
    <img style='width:350px' src="photos/velcro_in_frame.jpg"/>
</figure>

### Screw a short M3 motor bolt into each of the standoffs

Note: Although the image shows rounded top bolts, the correct ones are the [**short M3 bolts that are included with the motors**](#materials-bolt-m3). (The ones shown in the image came from the frame kit and they work fine, but the hex key doesn't fit them)

<figure>
    <figcaption>Putting Screws in Standoffs</figcaption>
    <img style='width:200px' src="photos/standoffs_with_screws.png"/>
</figure>

### Attach PDB to frame

Place the completed PDB into the center of the drone frame. For each of the 4 corner screw holes of the PDB, screw a standoff through the hole and into the drone frame. Note that the drone frame doesn't have screw grooves for the standoffs - you will create these grooves by applying downward force while screwing. Don't screw too far, since it is easy to strip the plastic. (We realize these don't hold into the frame that well, and are devising a better solution for the next hardware version.)

<figure class="flow-subfigures">  
    <figcaption>Put PDB on Drone Frame</figcaption>
    <figure>
        <figcaption>Applying Downward Force</figcaption>
        <img style='height:297px' src="photos/putting_standoffs_in_frame.jpg"/>
    </figure>
    <figure>  
        <figcaption>PDB Secured in Drone Frame</figcaption>
        <img style='height:297px' src="photos/pdb_in_drone_frame.jpg"/>
    </figure>
</figure>  

### Attach clockwise (CW) motors

Attach CW motors to the bottom-right and top-left of the drone frame, using 2 black screws for each attachment.

<figure class="flow-subfigures">  
    <figcaption>Attaching CW Motors</figcaption>
    <figure>
        <figcaption>Top View</figcaption>
        <img style='height:297px' src="photos/attach_cw_motors_to_frame_inked.jpg"/>
    </figure>
    <figure>  
        <figcaption>Bottom View</figcaption>
        <img style='height:297px' src="photos/motor_bottom.png"/>
    </figure>
</figure>  

### Attach Counter-Clockwise (CCW) Motors

Attach CCW motors to the bottom-left and top-right of the drone frame, using 2 black screws for each attachment.

<figure class="flow-subfigures">  
    <figcaption>Attaching CCW Motors</figcaption>
    <figure>
        <figcaption>Top View</figcaption>
        <img style='height:297px' src="photos/attach_ccw_motors_to_frame_inked.jpg"/>
    </figure>
    <figure>  
        <figcaption>Bottom View</figcaption>
        <img style='height:297px' src="photos/motor_bottom.png"/>
    </figure>
</figure>  

### Connect the Motors to the ESCs

For each motor, connect its plug bullet connectors to the socket bullet connectors of the ESC in the motor's corner (e.g. top-left motor connects to top-left ESC). Any connection order will suffice for now, as you will be able to change them in a latter phase.

<figure>
    <figcaption>Connecting Bullet Connectors</figcaption>
    <img style='width:350px' src="photos/connecting_bullet_connectors.jpg"/>
</figure>
