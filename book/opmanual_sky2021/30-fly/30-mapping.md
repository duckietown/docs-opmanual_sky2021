# Mapping and Localization {#mapping status=ready}

The Duckiedrone can perform localization with a map created from an
image, as well as the ability to run SLAM (online or offline).  Both
methods use the drone's camera to produce a pose estimate, but
localization requires a map of the environment before hand,
represented as images stitched together (map.jpg) whereas SLAM builds
a map of the environment as it runs. SLAM does not run well online
even with a fast base station. However it gives good performance when
run offline to create a map, and then later using that map to
localize.

These scripts replace the `vision_flow_and_phase.py` script that does
velocity and position control.  The reason is that we save time and
memory by avoiding sending images to different nodes on the Pi and
instead do all processing in a single node that directly connects to
the camera.

The recommended workflow is to first run SLAM to create a map offline.
Then after creating the map, run localization with the saved map to
give the drone a global position estimate.

## SLAM

The recommended mode for SLAM is to run it offline; there is not
enough compute even offboard to run it during flight.  It may be
possible to run SLAM online with additional optimization or by
rewriting the algorithm in C++; for this reason we include
instructions for running online as well.  Note that if you run
anything offboard, ROS must be installed on the offboard machine.
Running offboard is not required to run SLAM; however it may be
significantly faster to create the map if you use a fast base station.

**Offline SLAM:**

**Save Flight Data**: The first step to offline SLAM is to fly the drone
and collect image data to build the map. To do this, run 
'vision_localization_offboard.py --offline' which will save the image
data from a flight to 'flight_data.txt.' Press 'r' to toggle recording 
the data. After the second press, the script will write the data to
the file and will let you know when it is done (this may take ~10 min
for a longer flight).

**Build a Map**: This can be done either offline or online. Run 
"offline_slam.py" which will look for the "flight_data.txt" file
and save a map to a file called "map.txt."

**Localize**: Currently this only works onboard, but we will add
offboard support soon. Make sure your "map.txt" file is in the 
scripts folder and run "vision_localization_onboard.py --read" which
will perform localization over the map created by SLAM. Press "r" to 
restart the localization.

**Online SLAM**
Online SLAM runs but not in real time, even offboard.  Therefore we do
not recommend it until and unless we make it fast enough to run in
realtime.  However we are including instructions in case someone wants
to try!  For online slam:

**Offboard:** run `vision_localization_offboard.py` on the pi. On the
  offboard computer run `offboard_slam.py`. Press `r` to toggle SLAM.

**Onboard:** run `vision_localization_onboard.py --SLAM` on the
  pi. Press `r` to toggle SLAM.


## Localization with a Stitched Map

These instructions describe how to create a stitched image of a map
with your cell phone or other camera.  Once you have created a map,
you can use it to localize.

Take photos of the new map with a cell phone or other camera. Take
  them at a height of $25\mbox{cm}$ pointed downward at the workspace.
  Use an image stitching software to generate the map. We recommend
  [auto-stitch](http://matthewalunbrown.com/autostitch/autostitch.html)
  or [hugin](http://hugin.sourceforge.net/). Replace map.jpg with your
  new map and change the following four parameters in
  `offboard_localization.py`, `onboard_localization.py`, and
  `localization_helper.py`: MAP_PIXEL_WIDTH, MAP_PIXEL_HEIGHT,
  MAP_REAL_WIDTH, MAP_REAL_HEIGHT. You may need to resize the image to
  be smaller if it is too large.


**Onboard:** run `vision_localization_onboard.py` on the pi. You must fly over the area captured in map.jpg. Press `r` in the web interface to toggle localization.

**Offboard:** run `vision_localization_offboard.py` on the pi and `offboard_localization.py` on the remote computer. You must fly over the area captured in map.jpg. Press `r` to toggle localization.
