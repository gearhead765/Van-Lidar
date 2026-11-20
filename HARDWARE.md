# Hardware

## Off the Shelf Hardware
- **Board:** [Seeed Studio XIAO ESP32-S3](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/102010573/24814471)
- **Rangefinder:**
    - **TF02-Pro:** [Benewake 40m IP65 LiDAR UART](https://www.mouser.com/en/ProductDetail/Benewake/TF02-Pro-Uart)
- **Miscellaneous Components:**
    - **DC-DC Converter:** [Recom R-78K5.0-2.0L](https://www.digikey.com/en/products/detail/recom-power/R-78K5-0-2-0L/21284879) 
    - **Phoenix Wire Connector:** [Phoenix Mini Combicon MC 1840366](https://www.digikey.com/en/products/detail/phoenix-contact/1840366/349178) 
    - **Phoenix Board Connector:** [Phoenix Mini Combicon MC 1844210](https://www.digikey.com/en/products/detail/phoenix-contact/1844210/349195)
    - **PicoBlade Board Connector** [Molex 0530480410 Right Angle (2 required)](https://www.digikey.com/en/products/detail/molex/0530480410/242866)    
    - **Polyfuse:** [1.1Amp PTC Resetable Fuse](https://www.digikey.com/en/products/detail/littelfuse-inc/2920L110-60MR-A/11205746) 
    - **TVS Diode:** [Littelfuse SZ5KASMC36AT3G](https://www.digikey.com/en/products/detail/littelfuse-inc/SZ5KASMC36AT3G/18716674) 
    - **Reverse Polarity Protection:** [SS24](https://www.digikey.com/en/products/detail/taiwan-semiconductor-corporation/SS24/7369395) 
- **Project Box:**  [Hammond 1551KFLBK](https://www.digikey.com/en/products/detail/hammond-manufacturing/1551KFLBK/2094805)
    - **Screws to Secure Board in Enclosure (2 per Project):** [#2 x 1/4" Thread-Forming Screw](https://www.mcmaster.com/products/90385a311/)
    - **3D Printed Washer (2 per Project):** [5/32"[4mm OD] x 5/64"[2mm ID] x 1/16"[1.5mm Thick]](<CAD Model/3D Printed Washer.STL>)

## Modifications to Off the Shelf Hardware
The Hammond enclosure will need a cutout for the Phoenix power connector.  The top will need a tall opening, while the bottom will need the lip removed in the connector area.  Two small washers can be 3D printed to lift the board just a little so the IMU board will clear the lid.
<br>![](Images/cad1.png)![](Images/cad2.png)

[Box cutout dimensions](<CAD Model/box_machining.pdf>)<br>
[Lid cutout dimensions](<CAD Model/lid_machining.pdf>)

## The PCB
[Kicad](https://www.kicad.org/) was used to design the very simple carrier board for the ESP32 development board.  This eliminated the need for point-to-point wiring and made a much more compact package possible.  You can also construct this project on strip board, dead bug style, or how ever you want.

The majority of the components are in the power supply.  Since this was for use in a vehicle, it needed to operate off of 12V.  The sensor is supplied from the 5V output of the DC-DC converter, and the Xiao ESP32 board uses its onboard converter to run off 3.3V.

[![](Images/van_rangefinder_schematic.png)](Notes/van_rangefinder_Schematic.pdf)

The boards were produced by [OSHPark](https://oshpark.com/shared_projects/d4r7hpFr).  You can get three boards for $12 including shipping.  They are produced in the US and usually take a couple of weeks to arrive.  Of course, all of the Kicad source files are included in the repo if you want to send them to your favorite PCB manufacturer.

![](Images/van_rangefinder_pcb.png)

Assembly is straight forward.  Solder the lowest components first.
