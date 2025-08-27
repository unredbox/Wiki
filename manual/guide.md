---
title: How-To Guides
description: How to use your kiosk.
published: true
date: 2025-08-27T01:17:44.899Z
tags: 
editor: markdown
dateCreated: 2025-06-15T04:36:53.530Z
---

# Useful applications for your kiosk
These applications are helpful to know the state of your kiosk's PC.
### [CrystalDiskInfo](https://crystalmark.info/en/software/crystaldiskinfo/)
Program is used to determine the health of your HardDrive/Solid State Drive.

Features Include:
- S.M.A.R.T. Health Monitoring
- Temperature Tracking
- Power-On Hours & Usage Statistics
- SSD Endurance & Wear Leveling (NAND Health)
- Firmware & Interface Details
- Alerting & Logging
- Advanced APM/AAM Control (HardDrive Only)
- NVME Support (In Windows 10 PC or any PC replacement)
- Portable & Low Overhead

### [HWMonitor](https://www.cpuid.com/softwares/hwmonitor.html)
Program is used to monitor CPU, Memory (RAM), GPU (If installed), SSD/HDD, Battery, sensors, and more.

Features Include:
- Real-time sensor monitoring
- CPU & GPU on-die sensor support
- LPCIO chip monitoring
- Memory-module thermal sensors
- SSD/HDD S.M.A.R.T. temperature monitoring
- Battery status tracking (Requires TrippLite to have a working battery)
- Complete report export
- Minimal overhead & portable mode
- Multi-platform support (will work on Windows 7 Embedded version of the kiosk software)

Features Requires a Pro License:
- Remote Monitoring
- Graph Generator
- Improved Interface

# Upgrading to Windows 11 IoT Enterprise LTSC
> If you are using Windows 7, you will need to clone the Windows 10 IoT Enterprise Image from our Discord Server as Windows 7 - Windows 11 will remove all files and apps. 
{.is-danger}

### Preparing
When preparing, you will need to grab the `Windows 11 IoT Enterprise LTSC` ISO from [here](https://massgrave.dev/windows_ltsc_links) and download the Windows 11 IoT Enterprise LTSC link. We recommend the 2nd link as its already set to iso. You will need to install the ISO to your Kiosk PC or use a tool like Rufus to extract the ISO to your USB Flash Drive

### Running an upgrade
1. Open the ISO we downloaded to the Kiosk PC or plug in your USB Flash Drive
2. In the initial setup, you will be asked about Updates. If your kiosk is offline, you will need to set it to Not right now. If your kiosk is connected to the internet, you can download updates, drivers, and optional features. <figure class="image image_resized" style="width:80%;"><img src="/guides/windows-11-upgrade/setuphost_siftxqo21r.png"></figure>
3. When prompted for a product key, you should be able to skip this step. <figure class="image image_resized" style="width:80%;"><img src="/guides/windows-11-upgrade/setuphost_pqli1kz8iz.png"></figure>
4. When asked to select an image, select Windows 11 IoT Enterprise LTSC. <figure class="image image_resized" style="width:80%;"><img src="/guides/windows-11-upgrade/setuphost_kgktb97ir4.png"></figure>
5. If you successfully did everything correctly, you should be able to select `Keep personal files and apps` but sometimes this is automatically applied. Once you verified everything, proceed with installation.
6. Once the kiosk boots into Windows 11, you should activate windows as after 30 days, the kiosk will turn off automatically after 2 hours. You will need an internet connection to complete this. We recommend [MAS](https://github.com/massgravel/Microsoft-Activation-Scripts) as obtaining an IoT Enterprise License isn't given out to just anyone. 


# Upgrading from 3rd/4th Generation to 5th Generation Cortex Barcode Scanner
This is for upgrading from 3rd/4th Generation to 5th Generation. Typically this is beneficial as 4th Generation tends to have high amounts of issues during kiosk restarts, which tends to relieve long term issues.
1. Disconnect the USB Cable and Cable `J7` on the `DVD-36-000-04` Gripper Board
2. Loosen 2 Bolts Holding the old Camera Device
3. Grab the `Cortex Barcode Scanner` and mount to the bracket.
4. Install the Cortex Barcode Scannner using the same 2 bolts holding the old mount
5. Install the 5th Generation Camera from the Redbox Technician Driver Kit. 
> If you are using Windows 11, you will need to use the CR1100 drivers from CodeCorp's Website, which also support CR1000 devices.
{.is-warning}
6. Modify `hal.xml` and apply the following to the camera properties:
```xml
  <Camera>
   <CameraPlugin>DirectShowFrame</CameraPlugin>
   <SnapDecodePort>NONE</SnapDecodePort>
   <WritePause>500</WritePause>
   <RebootOnStart>true</RebootOnStart>
   <EnableInfared>false</EnableInfared>
   <CycleCameraOnUse>False</CycleCameraOnUse>
   <UseInliteOnFail>True</UseInliteOnFail>
   <ScannerService>Cortex</ScannerService>
   <LogDetailedScan>False</LogDetailedScan>
   <InsertReadStats>true</InsertReadStats>
   <ExpectedCodes>4</ExpectedCodes>
   <ScanTimeout>2000</ScanTimeout>
   <ScannerWakeupPause>15000</ScannerWakeupPause>
   <FilterExcessReadCodes>True</FilterExcessReadCodes>
   <CortexPortOpenWait>50</CortexPortOpenWait>
   <CortexSnapOnDecodeFailure>False</CortexSnapOnDecodeFailure>
   <CortexPortBufferSize>8192</CortexPortBufferSize>
   <UseRuntimePath>False</UseRuntimePath>
   <UseCortexHDField>True</UseCortexHDField>
   <IRHardwareInstallDate>NONE</IRHardwareInstallDate>
   <UseInliteForFraudValidation>False</UseInliteForFraudValidation>
   <CortexStartupAction>Decode</CortexStartupAction>
 </Camera>
```
7. Save and close
8. Open Command Prompt and execute ``reg.exe add "HKLM\SYSTEM\ControlSet001\Services\CCSERMU\Configuration\000000000000" /v PortName /t REG_SZ /d "COM6" /f``
9. Restart the computer

If done correctly, your Cortex Barcode Scanner Should work as expected. If you are getting a scanning error, Double check the steps above were followed correctly.

# How to re-enable Task Manager
All kiosks comes with Task Manager disabled, but with RBUser being an administrator account, this can be re-enabled.
1. Access Redbox Control Panel
2. Select DOS Prompt
3. Run command `gpedit.msc` and press `ENTER` to open `Local Group Policy Editor`
4. Navigate to `User Configuration > Administrative Templates > System > Ctrl+Alt+Del Options`
5. Select `Remove Task Manager` and set to `Disabled` or `Not Configured`
6. Press `Apply` and `OK`

# From HardDrive to a Solid-State Drive
For this, we will be using Macrium Reflect 8 (X works the same, but it is trialware and only restoring works after the trial period) though there are other tools to clone to a drive. You will need to prep the PC.

### Pre-existing OS Cloning/Restoring
This is for cloning your previous OS from your physical drive.
1. Disconnect the HardDrive from the Kiosk PC <figure class="image image_resized" style="width:40%;"><img src="/guides/drive_location.jpg"></figure>
2. Plug the Harddrive and Solid-State Drive into your PC (Recommended) or a SATA Drive Dock.
3. Open Macrium Reflect.
4. Locate **Backup** and select **Image Selected Disks**.<figure class="image image_resized" style="width:60%;"><img src="/guides/reflectbin_sjjl7sckt7.png"></figure>
5. Select the drive you wish to back up and restore on a Solid-State Drive.<figure class="image image_resized" style="width:60%;"><img src="/guides/reflectbin_nfxh8xa9j5.png"></figure>
6. You can skip the **Edit the Plan for this Backup** window as this is not required for our backup
7. Check advanced options and make sure the **Compression Level** is set to **Medium** and use **Intellegent sector copy**.<figure class="image image_resized" style="width:60%;"><img src="/guides/reflectbin_1tdbkhxyrt.png"></figure>
> If your backup fails upon restoring, you can set Compression Level to **None** which sometimes solves this issues.
> {.is-danger}
8. Press **Finish** and your backup should start. We recommend using Macrium Reflect 8 at the Highest Priority to speed up the backup process.
9. Once Finished, you will need to navigate to Restore and look for **Browse for an image or backup to restore...** and select the image we just backed up.<figure class="image image_resized" style="width:60%;"><img src="/guides/reflectbin_gnpcksufyy.png"></figure>
10. Press Restore once you verify the contents match what we backed up earlier.<figure class="image image_resized" style="width:60%;"><img src="/guides/reflectbin_hxe4dslkzx.png"></figure>
11. Make sure you select the correct target disk, then select **Erase Disk** and **Copy Partitions**.<figure class="image image_resized" style="width:60%;"><img src="/guides/olljysg2ii.png"></figure>
12. Press Finish and Macrium should start restoring.<figure class="image image_resized" style="width:60%;"><img src="/guides/r5phc7h3a9.png"></figure>
13. Unplug the Solid-State Drive from your PC or Dock and Plug it back into your Kiosk PC.
14. Boot up the PC and verify it boots properly before plugging all the cables back into your kiosk and screwing the Solid-State Drive to the mount in the case.

### Restoring from Images
Wanting to upgrade to the Windows 10 Image or having to get the Windows 7 Image because the drive was dead on arrival or missing? This section should help with restoring. You will need to get the images from the discord server.
1. Plug the Harddrive (7200 RPM Recommended. 5400 RPM will have a hard time querying the VistaDB database and may crash the kiosk software) or Solid-State Drive (Recommended) into your PC (Recommended) or a SATA Drive Dock.
2. Open Macrium Reflect.
3. Navigate to Restore and look for **Browse for an image or backup to restore...** and select the image we downloaded from the discord server.<figure class="image image_resized" style="width:60%;"><img src="/guides/reflectbin_gnpcksufyy.png"></figure>
4. Press Restore.<figure class="image image_resized" style="width:60%;"><img src="/guides/reflectbin_hxe4dslkzx.png"></figure>
5. Make sure you select the correct target disk, then select **Erase Disk** and **Copy Partitions**.<figure class="image image_resized" style="width:60%;"><img src="/guides/olljysg2ii.png"></figure>
6. Press Finish and Macrium should start restoring.<figure class="image image_resized" style="width:60%;"><img src="/guides/r5phc7h3a9.png"></figure>
7. Unplug the drive from your PC or Dock and Plug it back into your Kiosk PC.
8. Boot up the PC and verify it boots properly before plugging all the cables back into your kiosk and screwing the Solid-State Drive to the mount in the case. 
> If you start experiencing issues, you may need to repeat all steps again after re-downloading the image. Also follow **Migrate from old kiosk to new kiosk** guide to get your kiosk running with settings from your old kiosk.
{.is-warning}


# Re-wiring your Kiosk (Outdoor Only)
> Electrical work must be performed with extreme caution and precision. If you are unsure about any part of this process, or lack the proper tools or experience, stop immediately and consult a licensed electrician. Improper wiring can result in serious injury, death, fire, and/or damage to kiosk equipment.
{.is-warning}

This guide is for individuals who plan to reuse the existing outlets within the kiosk. If you're not confident in completing this process, consider using an extension cord as an alternative. Make sure the cord supports at least 125V. Keep in mind that, depending on the type of cord used, it may obstruct the removal and reinstallation of the drop bin.

### Required Tools & Materials
- **1x 12-AWG/2 or 12AWG/3 Power Cord (25ft)**
A thick, durable cable suitable for 20-amp circuits. The 25ft length should give you plenty of wire to work with inside the kiosk. You technically shouldn’t need more than 15 feet, but this allows you to have the proper lengths for daisy chaining from Outlet 1 to Outlet 2
- **1x GFCI Outlet Tester**
Use this to verify that the outlet is properly wired and the GFCI protection works as intended.
- **1x 3/8" Clamp-on Service Entrance Connector**
Prevents stress or accidental tugging from damaging the internal wiring. Required for secure and safe cable entry into the box.
- **5x 12-10 Yellow Ring Terminals**
These will be crimped onto the ground wires to ensure a tight, secure, and corrosion-resistant connection to the outlets and chassis.
- **1x Wire Stripper/Cutter/Crimper Tool**
A basic model will do fine. Used to cut wire to length, strip the outer jacket, and crimp terminals to the exposed copper.
- **1x GFCI Outlet or 1x 20 Amp Circuit Breaker**
Even though you're using 12 AWG wiring rated for 20 amps, GFCI outlets usually max out at 15 amps. Do not exceed the rated amperage.
>For permanent or outdoor setups, you may want to install a dedicated 20-amp breaker. If you’re not experienced with electrical panels, hire a licensed electrician to handle this part.
{.is-info}

- **1x 1/2" Plastic Screw-in Connector Conduit Fitting**
Optional, but great for helping keep moisture and rain out of the box, especially if the kiosk is outdoors.

### Optional Parts
- **2x 20-Amp 125V Outlets (or better)**
Used if you're replacing both receptacles inside the kiosk.
- **1x 1/2" Plastic Screw-in Connector Conduit Fitting** 
Great for helping keep moisture and rain out of the box, especially if the kiosk is outdoors. Most of the time, it is ok to re-use the old one, but is a good idea to use a new one to keep water from entering the kiosk.

### Replacement Steps
1. **Disassemble the Electrical Box**  
   - Unscrew and remove the two bolts holding the electrical box in place inside the kiosk.  
   - Pull the box outward carefully to access the internal wiring.  

2. **Remove the Old Wiring**  
   - Disconnect and discard all old wiring inside the box.  
   - You may need to cut the old green ground wire connected to the kiosk body. Don’t worry—you’ll replace it with fresh wire.  

3. **Inspect the Kiosk Entry Point**  
   - Check the condition of the plastic screw-in fitting where the cable enters the kiosk.  
   - If damaged or missing, replace it to ensure weather resistance.  

4. **Feed in the New Power Cord**  
   - Insert your 12 AWG power cord through the back of the kiosk and into the box area.  
   - Pull enough slack through to work comfortably and reach all terminals.  

5. **Strip the Outer Jacket**  
   - Use a wire stripper to remove the outer black insulation from the cord—be careful not to nick the internal wires.  
   - You should see three wires inside:  
     - **Black or Red** = Hot/Live  
     - **White** = Neutral  
     - **Green** = Ground  

6. **Replace the Clamp Connector**  
   - Remove the existing 3/8″ clamp connector from the electrical box.  
   - Install the new clamp connector and feed the stripped cable through it.  
   - Tighten the clamp securely to prevent movement.  

7. **Prepare the Jumper Wire**  
   - Cut a short length of cable to connect the first outlet to the second outlet inside the box.  
   - Leave extra length in case you ever need to remove or reposition the outlets.  

8. **Strip and Prep Wires**  
   - Strip both ends of the jumper wire: remove the jacket and expose the individual conductors.  
   - Crimp a yellow ring terminal onto the ground wire at both ends.  

9. **Secure Cable and Connector**  
   - Insert the power cord and jumper wire into the electrical box.  
   - Tighten the clamp-on connector to hold everything in place.  

10. **Tie the Underwriter’s Knot**  
    - Before connecting to the GFCI or breaker:  
      - Create a loop in the hot and neutral wires.  
      - Intertwine them so they form a knot (prevents tension on the terminals).  
      - Pull the knot tight and push it back into the box.  

11. **Connect to Outlet 1**  
    - Using the labeling on the outlet, connect:  
      - **Black/Red (Live)** to the brass screw  
      - **White (Neutral)** to the silver screw  
      - **Green (Ground)** (ring terminal) to the green screw  

12. **Connect the Jumper to Outlet 2**  
    - Repeat the connections using the jumper wire on Outlet 2:  
      - Live to brass screw  
      - Neutral to silver screw  
      - Ground (ring terminal) to green screw  

13. **Install and Mount the Outlets**  
    - Secure Outlet 1 (the back outlet) to the electrical box.  
    - Tighten the mounting screws and install the cover plate.  

14. **Ground to Kiosk Frame**  
    - Cut another length of ground wire to run from Outlet 2 to the metal frame of the kiosk.  
    - Crimp ring terminals on both ends.  
    - Secure one end to the green screw on Outlet 2 and the other to the chassis ground point on the kiosk.  

15. **Final Assembly**  
    - Neatly tuck the wires inside the box.  
    - Reattach the electrical box to the kiosk with the original bolts.  
    - Ensure everything is tight and sealed.  


### Testing and Verification
> Ensure all outlet connections are secure and tight before performing any tests. Loose wiring may cause an electrical fire or destroy kiosk equipment.
{.is-warning}
1. Plug in your GFCI Outlet Tester.
2. Make sure each outlet shows correct wiring and that GFCI protection functions.
3. If you get an error, double-check all wire connections, especially Live vs Neutral.
4. Once everything tests correctly, plug in your kiosk equipment.
<figure class="image image_resized" style="width:60%;"><img src="/guides/electrical-diagram.png"></figure>

# Migrate from old kiosk to new kiosk
> Make sure to backup everything before proceeding and note your registry settings.
{.is-warning}

### Backup Required Files (old kiosk)
- Backup the following files:  
  - `haldata.vdb3`  
  - `hal.xml`  
  - `inventory.data`  
  - `profile.data`  
  - `system.config`  
  - `Redbox.Rental.Services.dll`  
- Export registry key:  
  - `HKLM\SOFTWARE\Redbox\REDS\Kiosk Engine\Store`  

#### (Optional) Change Kiosk ID
- Edit **KioskID** and **market** in the above registry key  
- Reference KioskIDs and addresses from `profile.data > Store` table  
- Update **system.config**, replacing all old Kiosk ID values with the new one  

### Prepare New Kiosk
- Install a fresh kiosk image on the new PC  
- Replace the same files with the backed-up ones  

### Configure COM Ports
- Open **Device Manager**  
- Assign COM ports to match the old setup:  
  - USB → RS232 adapter → **COM1**  
  - Protenus board → **COM3**  

### Install in Kiosk
- Shut down the PC  
- Mount it into the kiosk hardware  
- Power on system  
- Confirm **KioskEngine** loads  

### Camera Driver Setup
- Open **Device Manager → Camera Devices**  
- If Microsoft default driver is installed, replace it  
- Install **AVEO x64 (4th Gen)** drivers (from Discord)  
- Open **HAL Tester → Configure Devices → Survey Hardware**  
- Verify camera detection (compare with screenshot from old kiosk)  

### Camera Calibration
- Open **HAL Tester**  
- Insert a disc into the gripper (aligned with camera)  
- Open **Camera Settings → Preview**  
- Adjust settings until image is clear and readable  
  - Example: lower **Gamma** for clarity