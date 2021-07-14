# Part 3: Motors and ESCs Checkpoint {#build-part3-checkpoint status=ready}

**Expected Time**: 20 minutes

## Verify the wiring is correct

### Visually inspect the drone to verify the following:

  - All red wires connected to the PDB are connected to positive (+) pads

  - All black wires connected to the PDB are connected to negative (-) pads

  - The wires on the IN side - **NOT** the OUT side - of the BEC are soldered to the PDB

  - For the battery monitor lead: the red wire is connected to a positive (+) pad while the brown wire is connected to a negative (-) pad

### Do a [connectivity check](https://docs.duckietown.org/daffy/opmanual_sky/out/build_multimeter.html) on the PDB; verify there is:

  - a short between any positive (+) pad and any other positive (+) pad

  - a short between any negative (-) pad and any other negative (-) pad

  - **no short** between any positive (+) pad and any negative (-) pad

### Do a [DC voltage check](https://docs.duckietown.org/daffy/opmanual_sky/out/build_multimeter.html) on the PDB;

**ONLY** if the connectivity check passed, plug in a 12V battery and verify there is:

  - ~0V between any positive (+) pad and any other positive (+) pad

  - ~0V between any negative (-) pad and any other negative (-) pad

  - ~12V between any positive (+) pad and any negative (-) pad.

Note: If the battery is X volts instead of 12 volts (e.g. 10), then the multimeter will show X volts instead of 12 volts.

### ESC check

**ONLY** if the DC voltage check passed, re-connect a battery to your drone and verify the following:

  - The ESCs emitted a quick succession of 3 beeps.

  - The bottom of the drone frame is illuminating, due to the LEDs on the bottom of the PDB.
