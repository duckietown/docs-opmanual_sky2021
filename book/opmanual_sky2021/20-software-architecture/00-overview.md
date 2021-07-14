# Software Architecture {#part:software-architecture status=ready}

In this section of the textbook, we will introduce you to the software
of the drone, and how it interacts with the hardware you put together
in the build project. First, we will offer a brief explanation of the
<a href="http://ros.org">Robot Operating System (ROS)</a>, and the ways its tools are specifically
implemented on the DuckieDrone to create the programs that allow the drone
to fly autonomously. Next, we will look at a diagram which provides a
visual overview of how all of the components needed to fly the drone
fit together. Finally, we will describe each ROS node that is running
while the drone flies to convert the data from the sensors into
controls to the acuators (the four motors). In doing so, we will look
closely at each component to understand its purpose, where it exists
in the code, what ROS topics it interacts with, and what hardware it
interfaces with.
