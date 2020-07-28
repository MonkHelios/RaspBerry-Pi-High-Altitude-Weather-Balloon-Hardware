# Raspberry Pi powered High Altitude Weather Balloon:

<The hardware of the weather balloon or the payload section is structured as a **six layered** stack of Raspberry Pi hats.>

![Stack](https://github.com/MonkHelios/RaspBerry-Pi-High-Altitude-Weather-Balloon-Hardware/blob/master/Payload/Pictures/InkedLRM_EXPORT_825743803905478_20190919_195242457_LI.jpg)

- The first layer is a Raspberry Pi which manages operation of all other stacks and undertakes necessary processing tasks.
- To power the entire stack we have a high current DC-DC converter as a power delivery unit which accepts 1S LiPo or LiIon batteries as input and outputs a steady 5V and allows a maximum current draw of 7A.
- For telemetry and other communication purposes we are using a CC1125 based RF board.
- The next stack comprises of a GSM board for non LOS communication at lower altitudes and a GPS board for tracking the balloon and for easy retrieval. Since both of these are using the same serial channel of the Raspberry Pi, multiplexing and demultiplexing were necessary. This was facilitated by a Mux Demux board which had the ability to select a peripheral among the two.
- Finally on top of the GPS hat we have the sensor hat.

## 1. Power Delivery Board:

To run the essential hardware stacks a power delivery system more capable than a Raspberry Pi's internal power distribution was required. A design of a power distribution stack which could supply a high enough current with stability was adopted. The board was powered with a 3.7V LiIon or LiPo cell, its output was a constant 5V with a maximum allowed current of 7A. Our required peak current was 5A so we went with a 2A headroom. The design was built around the LTC1871-1 - a wide input range, current mode, boost, flyback or SEPIC controller that drives an N-channel power MOSFET and requires very few external components.

### 1.1 Schematic:

![schematic](https://github.com/MonkHelios/RaspBerry-Pi-High-Altitude-Weather-Balloon-Hardware/blob/master/Payload/Hardware/Power_(Pi_Po)/Schematics%2BDesigns/schematic.png)

### 1.2 Composite:

![composite](https://github.com/MonkHelios/RaspBerry-Pi-High-Altitude-Weather-Balloon-Hardware/blob/master/Payload/Hardware/Power_(Pi_Po)/Schematics%2BDesigns/composite.png)

### 1.3 Assembly:

![assembly](https://github.com/MonkHelios/RaspBerry-Pi-High-Altitude-Weather-Balloon-Hardware/blob/master/Payload/Hardware/Power_(Pi_Po)/Schematics%2BDesigns/assembly.png)
