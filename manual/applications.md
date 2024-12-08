---
title: Useful Applications
description: 
published: true
date: 2024-12-08T20:06:39.029Z
tags: 
editor: markdown
dateCreated: 2024-12-08T12:59:34.669Z
---

## Installing VNC Server

If you've recently acquired a Redbox kiosk and want to tinker with your machine in the comfort of your own room, you may want to look into setting up a VNC server. A VNC server will allow you to remotely access and control your kiosk from any device, anywhere, which can save you the hassle of connecting a keyboard and mouse each time you need to access the machine. This is especially useful if your kiosk is placed in a less convenient location, like outdoors or in a cold garage. To start a VNC server on your kiosk, you'll need to choose one first. UltraVNC is highly recommended, as it works great on 32-bit devices and is easy to setup. First, [visit this page](https://uvnc.com/downloads/ultravnc.html) to download the latest version of UltraVNC Server (make sure to select the 32-bit architecture). Then, drag this executable on a USB stick and plug it into your kiosk.

Once you boot your kiosk, open the File Explorer and navigate to your external USB. Click on the executable to start the installation, and follow the instructions to set up your VNC server. When the installation is complete, navigate to `C:\Program Files\uvnc bvba\UltraVNC` and launch the `uvnc_settings.exe` file located in this folder. Here, you'll be able to configure your VNC server and setup a password for accessing it.

Then, apply all changes and restart your system. Once your system boots back up, you should be able to access your VNC Server at port 5900 (by default). Download a VNC Client on your devices (like RealVNC Viewer), and enter your kiosk's local IP address followed by the port. You should be able to connect without issues and access your kiosk on your network!

**Tip:** _If you want to access your kiosk outside of your network, you can setup port forwarding on your router to expose the 5900 port._

## Enabling SMB Protocol

If you'd like to have the option of managing the files on your kiosk with ease, enabling the SMB1 protocol is a good choice. Similarly to setting up a VNC Server, SMB will allow you to access your kiosk's internal files without the need of navigating through File Explorer directly. Before enabling SMB, you'll need to create a new Administrator account or change the password for `Rbuser` to login. You can learn how to change the default Administrator password [here](https://redbox.wiki/en/manual/troubleshooting#changing-your-administrator-password).

If you already have access to an Administrator account, open the Command Prompt on your kiosk and run the following command to enable SMB through the registry editor:  
`reg add "HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" /v SMB1 /t REG_DWORD /d 1 /f`

This will create a registry record enabling SMB1 on your device. Before you continue, it's also recommended that you ensure SMB will start properly on boot. To do this, enter the Services Manager (`services.msc`) and look for the following services: **Server**, **Workstation**, and **TCP/IP NetBIOS Helper**. For each of these, right-click them and select Properties, and make sure that the Startup type is set to "Automatic". They most likely are, but if not, make sure to update them as so and start them afterwards if they aren't already.  
  
Once you've enabled SMB and configured the start-up services, you'll want to grant permission to access the C:\\ drive on your kiosk. Navigate to your C:\\ drive in File Explorer and right-click on it, then select Properties. Click the Sharing tab, and select Advanced Sharing to open the permission manager. Tick the "Share this folder" option, and create a “Share name” to continue (you can name this whatever you'd like). Click the Permissions button below it, and check Allow for each option (Read/Write/Full Access), making sure the “Everyone” group is selected.

After doing this, you should be able to access your kiosk files through SMB! If you don't know how to do this already, you can use [this guide here](https://knowledgebase.45drives.com/kb/kb450446-connecting-to-smb-share-on-windows-and-macos/). When you're prompted to enter your credentials, use the login for your Administrator account that you setup before you started. That's it!

## Configuring Firewall

If you want to enable functionalities like starting a VNC server, enabling the SMB protocol, or any other tasks that require a local network connection, you'll want to connect your kiosk to your home network. As you may already know, however, you may not want to expose your computer to the internet directly as it may cause complications in the future when software is no longer supported (or in the case of being required to upgrade Windows 7). To help minimize your risk to such complications, you can configure your router's firewall and disable access to WAN. If you don't have your kiosk connected to the internet already, you can follow the instructions [here](https://redbox.wiki/en/manual/quirks#no-internet-on-cellular-modem-sim).  
  
To do this, you'll need access to your router's administrator panel. This tutorial will be using OpenWRT, but most router's support this functionality in a similar way (the instructions may vary, however). First, login to your router's OpenWRT interface and go to **Network > Firewall > Traffic Rules**. Then, create a new forward rule with the “Source zone” set to LAN, and the “Destination zone” set to WAN. Then, update this forward rule to the following details:

> Name: \[enter any name here\]  
> Restrict to address family: **IPv4 and IPv6** (default)  
> Protocol: **TCP+UDP** (default)  
> Source zone: **LAN** (default)  
> Source MAC address: \[select your kiosk's MAC address here\]  
> Source address: \[select your kiosk's local IP address here\]  
> Source port: **any** (default)  
> Destination zone: **WAN** (default)  
> Destination address: **any** (default)  
> Destination port: **any** (default)  
> Action: **reject**  
>   
> Click the **Save & apply** button below, and wait for the changes to propagate. Your kiosk should now have internet access restricted to only communicate devices in your local network.