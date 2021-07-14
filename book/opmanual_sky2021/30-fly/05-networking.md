# Network Configuration {#network status=ready}

There are several options for your Raspberry Pi's network structure
with different tradeoffs.  Here we give a summary of different
options.

## Drone as Access Point

The drone comes by default configured to act as an Wifi access point,
and you connect your base station to the drone's wifi as a client.  It
will use hostapd to give your base station an IP address via DHCP.
This configuration is the default configuration out of the box.  It
has the advantage that your drone can work anywhere, without any
existing wifi network, and without requiring you to change any
settings on the drone before connecting to it with your base station.
It has the disadvantage that by default, the drone only has one wifi
card and no wired access when it is flying.  Thus the drone does not
have access to the internet in this configuration.  Nor does your base
station have internet access while connected to the drone, unless you
have provide an alternative means.  For most people who use wifi to
connect to the Internet, this mode presents a problem.

You can ameliorate the internet access problem by using a wired
connection to either plug your drone into the wall, or into your base
station.  If you plug your drone into the wall, it will use DHCP to
request an IP address, and also route traffice from your base station
to the Internet and back, so both the Raspberry Pi and your base
station will have internet.  Alternatively, you can plug the drone
into your base station.  To make this mode work, you must first
configure your base station to perform internet connection sharing,
which is possible on most operating systems.  Then the drone will
obtain a DHCP address from your base station and be able to access the
internet when the base station is connected to ambiant wifi, and you
can ssh to the drone through the wired connection.

Of course, both of these solutions require an Ethernet cable to be
connected to your drone, which is problematic for flight.


## Drone in Managed Mode

A second option is to connect both your base station and your drone to
the wifi network.  Your drone will be in AP Managed mode, and obtain
an IP address and internet access in the same way as your base
station.  You can then use this wifi network to connect between the
base station and the drone.  The advantage of this approach is that
both machines have internet access, wirelessly.  The disadvantage is
that the drone must be configured to access the ambient network, with
its SSID and password, and this network must allow direct connections
between two clients on the network.  This network must be available
and working in order to fly.  Furthermore you must find the drone's IP
address from your base station, unless you want to plug in a keyboard
and monitor into the Pi to find out its IP address.

### Managed Mode Configuration

These instructions will save your networks credentials (network name, password)
across reboots. You only have to follow these steps the first time you wish to
connect to a new network.

**On your base station:**

1. connect your base station to the `defaultdrone` wifi network

2. browse to your drone's code server at the default ip address and port 8081: [192.168.42.1:8081](192.168.42.1:8081)

3. open a new terminal: Menu > Terminal > New Terminal

**In the terminal:**

1. navigate to the networking directory in the pidrone_pkg: `roscd pidrone_pkg/networking`

2. run the bash script to generate a wpa_supplicant.conf file for your network: `./generate_wpa_supplicant_conf.sh`

3. fill in the prompt for your networks ssid (your networks name) and press enter

4. fill in the prompt for your networks password and press enter. Note that you will not see anything happening when you are typing the password-- this is a security feature.

5. after the script finishes, move your newly created wpa_supplicant.conf file to the /etc/wpa_supplicant directory: `sudo mv wpa_supplicant.conf /etc/wpa_supplicant/`. Note that you will need to enter the user password when using `sudo`. By default, this is `bigbubba`

### Switching to Managed Mode

These instructions need to be followed every time you wish to switch your drone
to managed mode. The drone always starts up as a WiFi access point so that you
will always be able to connect to your drone, even if you are not in range of the
network you usually connect to.

**In the terminal:**

1. navigate to the networking directory in the pidrone_pkg: `roscd pidrone_pkg/networking`

2. run the bash script to connect your drone to the wifi network configured previously: `./connect_to_user_wifi.sh`

3. connect your base station to the same network that your drone is now connected to

4. reconnect to your drone

For this step, you can try to use your drone's hostname to connect; however this may not work. If using the hostname does not work for you, you will need to find your drone's IP address. Follow the instructions in [this article](https://www.raspberrypi.org/documentation/remote-access/ip-address.md) to find your drone's IP address. Note that your drone's hostname is `duckiesky-drone`, not `raspberrypi` which is used in the article.

a) First, try connecting via hostname:

browse to your drone's code server: [duckiesky-drone.local:8081](duckiesky-drone.local:8081)

b) If connecting via hostname did not work, then connect via IP address: ip_address:8081

Note: If you are connecting over ssh instead of the terminal in the code server, you will need to specify the username. For example, `ssh duckiesky@duckiesky-drone.local` or `ssh duckiesky@ip_address`
