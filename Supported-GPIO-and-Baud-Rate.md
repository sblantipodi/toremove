GPIOs determine where the LED data, relay, button, and LDR connect to the **Glow Worm controller**. Defaults below are chip family defaults; prebuilt boards and Luciferin modules can have different wiring or saved overrides.

Choose pins supported by the specific board. This page concerns the LED controller, not the host's HDMI USB capture card.

---

### ESP32-S3

- **LED GPIO16 (Default)**: Hardware accelerated GPIO using DMA
- **Relay GPIO13 (Default)**
- **Button GPIO0 (Default)**
- **LDR GPIO2 (Default)**

--- 

### ESP32-S2

- **LED GPIO16 (Default)**: Hardware accelerated GPIO using DMA
- **Relay GPIO9 (Default)**
- **Button GPIO0 (Default)**
- **LDR GPIO3 (Default)**

---

### ESP32-C5

- **LED GPIO0 (Default)**
- **Relay disabled by default**; select a suitable pin if your board uses a relay. GPIO13, GPIO14, and GPIO15 are reserved in this firmware configuration.
- **Button GPIO1 (Default)**
- **LDR GPIO6 (Default)**

---

### ESP32-C6

- **LED GPIO5 (Default)**: Hardware accelerated GPIO using DMA
- **Relay GPIO15 (Default)**
- **Button GPIO1 (Default)**
- **LDR GPIO2 (Default)**

---

### ESP32-C3

- **LED GPIO6 (Default)**: Hardware accelerated GPIO using DMA
- **Relay GPIO0 (Default)**
- **Button GPIO9 (Default)**
- **LDR GPIO3 (Default)**

---

### ESP32

- **LED GPIO2 (Default)**: Hardware accelerated GPIO using DMA
- **Relay GPIO12 (Default)**
- **Button GPIO0 (Default)**
- **LDR GPIO36 (Default)**

---

### ESP8266

- **LED GPIO2 (Default)**: Hardware accelerated GPIO using UART (recommended for using both Wireless Stream and USB)
- **LED GPIO3**: Hardware accelerated GPIO using DMA (fastest for Wireless Stream, USB will not work)
- **LED GPIO5**: Standard GPIO, no hardware acceleration (prefer GPIO2 or GPIO3)
- **Relay GPIO12 (Default)**
- **Button GPIO0 (Default)**
- **LDR A0 (Default)**: the ESP8266 analog input

---

> Using the [Luciferin Module for the Official PCB](https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB)?  
> Check [Supported GPIO on Modules](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-on-Modules).

> **Tip:** GPIOs can be changed on the fly on both **Full** and **Light firmware** from the **Firefly Luciferin** settings.  
> Curious about achievable framerate? See [Very Fast Capture](https://github.com/sblantipodi/firefly_luciferin/wiki/Very-fast-capture).

---

## How to change the GPIO in use

1. Open the **Devices** tab in Firefly Luciferin.
2. Double click the GPIO you want to change.
3. Press **Enter**.

<img width="900" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/gpio3.jpg?raw=true">  

> It may take a moment for the UI to register the change.
> Once changed, restart the capture for it to take effect.

You can also **invert the relay GPIO** for devices that require it, e.g., [Gledopto](https://github.com/sblantipodi/firefly_luciferin/wiki/Compatible-Hardware#pre-built-boards-support).

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/gpio2.jpg?raw=true">  

GPIOs can also be changed via the **[Web Interface](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access#luciferin-web-interface)** if you are using the **FULL firmware**.

<img align="center" width="750" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/img/web_interface_gpio.jpg?raw=true">

---

<!-- Screenshot: current Firefly web device controls for LED, relay, button, and LDR GPIOs. -->

## Baud rate

Baud rate affects **USB serial communication with the LED controller**. It does not set the USB capture card's frame rate and does not change WiFi/Ethernet streaming speed.

- If experiencing flickering **and** your hardware is correctly connected, try **lowering the baud rate**.
- To increase maximum framerate, **increase the baud rate**.

**Recommended maximums:**
- ESP8266 with **CH340**: up to 1,000,000 baud
- ESP8266 with **CP2102**: up to 921,600 baud

> An unsupported baud rate can break serial communication. FULL controllers may still be reachable over the network; LIGHT controllers may require a manual firmware/settings recovery.

**Default baud rates:**
- Light Firmware: **500K**
- Full Firmware: **115200**
