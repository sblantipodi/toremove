Luciferin supports **RGB strips** and **RGBW strips** (WS2812B, SK6812, APA102, SK9812).  
Choose **Color Mode** in Firefly's **Devices** settings to match the connected strip. Use RGB for a three channel strip; select an RGBW mode only for a strip with a dedicated white channel.

<img align="center" width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/luciferin_rgb_rgbw.png?raw=true">

### LED strip types

- **RGB:** Only RGB channels are used.
- **RGBW:** White is reproduced using the dedicated white channel (lower power consumption).
- **RGBW mixed (Brighter):** All four channels are used for white (high power consumption, maximum brightness).
- **RGBW (RGB only):** White is reproduced using RGB channels only (white channel not used).

---

## How to change color order

Luciferin supports many color orders:

- GRB / GRBW
- RGB / RGBW
- BGR / BGRW
- BRG / BRGW
- RBG / RBGW
- GBR / GBRW
- GRWB
- GWBR
- WRBG
- RGWB
- RWBG
- WGBR
- BGWR
- BWRG
- WGRB
- BRWG
- BWGR
- WRGB
- RBWG
- RWGB
- WBGR
- GBWR
- GWRB
- WBRG

Select **Color Order** in Firefly's **Devices** tab or web device settings. FULL controllers also expose it in the [Glow Worm web interface](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access#luciferin-web-interface).

If a red test appears green or blue, check color order first. RGB/RGBW mode controls the channels in use; color order determines which channel each transmitted value reaches.

<img align="center" width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/color_order.jpg?raw=true">

---

## LED Strip WS2812B / SK6812 5V

Luciferin supports both **RGB and RGBW strips**.  
60 LEDs per meter is generally bright enough for most applications and does not require much power.

<img width="700" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/ledstrip.jpg?raw=true">

**Recommended strips:**
- SK6812 RGBW 5V LED strip
- WS2812B RGB 5V LED strip
