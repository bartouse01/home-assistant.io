---
title: Suez Water
description: Instructions on how to integrate Suez Water daily data within Home Assistant.
ha_release: 0.97
ha_category:
  - Sensor
ha_iot_class: Cloud Polling
ha_config_flow: true
ha_codeowners:
  - '@ooii'
ha_domain: suez_water
ha_platforms:
  - sensor
ha_integration_type: integration
---

The Suez Water integration fetches your last day consumption of water from the French water provider [Tout Sur Mon Eau](https://www.toutsurmoneau.fr) website.

Prerequisite: The residential water meter needs to be a connected one ([Help here](https://www.toutsurmoneau.fr/edito/compteur-intelligent-connecte)). If you don't have this type of device, then the integration will not collect data.

It also gets the following data:

- Daily consumption for the current month
- Daily consumption for the previous month
- Monthly consumption for the last 26 months
- Highest monthly consumption
- Last year total consumption
- Current year total consumption

{% include integrations/config_flow.md %}



`counter_id` is the water counter id:

- To find this id, log in to your account [Tout Sur Mon Eau](https://www.toutsurmoneau.fr) with Chrome browser.

- Once logged in your account, it can be found in the source code your _Tout Sur Mon Eau_ [user account](https://www.toutsurmoneau.fr/mon-compte-en-ligne/historique-de-consommation-tr)

- Press Ctrl+U to switch to Source code of the page.

- Press Ctrl+F and look for `statMData`.

- You should land on the line with : `/mon-compte-en-ligne/statMData' + '/123456789'`

- The `counter_id` in this case is `123456789`.
