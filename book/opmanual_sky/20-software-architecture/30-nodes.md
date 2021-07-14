# Nodes {#ros-nodes status=ready}

This section elaborates on all of the ROS nodes that run on your drone to make it fly autonomously. These are described in the order in which they appear in pi.screenrc.

## \`0: roscore
Starts up a ROS master to allow the nodes to find eachother.

## \`1: Mode Controller
Mode controller controls what mode the drone should be in based on the user input and on safety checks. For example, if any of the heartbeats stop publishing, the mode controller disarms the drone. You will need to start this node explicitly after starting up a new screen.

* Python script: mode_controller.py
* Hardware interfacing: None
* Publishers:
    * '/pidrone/commanded/mode'
* Subscribers:
    * "/pidrone/mode"
    * "/pidrone/desired/mode"
    * "/pidrone/battery"
    * "/pidrone/heartbeat/infrared"
    * "/pidrone/heartbeat/web_interface"
    * "/pidrone/heartbeat/pid_controller"
    * "/pidrone/heartbeat/flight_controller"

## \`2: Command Line Interface
Command Line Interface is a text-based UI that allows you to control the drone. You will still need to connect to the drone using the web interface so that the web_interface heartbeat is publishing.

* Python script: command_line_interface.py
* Hardware interfacing: None
* Publishers:
    * "/pidrone/desired/mode"
    * "/pidrone/desired/pose"
    * "/pidrone/desired/twist"
    * "pidrone/reset_transform"
    * "pidrone/position_control"
    * "/pidrone/map"
* Subscribers:
    * "/pidrone/position_control"

## \`3: Flight Controller
Flight Controller interfaces with the flight controller board to extract the IMU and battery data, and to publish the roll, pitch, yaw, and throttle commands which are used to control the attitude of the drone. The Flight controller listens to the mode controller over the desired_mode topic to know what if it should listen to the fly_commands from the pid_controller which tell give it values to fly. If the mode is "ARMED" or "DISARMED", the flight controller node sends static command values, but if the mode is "FLYING", then the node sends the fly_commands to the flight controller board.

* Python script: flight_controller_node.py
* Hardware interfacing: flight controller board
* Publishers:
    * "/pidrone/imu"
    * "/pidrone/battery"
    * "/pidrone/mode"
    * "/pidrone/heartbeat/flight_controller"
* Subscribers:
    * "/pidrone/commanded/mode"
    * "/pidrone/fly_commands"

## \`4: PID Controller
The controller node could be any controller which takes the current position of the drone and attempts to drive the drone to the desired position. We use a widely used feedback controller known as a PID. You'll be implementing this in a project later on. In short, the PID controller uses the error betweent the desired and current values to compute roll, pitch, yaw, and throttle values to send to the flight controller.

* Python script: pid_controller.py
* Hardware interfacing: None
* Publishers:
    * "/pidrone/fly_commands"
    * "/pidrone/position_control"
    * "/pidrone/heartbeat/pid_controller"
* Subscribers:
    * "/pidrone/state"
    * "/pidrone/desired/pose"
    * "/pidrone/desired/twist"
    * "/pidrone/mode"
    * "/pidrone/desired/mode"
    * "/pidrone/position_control"
    * "/pidrone/reset_transform"
    * "/pidrone/picamera/lost"

## \`5: State Controller
State Controller subscribes to all of the sensor data and uses a filter to estimate the state of the drone. The state typically consists of the x,y,z positions and velocities, and the yaw of the drone. We've implemented several state estimators that vary in complexity. You will be implementing a state estimator that uses an Unscented Kalman Filter (UKF) in a future project.

* Python script: state_estimator.py
* Hardware interfacing: None
* Publishers:
    * "/pidrone/state"
* Subscribers:
    * "/pidrone/picamera/twist"
    * "/pidrone/picamera/pose"
    * "/pidrone/infrared"
    * "/pidrone/imu"
    * "/pidrone/reset_transform"

## \`6: Vision
The vision node interfaces with the picamera to provide velocity and position estimates. There are several vision files used to do this. `vision_flow_and_phase.py` uses the python scripts `analyze_flow.py` and `analyze_phase.py` to estimate the velocity and position of the drone using optical flow vectors and rigid transformations, respectively. These values are published for use by the state_estimator. Another vision node is 'vision_localization_offboard.py', which uses localization to provide the position of the drone to the state estimator. Others exist as well, and you will be writing vision nodes in future projects.

* Python script: vision_flow_and_phase.py
* Hardware interfacing: Pi camera
* Publishers:
    * "/pidrone/picamera/twist"
    * "/pidrone/picamera/pose"
* Subscribers:
    * "/pidrone/state"

## \`7: Infrared
Infrade is used to interface with the analog to digital converter (ADC) which is connected to the infrared sensor. This node is used to convert the data from the ADC into usable range readings to publish for use by the state estimator.

* Python script: infrared_pub.py
* Hardware interfacing: Infrared sensor
* Publishers:
    * "/pidrone/infrared"
