# Part 4: Camera, Propellers, and Mounting Hardware Overview {#build-part4-overview status=ready}

In this section of the build, you will attach the camera, and finalize the drone assembly.

- **Part : Quantity**
- [Raspberry Pi Camera](#materials-camera) : 1
- [Pi Mount](#materials-pi-mount) : 1
- [Pi Mount Screws](#materials-pimount-screws) : 3
- [Brass Standoffs](#materials-brass-standoffs) : 2
- [CW Propellors](#materials-props) : 2
- [CCW Propellors](#materials-props) : 2
- [8mm Wrench](#materials-wrench-8mm) : 1
- [Battery Mount](#materials-battery-mount) : 1
- [Hot glue gun](#materials-misc) : 1
- [Zip Ties](#materials-zipties) : 10+

## Hardware

### Camera
The camera is used to to measure the planar position and velocity of the drone; by planar, we mean that the camera provides position and velocities in the x and y axis but not z (left and right, forward and back, but not up and down). The planar velocity of the drone is found using optical flow, which is a technique that computes the change in position between two "features" over time. A feature is a distinct group of pixels in an image that. The position of the drone is found by computing the change in position between two subsequent camera frames. The drone is also able localize the drone in a known map. This means that if you upload to the drone a photo of the surface that the drone will be flying over, the drone will be able to know where it is at within this photo, or "map." Finally, the drone is able the Simultaneously Localize And Map (SLAM) which means that it can build its own map of what it is flying over, and then localize within the map that it creates. SLAM is used on all robot vacuums that clean your house for you. Without knowing what your house looks like, the robot bumps around and remembers where its been, creating a map.

For more information about the camera, watch [these lectures](https://edge.edx.org/courses/course-v1:Brown+CSCI1951-R+2020_summer/courseware/0e3596880ec446d8ab63df427e02e9c4/ccd9eede2624475b91ce4b55ee51ce87/?activate_block_id=block-v1%3ABrown%2BCSCI1951-R%2B2020_summer%2Btype%40sequential%2Bblock%40ccd9eede2624475b91ce4b55ee51ce87) (you will need to create a free EdX account to view the material)

<figure>
     <figcaption>Camera</figcaption>
    <img src="photos/new-picam.png" width="300"/>
</figure>

### Propellors
The propellors are what provide lift for the drone and allow it to fly. When the propellor spins, it creates a pressure difference between the air above and below it. The pressure below the propellor is greater than the pressure above, generating lift. Another way to think about how a drone prop works is that it pushes air down and the opposite reaction is the thrust lifting the drone up.

Drone are specified by three numbers. The propellors on your drone are 5 x 4 x 3. The first number, 5, is the size and it indicates the length of the blades; measured from the center to the tip. The second number, 4, is the pitch and it is a theoretical measurement of how far the propellor would travel through the air in one revolution. A larger pitch means more air is moved, so the propellor travels further, while a smaller pitch would move less air and therefore move less. The last number, 3, is the number of blades.

<figure>
     <figcaption>Propellors</figcaption>
    <img src="photos/new-props.png" width="300"/>
</figure>


## Build Progress

After completing this section, your build will match the diagram below. Compare this diagram to the [completed drone diagram](#diagram-complete) to see how what you're doing now fits into the final result.

<figure>  
  <figcaption> Diagram for Build Part 4 </figcaption>
  <img style='width:400px' src="photos/diagram-completed.png"/>
</figure>

The camera provides information about the position and velocity of the drone, which is used to hold the drone in one place, or move it at a specific velocity or to a specific position. After this build part, you will be ready to fly!
