If you are using **NVIDIA Surround** or **AMD Eyefinity**, you **do not need** to configure Luciferin for multi monitor setups, because these technologies manage multiple monitors as a single display.

Luciferin supports **dual- and triple monitor PC setups** with USB or network connected controllers. Network streaming can use UDP; **MQTT is optional**.

This page describes multiple PC displays. For external HDMI sources on a PC or Raspberry Pi, follow [Quick start](https://github.com/sblantipodi/firefly_luciferin/wiki/Quick-start).
You can choose to use:

- **One microcontroller for all monitors**
- **One microcontroller per monitor**

Note: driving a large number of LEDs on a single microcontroller can be problematic.  
Please take a look at [these benchmarks](https://github.com/sblantipodi/firefly_luciferin/wiki/Very-fast-capture) to get an idea of how many LEDs your microcontroller can realistically handle.

---

## Pros of one microcontroller per monitor
*(1 LED strip per monitor, driven by a dedicated microcontroller)*

- No daisy chaining between monitors, no “flying” connections.
- Each controller handles its own strip, reducing the LED count processed by a single controller.
- Individual monitor control: for example, in a triple monitor setup you can game on a single monitor while keeping others independent.
- Full flexibility in configuring the LED layout.

---

## Pros of one microcontroller for all monitors
*(1 single LED strip for all monitors, driven by 1 microcontroller)*

- Light effects like **rainbow** or similar can be synced across the entire LED strip.
- Easier wiring and simpler troubleshooting.

---

## How to set up multiple monitors

1. Connect the controllers and configure their network or USB connections. For FULL firmware, start with UDP streaming; configure MQTT only if you want broker based control/integration.

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/multi_display/multimonitor_1.jpg?raw=true">

2. In the **Devices** tab, select dual or triple display as needed.
    - Choose **"Single device"** if you want **one microcontroller for all monitors**
    - Click **Save**.

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/multi_display/multimonitor_3.jpg?raw=true">

3. Firefly starts an **instance for each monitor**, coordinating the capture/output setup. In a desktop session, each instance has a tray icon:

<img width="100" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/multi_display/triple_monitor_tray_grey.jpg?raw=true">

4. **Right click** the tray icon to configure the number of LEDs on that monitor:

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/multi_display/multimonitor_7.jpg?raw=true">

5. If using **one microcontroller per monitor**, configure an **output device** for each monitor:
    - Use **COM ports** for USB connection
    - Use **Device Name** for Wireless Stream

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/multi_display/multimonitor_6.jpg?raw=true">

> If using a **single microcontroller**, Firefly Luciferin will generate a **Gold instance**.  
> The gold instance acts as the master controlling all monitors.

<img width="100" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/multi_display/gold_instance.jpg?raw=true">

---

## Screen capture quality

Adjust the screen capture quality in the **Mode** tab:

- **Balanced (recommended):** Best option for most users
- **High quality:** Higher precision, but uses more system resources
- **Low quality:** Reduces system load, useful for less powerful machines or multi screen setups with high resolutions

<!-- Screenshot: current multi-monitor and Single device settings, plus Output device selection in Devices. -->

When using one controller, the coordinating instance combines the monitor colors into the configured strip layout. Check each monitor's LED order with the [Test Image](https://github.com/sblantipodi/firefly_luciferin/wiki/Test-image-and-latency-test).
