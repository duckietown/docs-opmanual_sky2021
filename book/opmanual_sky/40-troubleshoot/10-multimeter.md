# Multimeters {#part:multimeter}

Using a multimeter effectively is an essential part of debugging any
electronics project.  Achieving multimeter mastery is beyond the scope
of this course, but there are two modes that you should be aware of
and use as part of your work.

## Checking for Shorts

Most multimeters have a mode where they will beep if the two probes
are connected via a circuit.  You can use this mode to check that two
outputs on your drone that should be connected are connected.  Do this
checking with the drone powered off.  For example, verify that the PI
GPIO pin that is reading the Adafruit input is connected to the
correct output port on the Adafruit board.  And verify that the 5V
output from the BEC is connected to the 5V input on the Pi.  And then
verify that the power pad on the power distribution board is NOT
connected to the ground pad on the same board.

## Checking Voltage

When the drone is powered on, you can check each part of the drone for
shorts.  Voltage is a measure of relative electric potential between
two different parts of the project.  For example, verify that the
power pad and ground pad on the PDF show a 12 volt difference.  (It's
okay if it varies between 11 and 12.5 volts, depending on the state of
your battery sharge.)  Verify that the Pi's power and ground pins show
a 5 volt difference.  Verify that the Adafruit board's power and
ground pins show a 5 volt difference as well.
