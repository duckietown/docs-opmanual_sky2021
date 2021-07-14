# Part 1: Power Distribution and Raspberry Pi Checkpoint {#build-part1-checkpoint status=ready}

**Expected Time**: 10 minutes

## Connect to the Pi for the first time

You will now verify that the SD card is working properly by connecting to your Pi for the first time. The SD card is configured to serve a text editor that gives you access to all of the files on the Pi. You won't be making any changes at this point, you will just be verifying that you can connect to the server.

### Power up your drone build

Plug the battery into the XT60 connector

### Connect to the drone's wifi network

On your base station, connect to the network labelled **defaultdrone**. The wifi password is **bigbubba**

Note: At this point you will lose internet access, because you will be connected to the Pi's network. You can disconnect and reconnect to the network at any point without causing issues on the Pi.

### Browse to your drone's code server

In a web browser on your base station, browse to [192.168.42.1:8081](192.168.42.1:8081). The first 8 numbers (192.168.42.1) are the IP address of the drone, and the numbers after the colon (8081) is the port number that the text editor is served to

### Checkoff

If the link does not show an error, then your SD card is correctly flashed! The screen you are looking at is a text editor that allows you to edit the code on your drone. Any changes you make in this editor will be automatically saved to the drone. You can browse around the text editor and files if you'd like. You will be learning more about this interface in a later lesson.

## Change your WiFi SSID

At this point, if student A is working on their drone in the same room as student B, both students would not be able to connect to their drone.

Q: Can you figure out why?

A: There can't be multiple WiFi networks named "defaultdrone". The SSID must be changed for each drone so that there aren't multiple networks with the same name.

Now, you will change the name of your WiFi SSID. Follow the steps below along with [this instruction video](https://drive.google.com/file/d/1HvtKNhsjG_dQt2edeJ40WdhmyO649ZOd/view?usp=sharing) to change the SSID

### Launch a terminal

1. In the code server in your browser, find the the menu button in the top left corner (it looks like three horizontal lines)

1. Click the menu button, then click Terminal > New Terminal

1. A small window will open up in the bottom of your screen.

### change the SSID

1. In the terminal, type: `sudo nano /etc/hostapd/hostapd.conf`

1. when prompted, type `bigbubba` and press enter (you will not see the password typing as a security feature)

1. Use the arrow keys on your keyboard to move the cursor to the end of the second line of this file that says: `ssid = defaultdrone`

1. Delete the phrase `defaultdrone` and type a new network name for your drone

### Save and exit

1. While pressing down the control (ctrl) key, press the `x` key

1. Type `y` and press enter to save and exit

### Checkoff

Disconnect and reconnect the battery to your drone. On your base station, look for the available WiFi networks. If the file was edited properly, you will now see your new network name instead of "defaultdrone"

Congrats on finishing Build Part 1!
