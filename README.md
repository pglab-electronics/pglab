# pglab Home Assistant Integration

## Overview

This integration allows you to control [PG LAB Electronics](https://www.pglab.dev/) devices in Home Assistant.

## Installation

To install the integration manually.

1. Create a `config/custom_comoponents` directory if it doesn't already exist
2. Clone this repo and move `pglab` into `config/custom_components`. Your directory tree should look like `config/custom_components/pglab/...files...`.
3. Restart Home Assistant

## Supported devices

- [E-Board](https://www.pglab.dev/e-board): Controller board to interface I2C devices by a local LAN connection.
- [E-Relay](https://www.pglab.dev/e-relay): 8 Channels relay board controlled by I2C connection.
- [E-Switch]: Coming soon

## Requirements

- MQTT broker and the [MQTT integration](/integrations/mqtt/) set up in Home Assistant.
- PG LAB Electronics devices MQTT setting configured to communicate with the MQTT broker.

Once the device is connected to your MQTT broker, it should be discovered by Home Assistant.
Add PG LAB Electronics integration.

## Device configuration

Configure each PG LAB Electronics devices following these steps:

- Power the device and connect it to your local network.
- Get from your router the IP address of your device (example: 192.168.1.7).
- Connect to the internal device web server with a web browser (**don't** use 'https://...', instead connect to 'http://192.168.1.7').
- Change the default device name. Use a unique meaningful name such as: E_Board_Office, E_Board_Garden etc.
- Setup MQTT broker address, port number, username and password.
- Save the configuration and restart the device.

**Note:** Every device **MUST** have a unique name.  

## Supported features

PG LAB Electronics Relays, Shutters and Switches are supported.

- PG LAB Relays will be added as Home Assistant `switch` entities.
- PG LAB Shutters will be added as Home Assistant `cover` entities.
- The integration will also create diagnostic Status Sensors, with device different information.

