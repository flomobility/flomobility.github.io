---
layout: default
title: Networking
nav_order: 4
permalink: /docs/networking
---

# Networking with Flo Edge

Out of the box you'd be able to access Flo Edge via it's hotspot or USB Tethering.

## Important to Know
- You're `root` user by default on Flo Edge
- Password for root user is `flo@123`. Can later be changed with `passwd`

## USB Tethering
> Flo Edge has a static IP of `192.168.42.129` when tethered via USB

1. Firstly, power on Flo Edge and wait for it to boot completely
2. Connect a type-C to USB-A cable between Flo Edge and your computer
3. `ssh` into Flo Edge via terminal as `root` user
    ```bash
    ssh root@192.168.42.129
    ```

## Wireless Hotspot
> Flo Edge has a static IP of `192.168.43.1` when connected over hotspot

1. Power on Flo Edge and wait for it to boot completely
2. Connect your computer to the network `Flo Edge One`. Password is `floedge123`
3. `ssh` into Flo Edge via terminal as `root` user
    ```bash
    ssh root@192.168.43.1
    ```

> Note : In case you have multiple Flo Edge devices, be sure only a single device is powered on when doing so

## Network related APIs
Flo Edge comes with an sdk and [cli tool](/docs/anx) to faciliate ease of use

### Change Hotspot
It is recommended to change the SSID and password for your Flo Edge when working with 
multiple devices, in order to prevent cross connections. To do so, we've provided a command in the cli tool to help you

```bash
anx set_hotspot <ssid> <password>
```

### Connecting to a known wireless network
If you have a known network and want to connect your Flo Edge to it, use
```bash
anx set_wifi <ssid> <password>
```

### Stats
#### Hotspot Stats
> As of now, Flo Edge only supports a 2.4GHz wireless hotspot

To see number of clients connnected to yout Flo Edge, run the following
```bash
anx hotspot_stats
```

#### Wifi Stats
To see stats related to the wireless network your device is connected to
```bash
anx wifi_stats
``` 

#### Cellular Stats
If your Flo Edge has a SIM card inserted, you'd be able to see stats related to it using
```bash
anx cellular_stats
``` 