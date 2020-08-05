---
title: Crownstone
description: Instructions on how to setup the Crownstone integration within Home Assistant.
ha_release: 0.114
ha_iot_class: Cloud Polling
ha_category:
  - Light
  - Switch
ha_codeowners:
  - '@Crownstone'
  - '@RicArch97'
ha_config_flow: true
ha_domain: crownstone
---

The **Crownstone** integration brings all functionality from [Crownstone](https://crownstone.rocks/) to Home Assistant!

The Crownstone integration supports the following devices:

- Crownstone plug (Can be plugged directly into an existing power outlet)
- Crownstone built-in one (Is built into the power outlet enclosure)

## Configuration

To add the Crownstone integration, do the following:

1. In the Home Assistant UI, Go to Configuration >> Integrations.
2. Select **Crownstone** from the list.
3. Enter your Crownstone account credentials.
4. Enter a Sphere name of a Sphere you have set up in the Crownstone app. Sphere names are currently case sensitive.

After that your Crownstone data will be loaded into Home Assistant.

## Crownstones (Lights)

Crownstones have the ability to dim, however dimming is disabled by default. To enable dimming for a Crownstone:

1. go to your Crownstone app.
2. Tap on a Crownstone that you want to be able to dim.
3. Tap on **Abilities**
4. Turn **Dimming** on

When you have changed an ability through the Crownstone app, the change will be automatically updated in Home Assistant. However, the Crownstone app uses a 10 minute interval to sync changes with the cloud, so it can take 10 minutes before the change is updated in Home Assistant.

Enabling dimming is at own risk. It is recommended to only use dimming on lights.

## Crownstone USB

The default connection method of the Crownstone integration is Cloud Polling. However a [Crownstone USB](https://shop.crownstone.rocks/products/crownstone-usb-dongle) is available. Instead of switching and dimming Crownstones using the Cloud, this dongle hooks directly into the Crownstone mesh to switch Crownstones, which means the latencies are really low.

The Crownstone USB functionality is built into the Crownstone integration and is plug-and-play. This means a Crownstone USB can be connected to the computer that runs Home Assistant (e.g. a Raspberry Pi) at any time. If a Crownstone USB is connected, switching Crownstones will be done using the dongle. When the dongle is removed, the Cloud will be used again.
