# Connecting a "dumb" doorbell to Home Assistant
I have a very basic doorbell, it's one of the cheapo ones you can buy for a couple of bucks.

It's the type where you have a normally open pushbutton outside which is connected via two wires to the doorbell/buzzer unit.

The unit is powered by two 1.5 AA which means I have 3v on hand.

I had an unused Sonoff Zigbee magnet sensor, these things are basically all the same, the magnet is normally open and when it is magnetised by the opposing element it goes closed, completing the circuit.

I have made the following simple modifications:

* Connected the two sides of the magnet sensor to the two wires coming from the outside pushbutton
* Connected the two poles of the battery compartment to the zigbee device (3v remember)

Now, when the button is pressed, the magnet sensor circuit is closed momentarily, this causes the Zigbee device to flash Closed.
The rest is a Home Assistant Automation based on the magnet sensor, this is the same as any other door/windor sensor automation.

```
platform: state
entity_id:
  - binary_sensor.doorbellmagnet_contact
to: "off"
```

![image](https://user-images.githubusercontent.com/10833368/235573560-204f5086-5732-4723-ae91-0f699e9bb928.png)
![image](https://user-images.githubusercontent.com/10833368/235573598-2f80bf10-879d-40e0-8a4b-5737bc9214ca.png)
