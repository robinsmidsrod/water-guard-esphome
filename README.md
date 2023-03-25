# Water Guard integration with ESPHome

This repo contains documentation on how to integrate the [Water Guard remote interface WTG-35A](https://waterguard.no/remote_interface_msr/) with Home Assistant using ESPHome

## Requirements

- [Water Guard Remote Interface WTG-35A](https://waterguard.no/remote_interface_msr/)
- [ESP8266 NodeMCU](https://www.aliexpress.com/item/32656401198.html?spm=a2g0o.order_list.order_list_main.10.439d1802tDjiJX)
- Various dupont cables
- 12V power supply
- Two double WAGO blocks
- Optional: A 7-pin WAGO block if you don't want to solder ground wires together

## Usage

**BEWARE: Don't connect the USB port of the ESP8266 to your computer for programming
while you power the devices with 12V, or you will probably damage your computer's USB port.**

- The ESPHome YAML file contains the pinouts for the various outputs and inputs of
  the WTG-35A. Feel free to tweak the naming of things as needed.
- The wiring diagram in the `upstream-docs` folder shows which pins of the WTG-35A do what.
- Since this particular variant of the ESP8266 NodeMCU has a voltage regulator that
  tolerates up to 15V input power, you can use a single 12V power supply to power both the
  WTG-35A and the NodeMCU at the same time without any extra components. Since the WTG-35A
  comes with a 12V power supply, I've just used that one.
- Look at the images for details on how I connected things together.
- I soldered together all of the negative/black wires for a common ground.
- The WTG-35A uses opto-couplers inside, so all of the ports are potensial free.
- The Home Assistant device page shows how I've set it up in my home.
- The `automations` folder contains the YAML files for the automations shown. You'll need
  to adjust the device identifier in your own automations.

## Future plans

- I'm thinking that the alarm reset switch could be implemented as a `button` entity
  instead, but I haven't found the time yet to implement it.
- Would be very nice with a 3D-printed box that could contain all of this neatly.

## Warranty

This repository is informational. If you follow these instructions and break something,
I have absolutely no responsbility for your mishaps.

## Contact details

Robin Smidsrød <robin@smidsrod.no>

Or open up an issue or create a PR if you have improvements.
