# esp-test

## Installation
Checkout the repo to your HA config folder.

Install HACS.

Install the following HACS addons:
https://github.com/amaximus/bkk-stop-card/
https://github.com/amaximus/bkk_stop/

### Sensor configuration
Link the included `sensor.yaml` in your HA config:
```
sensor: !include esp-test/sensor.yaml
```

The default config fetches data from BKK servers using the `bkk_stop` plugin. Update this config to change stop or route ids. To find a `stopId`, use the Swagger documentation provided by BKK: https://editor.swagger.io/?url=https://opendata.bkk.hu/docs/futar-openapi.yaml


### Dashboard configuration
Add the following to your HA config: 
```
lovelace:
  mode: storage
  # Add yaml dashboards
  dashboards:
    lovelace-yaml:
      mode: yaml
      title: BKK
      icon: mdi:script
      show_in_sidebar: true
      filename: esp-test/dashboard.yaml
```
Note that `filename` here points to the dashboard config in the downloaded repo.
The included dashboard contains a simple card for showing all buses and trams at the Gardonyi station.

After a restart, you should see a new dashboard in the HA sidebar, showing a single card with the BKK stop card.

## ESP display
TODO!
Use the included `esp-device-config.yaml` file, and fix it!
