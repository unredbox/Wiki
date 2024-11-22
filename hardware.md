---
title: Hardware Overview
description: 
published: true
date: 2024-11-22T17:03:51.108Z
tags: 
editor: markdown
dateCreated: 2024-10-21T03:34:51.578Z
---

This page is extremely WIP. If you have a kiosk or know of additional hardware variants, please contribute.

# Kiosk Models
## Indoor
  - Model: DVD-IN
  - Part Number: Indoor_Kiosk
  - Has variants with outdoor screen for use in bright entryways
## Indoor (Blue Variant)
  - Model: DVD-IN
  - Part Number: Indoor_KioskWB
  - Made for Walmart per agreement with Redbox.
## Indoor (17" Screen)
  - Model: DVD-IN
  - Part Number: Indoor_Kiosk17
  - Manufactured in 2011+ (unconfirmed) with a 17" screen
## Outdoor
  - Model: DVD-OT
  - Part Number: Outdoor_Kiosk
  - Heating/Cooling unit
  	- IceQube IQ2200VS and control panel
      - Known to cause fires, should be removed before use
    - Stego CR027 Heater
      - Plenty reliable according to employees
## Outdoor (17" Screen)
  - Model: DVD-OT
  - Part Number: Outdoor_Kiosk17
  - Heating/Cooling unit
  	- IceQube IQ2200VS and control panel
      - Known to cause fires, should be removed before use
    - Stego CR027 Heater
    
# Paint
The paint officially used by Redbox to refurbish kiosks is "B66R11038 DTM Acrylic Gloss Color Safety Red" which can generally be found most places that stock paint. It's recommended to remove any rust via sanding and paint over it with "B66A50 DTM Bonding Primer" before using the red paint.

# Computers

## Dell
- Optiplex 380 (2010)
  - Unknown HDD
  - Unknown RAM
  - Unknown CPU (Intel Core 2 Duo)
- Optiplex 390 (2011)
  - MoBo: DELL PB0520
  - 250GB HDD Seagate Barracuda ST520DM000
  - Unknown CPU (2nd gen Intel)
  - 1x 2GB Nanya DDR3-1333
- Optiplex XE2 (2013)
  - 500GB Seagate HDD
  - 4GB DDR3
  - i3-4330

## Lenovo
- ThinkCentre M91p USFF (2011)
  - Intel Pentium G630
  - 2GB DDR3
  - 250GB HDD
- ThinkCentre M58p USFF (2010)
  - Intel Pentium E5400
  - 2GB DDR3
  - 250GB HDD

## Premio

- M2H6V1
   - PN: RDBX01186-01 Rev B
   - MoBo: MSI H61M-P32/W8
   - 500GB HDD WD5000BPKX
   - 4GB RAM
   - Intel i3 3220 @ 3.30GHz
   - Windows 7 Embedded SP1
   - BIOS Version: E7788IZ1 V10.25B8
- M2H11OV1
   - PN: 259474-03 Rev C
   - MoBo: MSI H110M-PRO-VHL
   - 500GB WD500LPLX
   - 4GB RAM
   - Intel i3 6100 @ 3.70GHz
   - unknown BIOS
   - 1x HDMI & 2x USB 3 ports
- M2H110V1
   - PN: 259474-02 Rev A
   - MoBo: MSI CSM-H110M PRO-VHL
   - 500GB WD500LPLX
   - 4GB RAM (KVR21N15S8/4)
   - Intel i3 6100 @ 3.70GHz
   - unknown BIOS
   - 1x HDMI, 2x USB 3.0
- M2H310V1
   - PN: RDBX01679-01 Rev. A
   - Mobo: ?? H310 Motherboard
   - Unknown HDD
   - Unknown RAM
   - Unknown CPU
   - Unknown BIOS
   
   
Both units have a power button located above on the I/O panel, it's a black discreet button.
 # Components
 ## Touch Screen
 - Kristel Displays (from outdoor kiosk) 15"
    - Product # 259420
    - Model LCD15-042A
    - LCD Panel Model: Sharp LQ150X1LG91
    - Max Resolution: 1024x768 @ 75Hz
    - OSD/Display controls can be accessed from four buttons on the back of the display 
 - Kristel Displays (from Walmart kiosk) 15" Outdoor TS
    - Product # RDBX00923
    - Model LCD15-027C
    - LCD Panel Model: UNKNOWN
    - Max Resolution: UNKNOWN
 - Kristel Displays (from indoor kiosk) 15"
    - Product # RDBX01570
    - Model LCD15-026D
    - LCD Panel Model: UNKNOWN
    - Max Resolution: 1024x768 @ 75Hz
   
## Carousel
 - Vexta 5-Phase Driver
    - Product # RKD514H-A-A11 / RKD514H-A-A6
    - Model RKD514L-A / RKD514H-A
    - Sticker # 091200M8ZX / 091200M8ZW
    ![vexta-5-phase-driver.jpg](/hardware/vexta-5-phase-driver.jpg)
   
 - Vexta PK Series Steppers
 		![vexta-pk564aw-a94-label.jpg](/hardware/vexta-pk564aw-a94-label.jpg)
    ![vexta-pl596aw1-ai7-stepping-motor-horizontal.jpg](/hardware/vexta-pl596aw1-ai7-stepping-motor-horizontal.jpg)
   
 - Arcus Proteus USB Stepper Controller

## Credit Card Reader
 - Ingenico iUC285
 ![ingenico_iuc285.png](/ingenico_iuc285.png)

## Modems
- Cradlepoint IBR650LPE Netcloud
![cradlepoint_ibr650lpe_label_img_1393.jpg](/cradlepoint_ibr650lpe_label_img_1393.jpg)
![cradlepoint_ibr650lpe_side_view_img_1394.jpg](/cradlepoint_ibr650lpe_side_view_img_1394.jpg)

- Cradlepoint IBR200

To access the admin interface connect to the modem, head to 192.168.0.1 and when prompted for your password use the default password on the back of the modem. You may need to do a factory reset by pushing in the recessed reset button on the ethernet-port-side of the modem to deprovision the modem and make it accessible with the default credentials.

If you're having issues getting into the unit after a factory reset, try removing the SIM during the reset process. You can put the SIM back in once it's unprovisioned.

## Power Distribution Unit
- APC Line-R 1200VA Automatic Voltage Regulator

## Boards
- PCB #DVD-26-000-04
   - SER. Master 7/25/06

![PCB #DVD-26-000-04 Board](/pcb_dvd-26-000-04_snachodog.jpg "PCB #DVD-26-000-04 Board")
- Dan Leiwe disc dispenser controller

![dan_leiwe_board_motor_position.jpg](/hardware/dan_leiwe_board_motor_position.jpg)

- AUX I/O Controller
   - PCB #DVD-25-000-04 7/25/06
![aux-io-controller-board.jpg](/hardware/aux-io-controller-board.jpg)

- Arcus Proteus XES (Carousel/Gripper Z-Axis)
  - Serial #202-SOL-112211-0987
  - PCB "PROTEUS USB2EX Rev. D6"

![proteus2ex-board-rev-d6-bare.jpg](/hardware/proteus2ex-board-rev-d6-bare.jpg)

## Lock
![Locked Lock from within a kiosk](/locked_lock.jpg "Locked lock from within a kiosk")
