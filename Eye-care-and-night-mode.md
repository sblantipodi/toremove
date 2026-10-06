These settings adjust lighting comfort for **PC or HDMI capture**. Configure them in **Misc** in Firefly's dedicated desktop interface, or through its web interface when using a host without a desktop.

## Night Mode

Luciferin offers several **eye care** features, starting with **Night Mode**, which can be enabled directly from the **Misc** tab.

Set a reduction percentage above **0%** and a start/end time. During that interval, Firefly reduces LED brightness by the chosen percentage; **0%** disables Night Mode.

<img align="center" width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/night_mode.jpg?raw=true">  

## Eye Care Dialog

By clicking the **`☰`** button, you can access the **Eye Care** dialog, where additional eye care features can be enabled.

<img align="center" width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/eye_care_dialog.jpg?raw=true">  

The Eye Care dialog provides the following features:

- **Night light:** Uses warmer colors to reduce blue light exposure. Increasing the level blocks more blue light. The **Auto** option follows the host operating system's night light state where supported. For a Raspberry Pi without a desktop or a system without that integration, use an explicit setting instead.
- **Luminosity threshold:** Prevents LEDs from turning completely off during black scenes, using a soft and gentle light instead.
- **Peak brightness limit:** Limits peak brightness without affecting low brightness scenes.
- **Light Dependent Resistor (LDR):** Automatically adjusts LED brightness based on ambient light using an external sensor.  
  The following options require an LDR sensor:
  - **Room brightness:** Current brightness level detected by the LDR.
  - **LDR reading interval:** Time interval (in minutes) between brightness readings.
  - **Turn off LEDs during readings:** Temporarily turns off LEDs during LDR readings, useful when the sensor is close to the LEDs.
  - **Minimum LED brightness:** Ensures a minimum brightness level when the room is very dark.
  - **Calibrate LDR:** Uses the current room brightness as the maximum reference level for brightness adjustment. Calibration takes up to 5 seconds.

## Automatic Brightness Control Using LDR

A photoresistor, also known as a **Light Dependent Resistor (LDR)**, is a passive component whose resistance decreases as the amount of incoming light increases.

<img align="center" width="700" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/CAD_schematics/luciferin_official_pcb/img/ldr_image.jpg?raw=true">

Luciferin can use this inexpensive component to automatically adjust LED strip brightness based on the ambient light level in the room.

This feature is optional but requires an LDR paired with a **10 kΩ resistor**.  
The **GL5516** LDR is a good choice for this purpose.

### Wiring

If you are using the [Luciferin Official PCB](https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB), simply connect:
- the LDR to the **R5** silkscreen
- the 10 kΩ resistor to the **R4** silkscreen

Once automatic brightness control is enabled, **manual brightness adjustment is disabled**.

If your room is not particularly bright and you want to use the current ambient light as the maximum brightness reference, you can calibrate the LDR by clicking the **`✔`** button.  
The current room brightness will then be used as the maximum reference level for LED brightness adjustment.

> Connect the LDR circuit to an **ADC capable pin** supported by your board and configure that pin in Glow Worm. ADC resolution and usable pins vary by chip; a non ADC pin is not a suitable substitute for analog brightness measurement.

Learn more about [how to change the GPIO in use for LDR](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate#how-to-change-the-gpio-in-use).

---

If you want to reduce eye strain even further, take a look at the  
[Smoothing feature using Linear Interpolation with Frame Insertion](https://github.com/sblantipodi/firefly_luciferin/wiki/Smoothing-color-transitions).

<!-- Screenshot: current Eye Care controls in Firefly's web interface, including LDR status and calibration. -->
