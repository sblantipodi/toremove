## Home Assistant integration
<img align="right" width="100" height="100" src="https://avatars3.githubusercontent.com/u/13844975?s=200&v=4">

MQTT connects Luciferin to Home Assistant for lighting controls, profiles, effects, and status sensors.

Before discovery, enable Home Assistant's MQTT integration and configure **Firefly and Glow Worm FULL** to use the same reachable broker with matching device topics. MQTT is optional for normal UDP lighting, but required for this integration.

<img align="center" width="1000" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/ha_luciferin.jpg?raw=true">

Once `Firefly Luciferin` is up and running, please follow the steps below:
- `Settings` -> `Network tab` -> `MQTT discovery topic`
- Click the `✔` button

Entities will be automatically added to `Home Assistant` via MQTT Auto Discovery.  
You can customize the `MQTT discovery topic` or use the default one for `Home Assistant`.

<img align="center" width="450" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/ha_integration_auto.jpg?raw=true">  

As soon as you click the button, all entities will be available in `Home Assistant`. Open a dashboard and add them to it.  
Entity names contain the `Luciferin` keyword, making them easy to find.  
If you have more than one `Glow Worm Luciferin` device, the entity will contain the name of the MQTT topic the device is using.

The following names are examples; actual entity IDs depend on device topics, discovery, and any Home Assistant renaming. Controller entities describe Glow Worm, while capture, profiles, gamma, and LUT settings belong to Firefly and require it to be running.

| Entity                                   | Description                                                                                           |
|------------------------------------------|-------------------------------------------------------------------------------------------------------|
| `light.luciferin_switch`                 | Turn on/off light, change color and brightness.                                                       | 
| `select.luciferin_effect_selector`       | Choose your preferred effect.                                                                         |
| `select.luciferin_color_mode`            | Choose between RGB, RGBW, RGBW mixed (Brighter), RGBW (RGB only) mode.                                |
| `select.luciferin_aspect_ratio`          | Switch aspect ratio between Fullscreen, Pillarbox, Letterbox, Auto.                                   |
| `select.luciferin_gamma`                 | Choose the preferred gamma.                                                                           |
| `select.luciferin_frame_generation`      | Smoothing control for Frame generation.                                                               |
| `select.luciferin_smoothing_ema`         | Smoothing control for Exponential Moving Average (EMA).                                               |
| `select.luciferin_profiles`              | Choose the profile you want to use.                                                                   |
| `number.luciferin_white_temp`            | Choose white temperature.                                                                             |
| `button.luciferin_reboot_glow_worm`      | Reboot Glow Worm device.                                                                              |
| `sensor.luciferin_glow_worm_version`     | Glow Worm Luciferin version.                                                                          |
| `sensor.luciferin_number_of_leds`        | Number of LEDs in use on the Glow Worm Luciferin device.                                              |
| `sensor.luciferin_gpio`                  | GPIO in use on the Glow Worm Luciferin device.                                                        |
| `sensor.luciferin_wifi`                  | Glow Worm Luciferin WiFi signal strength.                                                             |
| `sensor.luciferin_adaptive_gamma`        | Current Adaptive Gamma.                                                                               |
| `sensor.luciferin_last_update_glow_worm` | Last time Glow Worm device was sighted. Useful to check if the device is alive.                       |
| `sensor.luciferin_firefly_producing`     | Firefly capture framerate, for PC screen or HDMI input (FPS).                                                     |
| `sensor.luciferin_firefly_consuming`     | Firefly Luciferin throughput, shows how fast Luciferin is sending data to the Glow Worm device (FPS). |
| `sensor.luciferin_glow_worm_consuming`   | Shows how fast Glow Worm Luciferin is processing the received data (FPS).                             |
| `sensor.luciferin_ldr`                   | Reading of the LDR from 0% to 100% (room brightness).                                                 |
| `switch.luciferin_bias_light`            | Start and stop PC screen or HDMI capture on Firefly Luciferin.                                               |

![SCREENSHOT](https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/img/HA_mobile_client_screenshot.jpg?raw=true)

The integration also exposes a **3D LUT** selector in supported versions. See [HDR to SDR and LUT](https://github.com/sblantipodi/firefly_luciferin/wiki/HDR-to-SDR-and-LUT).

For application and controller update behavior, see [Update management](https://github.com/sblantipodi/firefly_luciferin/wiki/Luciferin-update-management).

<!-- Screenshot: current Home Assistant entities, including adaptive gamma and 3D LUT. -->

---

## Google Home integration via HA
Please configure [Google Home with Home Assistant](https://www.home-assistant.io/integrations/google_assistant),  
then adapt this example in your `configuration.yaml`, replacing the entity ID and room with your own:

```yaml
google_assistant:
  expose_by_default: false
  entity_config:
    light.glowworm:
      name: "glowworm"
      room: 'Roomname'
```
Be sure that your `ESP` is connected to WiFi/MQTT network, [quick guide here](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access).