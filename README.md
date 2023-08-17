# esphome-autovorm
ESPHome Integration for control of Technivorm Moccamasters

## Equipment
You will need an ESP32 device and two relays. I suggest the M5 Atom Lite with the 2-channel SPST relay unit.
You will also need wires and connectors to tap into the Moccamaster's power and hotplate circuit.

[M5 Atom Lite](https://shop.m5stack.com/products/atom-lite-esp32-development-kit)

[2-channel SPST Relay](https://shop.m5stack.com/products/2-channel-spst-relay-unit)

[Suggested leads for power connection](https://www.amazon.com/gp/product/B01CL3M7A4/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&th=1)

## Wiring the Moccamaster
The Moccamaster power switch has 5 connection terminals. You want to disconnect the right most two connections, remove the spade connectors, and attach your new leads to some new spade connectors. The hot plate should have one white wire that goes to the negative side of its switch. Just cut and strip that wire for connection to Relay 2.

![leads](./images/leads.png)

![connection](./images/connected.png)

## Installing Autovorm
Connect the M5 Atom Lite to your computer and note the device name that shows up under /dev (mine was ttyUSB0). Get the latest esphome docker image with `sudo docker pull esphome/esphome` and run the below command to install on the ESP32. 

`sudo docker run --rm -v "${PWD}":/config --device=/dev/ttyUSB0 -it esphome/esphome run autovorm.yaml`
