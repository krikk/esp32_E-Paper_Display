# esp32_E-Paper_Display


<p align="center"> <img src="images/front.jpg" width="300"><img src="images/back.jpg" width="300"></p>
<p align="center"> <img src="images/side.jpg" width="300" > <img src="images/inside.jpg" width="300" ></p>

This is the documentation of my self-build ESP32 based E-Ink Display for displaying Smart Home Data. All of this is heavily inspired on this thread: https://community.home-assistant.io/t/e-paper-display/138625/92

But as I am a OpenHAB user, it is all based on MQTT, and this is still work in progress...

Used Hardware:
- [Thingpulse ePulse – Low Power ESP32 development board](https://thingpulse.com/product/epulse-low-power-esp32-development-board/) 
- [Waveshare 7.5inch e-Paper HAT](https://www.waveshare.com/wiki/7.5inch_e-Paper_HAT)
- 2 x [18650 Battery Holder](https://www.aliexpress.com/item/4000066839172.html)
- 4 x [Liitokala 18650 3400mAh Li-Ion NCR18650B rechargeable Li-lon](https://www.aliexpress.com/item/32362625564.html)
- 1 x 220 kOhm resistor (for the voltage divider)
- 1 x 100 kOhm resistor (for the voltage divider)

The battery holders are connected in serial, so that we have an output voltage of 8.4 V max and 5 V min, to monitor battery level i build a voltage divider:
Input 8.4 V
R1 = 220kOhm
R2= 100kOhm
Out: 2.625V



Used Software:
- [ESPHome](https://esphome.io/index.html)
- you find my code in this repository
- the BLE part is disabled, because of memory problems...

To correctly compile this you have to create a secrets.yaml file within the root directory of the project with the following content:
```console
wifi_ssid: "yourssid"
wifi_password: "yourpassword"
api_password: "yourpassword"
ota_password: "yourpassword"
mqtt_host: 192.168.1.111
mqtt_user: mqttuser
mqtt_password: mqttpassword
```
