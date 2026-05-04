# ESPHome-Configs
Here are some of my personal ESPHome projects. I've coded some from scratch, but some configs I've gotten online and then refactored to my liking. I've tried to keep them simple and mostly lambda free for simple stuff.

# How To Use
These files *do not include* the usual `logger:`, `api:`, etc because my intended purpose for these is to be drop in. 

The best way to use them is by using [!include](https://esphome.io/components/packages/#local-packages). For example, follow the prompts in the ESPHome Device Builder to create an initial YAML, then add an include file referencing one of these files *(please move to your disk rather than using GitHub, as I may move the structure around!)*. Then, you can write the unique config for the particular device.

### Example of a simple node:
```
esphome:
  name: esphome_node
  friendly_name: ESPHome Node

packages:
  - !include ESPHomePackages/basics.yaml # This adds the restart button and basic universal sensors
  - !include ESPHomePackages/ipv6.yaml # This package adds IPv6 and related sensors
  - !include ESPHomePackages/Hardware/full-vanilla.yaml # This sets up the board specifics, such as board type, GPIOs of onboard LEDs and the BOOT button

# Put your unique config here, e.g LVGL, sprinkler relays, buzzer, mmWave, BME680...
  
# Enable logging
logger:

# Enable Home Assistant API
api:
  encryption:
    key: "YOUR_KEY_HERE"

ota:
  - platform: esphome
    password: "YOUR_PASSWORD_HERE"

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "ESPHome Node Fallback Hotspot"
    password: !secret ap_password # You can hardcode it here but I recommend adding a simple ap_password line in your secrets.yaml

captive_portal:
```

# Think of an improvement? Please share!
Have an issue? Create an issue! I'd love to look into any issues and fix them.
Also, I am always adding new functionality and making the code even simpler. If you improve my code in any way, or implemement it into a cool project, please share *(if you'd like)*! PRs welcome. 

*(Note: I don't really care for a ton of lambda and complexity so if your improvement is adding a bunch of really complex lambdas and automations you might make your own repo for those :D)*
