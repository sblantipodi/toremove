A Luciferin setup has four parts: **a capture host**, **a LED controller**, **an addressable strip**, and **a suitable power supply**. This page covers the controllers and supporting hardware; follow [Quick start](https://github.com/sblantipodi/firefly_luciferin/wiki/Quick-start) for the connections.

## Capture host and HDMI hardware

- **PC screen capture:** run Firefly on the Windows or Linux PC whose screen you want to capture. For PC gaming, this direct path is the recommended setup.
- **External HDMI source:** use a Windows/Linux PC or an ARM64 Linux host, such as a Raspberry Pi with a 64-bit OS. A Raspberry Pi can run without a desktop and be controlled from Firefly's web interface.
- **HDMI wiring:** source → splitter → TV on one output, USB capture card on the other → Firefly host. The capture card connects to the host, not directly to the LED controller.

Recommended hardware links will be added here:

- **HDMI splitter 1:** link to be added.
- **HDMI splitter 2:** link to be added.
- **USB capture card 1:** link to be added.
- **USB capture card 2:** link to be added.

<!-- Add the user's verified splitter/capture-card links and optional product screenshots. -->

## LED controllers

[**Glow Worm Luciferin**](https://github.com/sblantipodi/glow_worm_luciferin) is a firmware designed for **ESP microcontrollers**.

**Supported devices:** ESP8266, ESP32, ESP32-C3, ESP32-C6, ESP32-C5, ESP32-S2, ESP32-S3.    

> The ESP32-S3 is one of the newest and most powerful ESP32 chips.  
> The ESP32-C5 supports 5 GHz WiFi 6 and offers higher WiFi performance compared to the other variants.
> Ethernet requires a supported controller and the appropriate external Ethernet hardware; the chip alone does not provide an Ethernet connector.

The **D1 Mini format** is compatible with the [Luciferin Official PCB](https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB).
[Luciferin modules](https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB#luciferin-module-for-the-official-pcb) for the Official PCB add support for smaller boards than the D1 Mini.

Below is a list of high quality microcontrollers from reputable manufacturers, all fully tested with Luciferin.

---

## Lolin D1 Mini [ESP32 family]

| Lolin ESP32-C3                                                                                                                                                       | Lolin ESP32-S2                                                                                                                                                        | Lolin ESP32-S3                                                                                                                                                        |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <a href="https://www.wemos.cc"><img width="300" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/c3_mini_v2.1.0_1_16x16.jpg"></a> | <a href="https://www.wemos.cc"><img width="300" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/s2_mini_v1.0.0_1_16x16.jpg"></a> | <a href="https://www.wemos.cc"><img width="300" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/s3_mini_v1.0.0_1_16x16.jpg"></a> |



## Mini devices [ESP32 family]

| WaveShare ESP32 Zero family                                                                                                                                   | Seeed Studio XIAO ESP32 family                                                                                                                              | ESP32 Super mini family                                                                                                                                  |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <a href="https://www.waveshare.com"><img width="300" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/waveshare.jpg"></a> | <a href="https://www.seeedstudio.com/"><img width="300" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/xiao.jpg"></a> | <img width="300" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/supermini.jpg"> |

## Lolin D1 Mini [ESP8266]

| LOLIN ESP8266 D1 Mini 4MB                                                                                                                                             | LOLIN ESP8266 D1 Mini Pro 4MB                                                                                                                                             |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <a href="https://www.wemos.cc"><img width="250" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/d1_mini_v4.0.0_1_16x16.png"></a> | <a href="https://www.wemos.cc"><img width="250" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/d1_mini_pro_v2.0.0_1_16x16.jpg"></a> |

- **Full firmware** requires ESP8266 with 4MB flash
- **Light firmware** can run on ESP8266 Lite with 1MB flash

## ESP32

| Lolin ESP32 D32                                                                                                           | TinyPICO ESP32                                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <a href="https://www.wemos.cc"><img width="250" src="https://docs.wemos.cc/en/latest/_images/d32_v1.0.0_1_16x16.jpg"></a> | <a href="https://www.tinypico.com/"><img width="250" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/tinypico.jpg"></a> |

## Ethernet devices

| QuinLED-ESP32-ABE | WT32-ETH01 | ESP32-POE |
|------------------|------------|-----------|
| <img width="400" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/quindor_esp32_eth.png"> | <img width="400" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/wt32-eth01.jpg"> | <img width="400" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/esp32poe.jpg"> |

> **Supported Ethernet devices:**  
Gledopto Series with Ethernet, T-ETH ELite ESP32-S3, T-ETH Lite ESP32-S3, QuinLED-ESP32-Ethernet, QuinLED-Dig-Octa Brainboard-32-8L, LilyGO-T-ETH-POE, LilyGO-T-POE-Pro, WT32-ETH01, ESP32-ETHERNET-KIT-VE, ESP32-POE, ESP32-POE-WROVER, WESP32, Gledopto series with Ethernet.

**Luciferin supports all SPI Ethernet devices**, including custom ones. GPIOs can be configured for SPI Ethernet.

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/ethernet.jpg?raw=true">  

Thanks to [Arduino Boostrapper](https://github.com/sblantipodi/arduino_bootstrapper), Luciferin can run on many devices. For non ESP boards, firmware must be compiled manually.

---

## LED Strip SK6812 / WS2812B / APA102 / SK9812 5V

Luciferin supports **RGB and RGBW strips**.  
60 LEDs/meter is usually bright enough and energy efficient.  
**SK6812** is recommended if purchasing new LEDs.

<img width="700" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/ledstrip.jpg?raw=true">

**Recommended strips:**
- SK6812 RGBW 5V LED strip
- WS2812B RGB 5V LED strip

Learn how to configure RGB or RGBW strips [here](https://github.com/sblantipodi/firefly_luciferin/wiki/RGB-and-RGBW-support).

---

## Power supply for the LED strip

Choose a power supply matching the strip voltage and its maximum intended load. These are example sizes for a 5 V setup; verify the actual strip specification:

- **60 LEDs:** 5V / 3A recommended
- **120 LEDs:** 5V / 6A recommended

> A larger power supply runs cooler and more reliably. **Do not undersize your PSU.**

---

## Simple schematic

<img width="700" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/img/ambilight_bb.png?raw=true">

- **FULL firmware** adds network control and the controller web interface. Configure [WiFi or Ethernet](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access); **MQTT is optional**. USB can also be used.
- **LIGHT firmware** requires USB cable.
- For FULL firmware without USB, connect **5V pin** to the power supply.

---

## Luciferin Official PCB
<a name="unlike-other-pre-built-boards-the-official-pcb-is-upgradable"></a>

#### Unlike other prebuilt boards, the official PCB is **upgradable**!

<a href="https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB"><img width="700" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/CAD_schematics/luciferin_official_pcb/img/PCB_front.jpg?raw=true"></a>  
<a href="https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB"><img width="700" src="https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/CAD_schematics/luciferin_official_pcb/img/pre_after.jpg?raw=true"></a>

- If you prefer building your own controller to using a prebuilt board, [Luciferin's official PCB](https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB) lets you assemble it with a soldering iron without designing a PCB.

---

<a name="pre-built-boards-support"></a>

## Prebuilt boards support

Luciferin supports prebuilt boards such as [QuinLED-Dig-Uno](https://quinled.info/pre-assembled-quinled-dig-uno/), [QuinLED dig2go](https://quinled.info/quinled-dig2go/), and [Gledopto](https://gledopto.com/).

| [QuinLED-Dig-Uno](https://quinled.info/pre-assembled-quinled-dig-uno/) | [QuinLED dig2go](https://quinled.info/quinled-dig2go/) | [GLEDOPTO](https://gledopto.com/) |
|--------------------------------------------------------------------------|--------------------------------------------------------|----------------------------------|
| [<img width="500" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/quinled.png?raw=true">](https://quinled.info/pre-assembled-quinled-dig-uno/) | [<img width="500" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/dig2go.jpg?raw=true">](https://quinled.info/quinled-dig2go/) | [<img width="400" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/gledopto.png">](https://gledopto.com) |

- **GPIO notes:** DigUno and dig2Go use **GPIO16** by default. Learn more about [how to change the GPIO in use](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate#how-to-change-the-gpio-in-use).
- Dig2go is limited to 5V / 3A; brightness may be limited with many LEDs.

> Note: Some devices, like certain **GLEDOPTO** models, require the GPIO signal to be **inverted**.  
> You can enable this option in the GPIO settings.