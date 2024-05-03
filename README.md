# esphome-dashboard

This is a playground for ESP32 microcontrollers connected to Home Assistant via ESPHome. I aim to create a physical home dashboard that displays relevant information at the house. Thanks [@bodnaristvan](https://github.com/bodnaristvan) and [@zmetser](https://github.com/zmetser) for your help setting these up. Thanks to [@madelena](https://github.com/Madelena) for publishing her [Weatherman Dashboard](https://github.com/Madelena/esphome-weatherman-dashboard), most of this work is based on that. 

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

The default config fetches data from BKK servers using the `bkk_stop` plugin. Update this config to change stop or route ids. To find a `stopId`, use the Swagger documentation provided by BKK: https://editor.swagger.io/?url=https://opendata.bkk.hu/docs/futar-openapi.yaml or the interactive map here: https://futar.bkk.hu/stop/BKK_F01029. 


### Dashboard configuration
Download `dashboard.yaml` and `sensor.yaml` to a directory under config (esp-test in this example). 

Merge the `configuration.yaml` file with your pre-existing HA config.

The included dashboard contains a simple card for showing all buses and trams at an example station.

After a restart, you should see a new dashboard in the HA sidebar, showing a single card with the BKK stop card.

## ESP display
The included `esphome-web-160662.yaml` file contains all the information and examples to display BKK bus and some weather data. 

This is the current implementation, showing start times for buses in a stop (in Hungarian), the current time and weather temperature and conditions. 

<img width="612" alt="image" src="https://github.com/eszpee/esphome-dashboard/assets/980563/9589ed10-8ce7-48fd-83ae-f25447b1a962">

