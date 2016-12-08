Raspberry PI iC880A and LinkLab Lora Gateway Shield
===================================================

<img src="https://raw.githubusercontent.com/ch2i/iC880A-Raspberry-PI/master/pictures/RPI-Lora-Gateway-mounted.jpg" alt="Full stack">     

At the begining this shield has been created to help wiring between Raspberry PI and ISMT [iC880A][10] LoraWan concentrator Gateway (SPI version) and to be able to put the whole thing into a outdoor enclosure such as this [one][15].

Then I decided to add some funky stuff like:

- Footprint for [iC880a][10] ISMT LoraWan concentrator (main goal)
- ~~Can be also used between LinkLabs [board][11] and Raspi~~
- I2C and Grove connectors to be able to add internal/external sensors such as BME280, SI7021 or HTU21D
- Footprint for DC/DC step down if you want to do some simple [POE splitter][16] to power the whole thing thru a network cable or any power 
- Footprint for a simple Lora module such as RFM95 that can be used a Single Channel Gateway or also act as a Lora Node
- Power with DC Barrel connector and terminal block
- Four visual GPIO Led
- Footprint for DHT1x Temperature/Humidity sensors
- Easy to build and solder, 0805 or PTH components
- Holes to fix board on enclosure or other support

Detailed Description
====================

No specific documentation for now, it's just a kind of wiring helper, please see Gateway section on [TTN Wiki][13] and also on [TTN Forums][14] for more information on these gateways.

You can power the board with 5V going to Raspberry PI USB power directly, in this case use a descent power supply.
You can also use "basic" POE with injector and splitter, this is what I do to oustide (I inject 12V) and use the DC Barrel, in this case I put D4 and a DC/DC Step down calibrated to 5V (**do calibration before beforre pluging any boards/devices because default DC/DC output can be over 5V can fry all your boards**)

If you need to use sensors you can check out these [examples][12], they're just awesome, I'll post examples as soon as I get all working.

If you use linklabs board you can use these [version][2] of packet_forwarder, it has been modified to drive LED of linklabs boards and PPS modem line.

Installation
=============

No specific documentation for now, it's just a kind of wiring helper, please see Gateway section on [TTN Wiki][13] and Installation is quite easy but as the plate need to go over RPI network and USB connector, you need to use a 2x20 Raspberry PI connector such as [this one][25] form adafruit. You can also find some on ebay.

This specific version of [poly_packet_forwarder][30] for Raspbery PI use bcm2835 library, you need to install it before anything. See http://www.airspayce.com/mikem/bcm2835/

For driving specific onboard LED with packet forwarder, please see the specific readme file of the [poly_packet_forwarder][30] to adjust you json config file.

I suggest to plug the connector into the PI to see space needed then plug the plate to the connector and start soledering one pin on each edge so the connector will be fixed, then remove plate and connector and solder all other pins.

Software Installation is straightforward, just follow the [dedicated installer][26].

### Schematic
![schematic](https://raw.githubusercontent.com/ch2i/iC880A-Raspberry-PI/master/pictures/RPI-Lora-Gateway-Shield-sch.png)  

### Boards 

**Top side**

<img src="https://raw.githubusercontent.com/ch2i/iC880A-Raspberry-PI/master/pictures/RPI-Lora-Gateway-Shield-top.jpg" alt="PCB TOP">    

**Bottom side**

<img src="https://raw.githubusercontent.com/ch2i/iC880A-Raspberry-PI/master/pictures/RPI-Lora-Gateway-Shield-bot.jpg" alt="PCB TOP">    


You can order the PCB of this board at [PCBs.io][3]. Don't worry they still have a bug with top/bottom thumbails view but final boards are okay
PCBs.io give me some reward when you order my designed boards from their site. This is pretty good, because I can use these rewards to create and design new boards and order boards for a discounted price, so if you don't care about PCB manufacturer please use PCBs.io.

### Assembled boards into nice enclosure with sensors

<img src="https://raw.githubusercontent.com/ch2i/iC880A-Raspberry-PI/master/pictures/ch2i-shield-lorawan-gateway.jpg" alt="Fully assembled and in nice enclosure with sensors">     

Sensors values en Cayenne (see [installer][26] readme for setup)
<img src="https://raw.githubusercontent.com/ch2i/iC880A-Raspberry-PI/master/pictures/ch2i-gateway-monitoring-iot.jpg" alt="Gateway Monitoring with external sensors">     


##Bill Of Material

Nothing fancy, all components are 0805 and/or PTH and can be ordered almost anywhere (digikey, mouser, radiospare, ...). 
use only what you need dependings on what you want to do. 

- ~~Adjustable DC/DC step down like this [one][18] or this [one][19]~~
- Fixed 5V DC/DC step down like this 3A [one][27] or this 1.5A [one][28] 
- LED for 4 GPIO (4/23/18/24) are 3mm PTH or 0805, color of your choice
- If you use RFM95, diode for DIO0/DIO1/DIO2 (if you want to use interrupts) are 1N4148 PTH or SOD123
- POE Splitter such as [these][16] and POE injector as this [one][17]
- Terminal blocks are 5MM spacing
- D3 is 1N400x (1N4001, 1N4007, ..) whatever you have, PTH or DO214
- DC/Barell power jack 
- Grove connector and others at [seeedstudio][20]
- ~~Some PI connector with [long pins][21] for pluging this board and Linklabs one~~
- Some 2X20 pins [PI connector][29] for pluging this board  
- Antenna [UFL][22] with [IPEX][23] cable or [SMA][24] if using Lora Module
- Small Enclosure 125x125mm 75mm Height [#1][40] or [#2][41]

##License

<img alt="Creative Commons Attribution-NonCommercial 4.0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png">   

This work is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](http://creativecommons.org/licenses/by-nc/4.0/)    
If you want to do commercial stuff with this project, please contact [CH2i company](https://www.ch2i.eu/en#support) so we can organize an simple agreement.

##Misc
See news and other projects on my [blog][1] 
 
[1]: https://hallard.me
[2]: https://github.com/ch2i/packet_forwarder
[3]: https://PCBs.io/share/rmVdD

[10]: http://webshop.imst.de/ic880a-spi-lorawan-concentrator-868mhz.html
[11]: http://forum.thethingsnetwork.org/t/raspberry-pi-lorawan-gateway-board/1071
[12]: https://github.com/leon-anavi/rpi-examples
[13]: https://staging.thethingsnetwork.org/wiki/Hardware/Gateways/Overview
[14]: http://forum.thethingsnetwork.org/c/gateways
[15]: https://www.aerial.net/shop/product_info.php?products_id=1102
[16]: https://www.aerial.net/shop/index.php?cPath=22_124
[17]: http://wiki.dragino.com/index.php?title=PoE_Injector
[18]: http://www.ebay.com/itm/2-PCS-MP1584EN-Step-down-Power-DC-DC-3A-Adjustable-Ultra-LM2596-Step-down-Module-/301798394307
[19]: http://www.ebay.com/itm/1x-Tiny-4-5-28V-3A-DC-DC-Buck-Converter-Step-down-Power-Regulator-MP1584EN-/141524007951
[20]: http://www.seeedstudio.com/depot/index.php?main_page=opl_info&opl_id=4
[21]: http://www.ebay.com/itm/170578495165
[22]: http://www.ebay.com/itm/351690376555
[23]: http://www.ebay.com/itm/351738196013
[24]: http://www.ebay.com/itm/371534934746

[25]: https://www.adafruit.com/products/1979
[26]: https://github.com/ch2i/ic880a-gateway/tree/ch2i-rpi-shield

[27]: http://www.ebay.com/itm/351674929937
[28]: http://www.ebay.com/itm/371348168950
[29]: http://www.ebay.com/itm/351588181858

[30]: https://github.com/ch2i/packet_forwarder/blob/master/poly_pkt_fwd/readme.md

[40]: http://www.ebay.com/itm/262500056078
[41]: http://www.aliexpress.com/item/Free-Shipping-Good-Quality-ABS-Material-Transparent-Cover-IP66-Waterproof-Electrical-Switch-Box-125-125-75mm/32522255056.html
