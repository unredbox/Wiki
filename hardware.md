---
title: Hardware Overview
description: 
published: true
date: 2025-02-18T13:40:54.675Z
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
  	- IceQube IQ2200VS and control panel (Before February 2012)
      - Known to cause fires, should be removed before use
    - IceQube IQ990FFS and control panel (After February 2012)
      - No fires reported or known. Best to use with caution
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
  - 1x 2GB Nanya DDR3-1333
  - Unknown CPU (2nd gen Intel)
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
<figure class="image image_resized" style="width:40%;"><img src="/20241207_221751.jpg"></figure>

   - PN: RDBX01186-01 Rev B
   - MoBo: MSI H61M-P32/W8
   - 500GB HDD WD5000BPKX
   - 4GB DDR3 RAM 
   - Intel i3 3220 @ 3.30GHz
   - Windows 7 Embedded SP1
   - BIOS Version: E7788IZ1 V10.25B8
   - IO expansion board 3RAM3014000 REV:1.0
   <figure class="image image_resized" style="width:40%;"><img src="/20241207_181720.jpg"></figure>
   
   
- M2H110V1
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
   - BIOS Version: American Megatrends Inc. 2.P5
   - 1x HDMI, 2x USB 3.0
   - IO expansion board 3RAM63014000 REV:1.0

- M2H310V1
   - PN: RDBX01679-01 Rev. A
   - Mobo: MSI H310M PRO-VLH PLUS
   - 500GB WD5000LPSX
   - 4GB DDR4 2400Mhz RAM
   - Intel i3 9100 @ 3.60 GHz
   - Windows 10 Enterprise LTSC x64
   - AMI 1.Q3, 1/22/2020
   - 1x HDMI, 2x USB 3.0

All Redbox Premios have a power button located above on the I/O panel, it's a black discreet button.
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
The carousel consists of a central solid steel rod with 8 plastic platters (decks), each deck consists of 6 quadrants (the area between posts) where each quadrant holds 15 disks, for a total of 90 disks per deck. A VMZ equipped kiosk can store a total of 720 disks (but usually only contains around 600 to keep the VMZ empty and to reserve space for returns).

Carousel in a VMZ kiosk:
<figure class="image image_resized" style="width:40%;"><img src="/20241209_093046.jpg"></figure>


 - Vexta 5-Phase Driver
    - Product # RKD514H-A-A11 / RKD514H-A-A6
    - Model RKD514L-A / RKD514H-A
    - Sticker # 091200M8ZX / 091200M8ZW
		<figure class="image image_resized" style="width:40%;"><img src="/hardware/vexta-5-phase-driver.jpg"></figure>
   
 - Vexta PK Series Steppers
	<figure class="image image_resized" style="width:40%; display: inline-block;"><img src="/hardware/vexta-pk564aw-a94-label.jpg"></figure>
	<figure class="image image_resized" style="width:29.93%; display: inline-block;"><img src="/hardware/vexta-pl596aw1-ai7-stepping-motor-horizontal.jpg"></figure>
   
 ## Picker/Y-axis
The picker (or Y-axis) consists of a vertically mounted metal extrusion, with a rail mounted in the center. At the top and bottom of the section are ball bearing belt rollers, that allow the belt to rotate, but stay fixed in place horizontally. This belt is then looped through the frame of the picker.
<figure class="image image_resized" style="width:50%;"><img src="/screenshot_20241209_093520_gallery.jpg"></figure>


## Barcode scanner
The barcode scanner is mounted to the inside of the picker carriage's frame, facing outwards to the disk. It is connected to the internal PC via USB, and is used to determine the disk that is being returned or rented.
- Code USB reader model CR1011_04
    - S/N: 20884820
    - Revision: 04.4
    <figure class="image image_resized" style="width:30%; display: inline-block;"><img src="/20241206_235637.jpg"></figure>
    
  
    <figure class="image image_resized" style="width:30%; display: inline-block;"><img src="/20241206_235617.jpg"></figure>

## Cooling Units
### IceQube IQ2200VS (Air Conditioner)
> These units are known to catch fire. Re-wiring is required to resolve this issue. Check for frayed wires.
{.is-warning}

- Unit
![iq2200vs_unit.jpg](/iq2200vs_unit.jpg)
- Controller
![iq2200vs_controller.jpg](/iq2200vs_controller.jpg)

### IceQube IQ900FFS (Air Exchanger)
- Unit
![iq900ffs_unit.jpg](/iq900ffs_unit.jpg)
- Controller
![iq900ffs_controller.jpg](/iq900ffs_controller.jpg)
    
## Credit Card Reader
 - Ingenico iUC285
	<figure class="image image_resized" style="width:40%;"><img src="/ingenico_iuc285_hd.jpg"></figure>

## Modems
- Cradlepoint IBR650LPE Netcloud
	<figure class="image image_resized" style="width:40%; display: inline-block;"><img src="/cradlepoint_ibr650lpe_label_img_1393.jpg"></figure>
	<figure class="image image_resized" style="width:40%; display: inline-block;"><img src="/cradlepoint_ibr650lpe_side_view_img_1394.jpg"></figure>

- Cradlepoint IBR200
	<figure class="image image_resized" style="width:40%; display: inline-block;"><img src="/cradlepoint_ibr200_bottom.png"></figure>
	<figure class="image image_resized" style="width:40%; display: inline-block;"><img src="/cradlepoint_ibr200_front.png"></figure>
  
To access the admin interface connect to the modem, head to 192.168.0.1 and when prompted for your password use the default password on the back of the modem. You may need to do a factory reset by pushing in the recessed reset button on the ethernet-port-side of the modem to deprovision the modem and make it accessible with the default credentials.

If you're having issues getting into the unit after a factory reset, try removing the SIM during the reset process. You can put the SIM back in once it's unprovisioned.

## Power Distribution Unit
> There is possibilities that none of these will be in the unit and would be replaced with a random power strip.
{.is-info}
- APC Line-R 1200VA Automatic Voltage Regulator
![apc_line-r_1200va.jpg](/apc_line-r_1200va.jpg)
- Tripp Lite 900VA UPS Battery Back Up - OMNI900LCD
![tripp_lite_900va.jpg](/tripp_lite_900va.jpg)

## Boards
- PCB #DVD-26-000-04
   - SER. Master 7/25/06
		<figure class="image image_resized" style="width:50%;"><img src="/pcb_dvd-26-000-04_snachodog.jpg" alt="PCB #DVD-26-000-04 Board"></figure>

- Dan Leiwe disc dispenser controller
	<figure class="image image_resized" style="width:50%;"><img src="/hardware/dan_leiwe_board_motor_position.jpg"></figure>

- AUX I/O Controller
   - PCB #DVD-25-000-04 7/25/06
   
		<figure class="image image_resized" style="width:50%;"><img src="/hardware/aux-io-controller-board.jpg"></figure>

- Arcus Proteus XES (Carousel/Gripper Z-Axis)
  - Mounted to top of carousel cross-beam, connects to Vexta drivers via USB
  - Serial #202-SOL-112211-0987
  - PCB "PROTEUS USB2EX Rev. D6"

	<figure class="image image_resized" style="width:50%;"><img src="/hardware/proteus2ex-board-rev-d6-bare.jpg"></figure>

## Lock
<figure class="image image_resized" style="width:70%;"><img src="/locked_lock.jpg" alt="Locked Lock from within a kiosk"></figure>


## Weights
Some items have been weighed, while others are estimates:
- Bare kiosk shell and door is ~300 lbs (weighed by kas)
- Carousel, containing a central solid steel rod and plastic platters (decks), weighs ~100 lbs
- Unloaded kiosk weighs ~600 lbs (weighed by kas)
- Loaded kiosk weighs ~800 lbs
- AC unit is 56 lbs (weighed by iiPython)
- Picker Assembly weighs ~30 lbs
- Air exchanger is ~32 lbs (weighed by iiPython)
- Screen is 11.6 lbs (weighed by iiPython)
- Carousel motor is 8.8 lbs (weighed by iiPython)
- Carousel shaft is 17.5 lbs (weighed by iiPython)
- Linear rail is 15.5 lbs (weighed by iiPython)
- Internal space heater is 1 lb, 15.2 oz (weighed by iiPython)
- Shaft collars are 1 lb, 2.1 oz each (weighed by iiPython)
- Monitor cooling is 3 lbs, 11 oz (weighed by iiPython)
- Carousel top crossbeam is 5 lbs, 1.1 oz (weighed by iiPython)
- A single Redbox disk and case weights 2 oz (weighed by kas)
    - A single empty Redbox case weighs 1.5 oz
    - A fully loaded kiosk worth of disks (600) would weigh ~90 lbs
    
## Disc Dispenser / Return Slot Variant (Test Markets)
Only available in test markets, a variant of the Disc Dispenser / Return Slot was tested but never widely rolled out.  It is not known how many exist.
It was designed that if there was a line of people waiting to rent movies or games at a Redbox, and you only had to return a rental, you would go to the right side of the machine, press the green lit-up button, insert your return, and the small LCD display would tell you if your return was successful.  These photos are from the Walmart in Antioch, IL kiosk from Google Maps.  The machine has been removed and probably scrapped.  These photos were uploaded to Google Maps by a visitor of the kiosk in January 2018, so it shows an old card reader and old UI.
![cardreadervariant1.png](/cardreadervariant1.png)
![cardreadervariant2.png](/cardreadervariant2.png)