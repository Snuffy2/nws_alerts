# Alerts from the US National Weather Service  (nws_alerts)

This integration retrieves updated weather alerts every minute from the US NWS API (by default but it can be changed in the config options).

You can configure the integration to use your NWS Zone, your precise location via GPS coordinates, or you can get dynamic location alerts by configuring the integration to use a device_tracker entity from HA as long as that device tracker provides GPS coordinates.

The integration presents the number of currently active alerts as the state of the sensor and lists many alert details as a list in the attributes of the sensor.

You can send specified alerts to the HA Mobile App or Announce them via Alexa devices.

You can also display the generated alerts in your frontend. For example usage see: https://github.com/Snuffy2/nws_alerts/blob/main/lovelace/alerts_tab

## Installation
  
### HACS

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Snuffy2&repository=nws_alerts&category=integration)

1. Confirm adding the custom repository if prompted

1. Download NWS Alerts

1. Restart Home Assistant

<details>
<summary><h3>Manually</h3></summary>

You probably <u>do not</u> want to do this! Use the HACS method above unless you know what you are doing and have a good reason as to why you are installing manually

1. Using the tool of choice open the directory (folder) for your HA configuration (where you find `configuration.yaml`)

1. If you do not have a `custom_components` directory there, you need to create it

1. In the `custom_components` directory create a new folder called `nws_alerts`

1. Download _all_ the files from the `custom_components/nws_alerts/` directory in this repository

1. Place the files you downloaded in the new directory you created

1. Restart Home Assistant

</details>

## Adding Integration

[![Open your Home Assistant instance and install an integration.](https://my.home-assistant.io/badges/config_flow_start.svg)](https://my.home-assistant.io/redirect/config_flow_start/?domain=nws_alerts)

<details>
<summary><h3>Manually</h3></summary>

1. Configure the integration by going to `Settings->Integrations`

1. Click on `+ Add Integration` button in the bottom right corner.

1. Search for `NWS Alerts` and select it to add the integration and start configuration.

</details>

## Configuration

NWS Alerts will default in the nearest Zones based on your Home location set in in HA. You can find other Zone or County IDs by going to [https://alerts.weather.gov/](https://alerts.weather.gov/). Scroll down to your state and click on the `zone list` and/or `county list` to find the desired entries.

There are a few configuration method options to select from. Please see the following link to help you decide which option to use: https://github.com/Snuffy2/nws_alerts/blob/main/lookup_options.md

If you select the `Using a device tracker` option under the `GPS Location` option then HA will use the GPS coordinates provided by that tracker to query for alerts so you should follow the same recommendations for using GPS coordinates when using that option.

Enable Send Alerts to Send specified alerts to the HA Mobile App or Announce them via Alexa devices.

## Previous Authors

Originally by @eracknaphobia

Forked from @finity69x2