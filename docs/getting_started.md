---
layout: default
title: Getting started
nav_order: 2
---
# Getting started

## Requirements
1. FloEdge
2. FloEdge attachment
3. Power source(12V 3A)

## Turning on
1. Connect power source.
2. Led on FloEdge attachment will start blinking red.
3. When led becomes solid green FloEdge is up and running.
4. Connect to FloEdge hostpot (ssid: "FloEdge", password: "FloEdge")
5. ssh to FloEdge using cmd {ssh root@192.168.43.1 -p 2222}
6. Now you are in a preconfigure debian OS for robotics and ai application.
7. [anx_interface]({% link docs/anx_interface.md %}) will be available to interact with the system.

## Turning off
1. Using [anx_interface]({% link docs/anx_interface.md %})
2. Long press the power button on FloEdge attachment
  - Led on FloEdge attachment will start blinking green.
  - When FloEdge is turned off led will become solid red.

## Operating condition
- Temperature: 5 - 65 degree celsius
