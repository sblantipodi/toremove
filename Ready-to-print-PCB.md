## Official Printed Circuit Board for Luciferin
<a name="unlike-other-pre-built-boards-the-official-pcb-is-upgradable"></a>

#### Unlike other prebuilt boards, the official PCB is **upgradable**!
<p align="center">
  <a href="https://raw.githubusercontent.com/sblantipodi/glow_worm_luciferin/refs/heads/master/assets/CAD_schematics/luciferin_official_pcb/img/PCB_front.jpg">
    <img width="900" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/CAD_schematics/luciferin_official_pcb/img/PCB_front.jpg?raw=true">
  </a><br>
  <em>(click the image to zoom)</em>
</p>

If you prefer assembling a controller to buying a prebuilt board, **Luciferin's official PCB** provides a ready to manufacture design. You need a soldering iron and the listed components; no PCB design work is required.

---

## How to Create Your Luciferin PCB

> 1. Download the [GERBER file for the Luciferin Official PCB](https://github.com/sblantipodi/glow_worm_luciferin/raw/master/assets/CAD_schematics/luciferin_official_pcb/Gerber_Luciferin_ESP8266_PCB_V1.1_final.zip)

2. Upload the GERBER file to your favorite PCB manufacturer.  
   If you want to use **JLCPCB**, follow [this guide](https://jlcpcb.com/help/article/how-do-i-place-an-order).

3. Order all the required components.

## Bill of Materials (BOM)

### Main Board
- **D1 Mini format board with a ESP32 or ESP8266 chip**, for example.
  - Lolin ESP32-S3 Mini
  - Lolin ESP32-C3 Mini
  - Lolin ESP32-S2 Mini
  - Lolin ESP8266

  **Note:**  
  For new purchases, preference should be given to newer chips such as the ESP32-S3 or ESP32-C6/C5 families.

### Electronic Components
- 74AHCT125N (logic level converter 3.3V → 5V) **Align the notch correctly before soldering**
- 1500 µF 16V capacitor
- 100 nF capacitor
- 3 × 330 Ω resistors (R1, R2, R3)
- WS2812B 5V LED strip
- Fuse holder (Keystone Electronics **3557-2**)
- Full size **ATO fuses**
    - WS2812B consumption: up to **0.060 A per LED**
    - Example: 100 LEDs → ~6 A, Recommended fuse: **7.5 A**
- Header pins (2.54 mm)
- Jumpers (2.54 mm)
- 5 × 2-pin terminal blocks (5.08 mm)

### Optional (Auto Brightness)
- LDR **GL5516** (R5)
- 10 kΩ resistor (R4)  
  [Auto brightness documentation](https://github.com/sblantipodi/firefly_luciferin/wiki/Eye-care-and-night-mode#automatic-brightness-control-using-ldr)

## Assembly

4. Solder all components following the PCB silkscreen.
5. Check the connections and configured GPIOs, install Glow Worm firmware, then follow [Quick start](https://github.com/sblantipodi/firefly_luciferin/wiki/Quick-start).

---

## Parts Overview (Soldering Video)

<p align="center">
  <a href="https://youtu.be/J4TE75ME86w">
    <img width="900" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/CAD_schematics/luciferin_official_pcb/img/all_parts_play.jpg?raw=true">
  </a>
</p>

## Fully Assembled PCB

<p align="center">
  <img width="900" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/CAD_schematics/luciferin_official_pcb/img/all_parts_assembled.jpg?raw=true">
</p>

---

## How to Connect the LED Strip

- Connect the power supply to the **first terminal block** (+ IN −)
- Connect the LED strip power to the **second and third terminal blocks** (+ OUT −)
- Connect the **data pin** of the LED strip to the **fourth or fifth terminal block**
    - Using the **ALL** position allows GPIO switching via jumper
- Configure GPIOs: [documentation here](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate)
- Optional relay support: [documentation here](https://github.com/sblantipodi/firefly_luciferin/wiki/Power-saving-features#add-a-relay-to-cut-power-to-the-led-strip)

**Do NOT place a jumper on USB pins if using a USB cable**. Add the jumper only when USB is not used.

---

## Maximum Load

- Tested up to:
    - **10 A** with 1 oz copper
    - **15 A** with 2 oz copper
- Copper thickness selectable during PCB manufacturing
- Thermal testing (free air):
    - Temperature rise: **+15 °C over ambient** at max load

<p align="center">
  <img width="900" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/CAD_schematics/luciferin_official_pcb/img/thermal_test.png?raw=true">
</p>

---

## PCB Upgradeability

Luciferin PCBs are designed to be **future proof and fully upgradable**.

If your original build uses an **ESP8266**, you can later upgrade to:
- ESP32
- ESP32-C3
- ESP32-S2
- ESP32-S3
- Other compatible boards in **D1 Mini format**

No PCB redesign is required for a compatible replacement. Match the wiring and GPIO configuration when replacing the microcontroller.

---

## Luciferin Module for the Official PCB

The Luciferin Official PCB requires a "D1 Mini format" board. With the new Luciferin Module for the Official PCB, you can use a smaller board, opening up more upgrade possibilities without the need to replace the PCB or redo any soldering or cabling.

<p align="center">
  <img width="900" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/pcb_noeth.jpg?raw=true">
</p>

> Download the [GERBER file for the Luciferin Module for the Official PCB](https://github.com/sblantipodi/glow_worm_luciferin/raw/master/assets/CAD_schematics/luciferin_modules/standard/2.1/Gerber_PCB_Luciferin_Module_V2.1_final_PCB_Luciferin_Module_V2.1_final.zip)

If you prefer a board that is:
- smaller than D1 Mini
- based on a newer chipset (for example, a more powerful MCU capable of driving more LEDs, with improved connectivity, etc.)
- cheaper
- or simply different

You can use the **Luciferin Module for the Official PCB**.

### Supported Boards

The module supports boards with pin spacing of **6 × 2.54 mm (15.24 mm)**, including:

- WaveShare **Zero** family
- Seeed Studio **XIAO** family
- ESP32 **Super Mini** family
- Unexpected Maker **Tiny** family
- Adafruit **QT Py** family
- Other compatible layouts

**Important:**  
Power pins (**VCC** and **GND**) must be located within the **first three pins** on either the left or right side.

---

## Hardware and Software Configuration

Luciferin supports **both software and hardware configuration**.

### Software (GPIO Mapping)

Using **Glow Worm Luciferin firmware**, GPIOs can be remapped to match your board layout.

No PCB changes are needed for supported GPIO remapping.

### Hardware (Power and Ground)

Power lines (**5V, 3V3, GND**) cannot be remapped in software.

Instead, the Luciferin Module allows hardware configuration using **solder bridges**.

#### Example

Board layout:
- 5V → first pin (right)
- GND → second pin (right)
- 3V3 → first pin (left)

Solder bridges:
- **L1: 5V**
- **L2: GND**
- **R1: 3V3**

This adapts the module power routing to your board.

The LDR hole (top right of the PCB) is a flexible connection point for the LDR sensor's ADC pin.

If you solder the solder joint → the LDR sensor is automatically connected to the default ADC pin (the one printed on the silkscreen). No extra wiring needed.
If you leave the solder joint open → the default connection is broken, and you can run a wire from any ADC pin you prefer to that LDR hole. This lets you choose a different ADC pin than the default one.

---

## Luciferin Ethernet Module for the Official PCB

<p align="center">
  <img width="900" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/pcb_eth.jpg?raw=true">
</p>

> Download the [GERBER file for the Luciferin Ethernet Module for the Official PCB](https://github.com/sblantipodi/glow_worm_luciferin/raw/master/assets/CAD_schematics/luciferin_modules/ethernet/2.1/Gerber_PCB_Luciferin_Module_V2.1_ETH_final_PCB_Luciferin_Module_V2.1_ETH_final.zip)

The **Luciferin Ethernet Module** adds Ethernet support to the official PCB.

### Requirements
- Luciferin Ethernet Module
- ESP32 (or newer, ESP32-S3 is one of the best option for the ethernet module)
- W5500 Lite Ethernet board

### Configuration
Enable Ethernet in the **Glow Worm controller's web interface**, or through Firefly's supported network/device settings, and configure:
- MISO
- MOSI
- SCLK
- CS

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/ethernet.jpg?raw=true">

**Luciferin supports all SPI Ethernet devices**, including custom ones. GPIOs can be configured for SPI Ethernet.

---

## Luciferin Case

<p align="center">
  <img width="900" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/luciferin_case_4_photos.png?raw=true">
</p>

- Supports WiFi and USB installations
- Compatible with ESP8266 and Tiny Pico ESP32 upgrades

### Variants
- Desktop version (no mounting flaps)
- Regular version (with mounting flaps)

### Print Settings
- Material: PLA
- Infill: 20%
- Layer height: 0.2 mm
- Supports: Yes

Luciferin Case is Designed by  
[@pbl0m (Patrick Blom)](https://github.com/patrick-blom)

Downloads:
- Thingiverse: https://www.thingiverse.com/thing:5220580
- Thangs: https://thangs.com/pbl0m/Luciferin%2520Case-51051

---

## Community & Disclaimer

Join the community on Discord:  
[![Discord](https://img.shields.io/discord/747247942074892328.svg?label=LUCIFERIN&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)](https://discord.gg/aXf9jeN)

This PCB and kit are provided for **educational and hobby use only**.  
They are **not certified** for commercial or safety critical applications.

By manufacturing this PCB, you acknowledge that:
- Assembly and usage are your responsibility
- The author is not liable for damages
- The product is not CE/FCC/EMC/RoHS certified
- Proper tools and precautions must be used
