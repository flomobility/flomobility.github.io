---
layout: default
title: anx
nav_order: 6
permalink: /docs/anx
---

# anx

> anx is a cli tool to interact with FloEdge (i.e. reboot, shutdown, stream_imu etc...). Use `anx --help` to know more about it.

## Rebooting device
```bash
anx reboot
```

## Shutting down
```bash
anx shutdown
```

## Reset File system
In case you need to reset your Flo Edge's file system, use
> Beware : This would essentially do a factory reset of your rootfs

```bash
anx reset_fs
```

## Identiy
Every Flo Edge comes with dual SIM card support, which means it has 2 IMEI numbers.
This serves as the unique identity for your Flo Edge
```bash
anx imei_numbers
```

## Logging
To help us catch and fix any bugs, we've added support to capture system logs.
In case you do face any issue while using your Flo Edge, be sure to share your system logs with us and we'll be on top of fixing it.
> Note : Logs are located in the `/root/.logs/system` folder in your rootfs

```bash
# To start logging
anx start_android_logs

# To stop
anx stop_android_logs
```
