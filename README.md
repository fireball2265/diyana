Super lightweight OS for the Hare Technologies Diana Nerf Blaster

This started out with an idea to make the Diana more suitable for friendly games rather than anything super competitive, 
but quickly snowballed into a full rebuild of the electronics to allow full customisation. The code could be adapted to 
suit any blaster of your choosing - I just happen to really like the form factor of the Diana so that's where I started.


Hardware requirements:

HT Diana
2 x 20a ESC's - https://www.amazon.co.uk/dp/B0DLZGK1WN

IRFZ44N Mosfet - https://www.amazon.co.uk/dp/B0D69Y4GKW

Raspberry Pi Pico W (make sure you get the W for the wireless!) - https://thepihut.com/products/raspberry-pi-pico-w (only tried with v1, may be compatible with the Pico 2W)
Misc wire / heat shrink etc


You can set your own WIFI SSID and password in the code. You can also customise the pins if you've moved anything around
wiring up the blaster. I've mostly used the closest pins to the various switches so it should be fairly straight forward.

esc1Pin = 28 (output to signal wire of ESC)

esc2Pin = 6 (output to signal wire of ESC)

solenoidPin = 20 (output to gate of solenoid)

triggerPin = 14 (input from trigger)

modePin1 = 10 (input from 3 pos switch)

modePin2 = 11 (input from 3 pos switch)

ledPin = 1 (output to LED)

ledControlPin = 17 (input from 2 pos switch)

At the moment the "rage mode" switch from the original blaster simply toggles the LED on and off. This is a placeholder
in the code to add that at a future point (or you can make it do something compeltely different, your choice!)

Inputs are set to trigger when the pin is pulled low, so the common wires for the trigger and 2 switches are wired to
the various ground pads around the board.

Once everything is wired up, plug in a battery and you're off to the races. The Pico should set up a new Wifi network
for you to connect to. Once everything is connected, go to your browser and type in http://192.168.42.1. The site should
work fine on desktop and mobile. 

Please note for first use the default settings will be -1 so you need to configure them (see defaults below)


Basic settings and remote firing via a web UI:

Burst - Fires the current burst setting as if the trigger is pulled (default 1 unless changed)
Mag Dump - Fires 15 shots full auto with the current settings

Motor Speed/Power (% - 0-100)

Spin up delay (depends on battery / ESC / etc - suggest starting with 300ms)

Solenoid trigger time (as above, start with 50ms)

Wait time after firing (as above, start with 50ms)

Burst Amount (Choose the number of shots per burst, or 1 for single shot) 

Full auto timeout (Adds a timeout on full auto to stop the blaster after a set time period - suggest 2000ms)
