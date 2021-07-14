# Part 2: IR Sensor Instructions {#build-part2-instructions status=ready}

**Expected Time**: 2 hours


## Solder Pins to the ADC

### Identify the top and bottom

The top of the ADC has the labels near the holes, "V," "G," "SCL," etc.

The bottom of the ADC says "ADS1115/ADS1015"

<figure>
  <figcaption>Bottom of ADC</figcaption>
  <img style='width:250px' src="photos/new-adc.png"/>
</figure>

### Insert pins

Insert the **short** ends of the pins into the holes in the **bottom** of the ADC and clamp the ADC with the helping hand as shown in the image below.

Note: The ADC shown is from a previous hardware version. For your ADC, the helping hands will be on the left side and the pins will be on the right

<figure>  
   <figcaption>Helping hands hold the ADC for soldering</figcaption>
   <img style='width:250px' src="photos/adc_pins_soldered_2.jpg"/>
</figure>

### Solder

Solder the pins on the **top** of the ADC using the [through-hole soldering technique](#prereq-solder-through-hole)

<figure>
  <figcaption>Top View of ADC after soldering</figcaption>
  <img style='width:250px' src="photos/new-adc-pins-soldered.jpg"/>
</figure>


## Solder the ADC to the Pi Hat

### Detach the Pi Hat from the Pi.

Gently lift the Pi Hat near the pin header to detach.

### Solder the ADC to the Pi Hat

Following the image below, insert the ADC into front of the Pi Hat. Then, flip the Pi Hat over so you can solder the pins on the back of the Pi Hat using the [through-hole soldering technique](#prereq-solder-through-hole)

Note: Be sure to solder the ADC to the correct location on the Pi Hat. Use the location of the slot in the Pi Hat to help you align the ADC.

<figure class="flow-subfigures">
<figcaption>ADC soldered to Pi Hat</figcaption>
   <figure>
       <figcaption>Diagram</figcaption>
       <img style='width:150px' src="photos/new-adc-soldered.png"/>
   </figure>
   <figure>  
       <figcaption>Actual</figcaption>
       <img style='width:150px' src="photos/new-adc-soldered-real.jpg"/>
   </figure>
</figure>   

### Solder the ADC wires

Following the diagram below, insert a wire into the correct hole on the front of the Pi Hat. Then, flip the Pi Hat over to solder the wire on the back of the Pi Hat using the [through-hole soldering technique](#prereq-solder-through-hole).

Note: Recall that the Pi Hat is a breadboard, so it has rails. The wires you solder do not need to go into exact holes; each wire just needs to go into a hole on the same rail as its corresponding ADC pin. You can look at the back of the Pi Hat and see the metal connections between holes. You can also do a connectivity check with the multimeter if you have doubts about which holes are connected.

1. Use a small piece of **red** wire to connect the **V** pin of the ADC to the 5V rail.

1. Use a small piece of **black** wire to connect the **G** pin of the ADC to the the GND rail

1. Use a small piece of **blue** wire to connect the **SCL** pin of the ADC to the hole labelled **SCL** on the Pi Hat

1. Use a small piece of **green** wire to connect the **SDA** pin of the ADC to the hole labelled **SDA** on the Pi Hat


Remark: For the wires, we use the colors: red, black, green, and blue. However, any color wires will work.

<figure>
   <figcaption>ADC Wires soldered to Pi Hat</figcaption>
   <img style='width:300px' src="photos/new-adc-wired.png"/>
</figure>


<div class='check' markdown="1">

Do a [connectivity check](https://docs.duckietown.org/daffy/opmanual_sky/out/build_multimeter.html) on the Pi Hat; verify:

- There is **NO** electrical connection (short) between the 5V and GND rails.

- There is **NO** electrical connection (short) between the SCL and SDA wires

- There are **NO** stray wire strands that are connecting adjacent pins, especially between 5V and GND (see image below)

</div>

<figure>
   <figcaption>BAD: Wire strands causing shorts</figcaption>
   <img style='width:150px' src="photos/pi-hat-soldered-bad.jpg"/>
</figure>

## Prep the IR Sensor Wire

### Trim

Cut the black plastic piece off the end of the IR sensor cable


<figure class="flow-subfigures">
<figcaption>IR sensor cable before and after</figcaption>
   <figure>
       <figcaption>Pre-cut</figcaption>
       <img style='width:150px' src="photos/ir_cable_precut.jpg"/>
   </figure>
   <figure>  
       <figcaption>Post-cut (not yet stripped)</figcaption>
       <img style='width:150px' src="photos/ir_cable_postcut.jpg"/>
   </figure>
</figure>   

### Strip and Tin

1. Strip about 5mm off of the newly-exposed ends of the IR sensor wire

1. Twist and Tin the IR sensor wires. Do not put too much solder, as the wires must fit through the holes in the Pi Hat

## Solder the IR Sensor Wires

### Solder the IR Sensor Wires to the Pi Hat

Following the diagram below, insert a wire into the correct hole in the front of the Pi Hat. Then, flip the Pi Hat over to solder the wire on the back of the Pi Hat using the [through-hole soldering technique](#prereq-solder-through-hole).

1. Solder the **red** IR Sensor Wire to the 5V rail

1. Solder the **black** IR Sensor Wire to the GND rail

1. Solder the **yellow** IR Sensor Wire to any hole in the same row as **A0** on the ADC

<figure>
   <figcaption>ADC Wires soldered to Pi Hat</figcaption>
   <img style='width:300px' src="photos/new-adc-final.png"/>
</figure>


<div class='check' markdown="1">

Do a [connectivity check](https://docs.duckietown.org/daffy/opmanual_sky/out/build_multimeter.html) on the Pi Hat; verify:

- There is **NO** electrical connection (short) between the 5V and GND rails.

</div>

## Reattach the Pi Hat to the Pi

Reattach the Pi Hat to the Pi by aligning the GPIO pins with the pin header and pressing down. Refer to [part 1](#build-part1-attach-pihat) for detailed instructions on how to attach the Pi Hat.
