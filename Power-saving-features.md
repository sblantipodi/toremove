## Turn off LEDs during long inactivity periods

<img align="center" width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/power_saving.jpg?raw=true">

Firefly can turn off the LEDs after the captured colors remain unchanged for a configurable time. Select the power saving timeout in **Misc** or the web interface.

This also applies to HDMI capture: a paused picture or static source can trigger the timeout even if the TV is still on. Screensaver detection is a separate Windows desktop feature. A normal host shutdown can turn the LEDs off; abruptly removing host power is not the same as a clean shutdown.

---

## Add a relay to cut power to the LED strip

Each LED on the strip has its own tiny controller, meaning the strip **still consumes power even when all LEDs are off**.  
For example, a WS2812B LED strip with 300 LEDs consumes up to **6W** when off.

Including a **power relay** can prevent this energy waste.

Some devices, like **DigUno** and certain **Gledopto models**, have an integrated relay.  
Even with an integrated relay, you must configure the **relay GPIO** in Luciferin.

<img align="center" width="250" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/relay.jpg?raw=true">

### Relay installation options

1. Add a relay in the **DC path** after the LED power supply.
2. Add a relay in the **AC path** before the LED power supply.

> You can still power the ESP via USB using a separate power supply (e.g., a phone charger).

`Luciferin` controls the relay as follows:

- Sends a **HIGH signal** to the GPIO a few milliseconds **before** the LEDs are turned on
- Sends a **LOW signal** a few seconds **after** the LEDs are turned off

Relay GPIOs depend on the chip, board, and any module wiring. Check [Supported GPIO and Baud Rate](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate) or your prebuilt board documentation before configuring the relay.

> Note: Some devices, like certain **GLEDOPTO** models, require the GPIO signal to be **inverted**.  
> You can enable this option in the GPIO settings.

Learn more about [how to change the GPIO in use](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate#how-to-change-the-gpio-in-use).

---

**Check the relay rating before using it.**
- DC rating is usually different from AC rating

<!-- Screenshot: current power-saving timeout and controller relay settings. -->
