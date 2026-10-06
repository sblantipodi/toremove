<img align="right" width="350" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/rgbcym_degree.jpg?raw=true">  

**HSL** stands for **Hue, Saturation & Lightness** and is one of the main ways to represent RGB color values.  
HSL differs from **HSB/HSV**: lightness and brightness/value use different scales. This page describes HSL.

The **HSL Tuning control panel** allows you to adjust Hue, Saturation, and Lightness of your LED strip.  
It can be used to:
- Shift specific colors slightly
- Desaturate certain colors
- Brighten or darken specific colors

HSL tuning is particularly useful when you want to tweak specific colors from your screen capture.  
For example, correct an overly green yellow or reduce an oversaturated blue. These adjustments affect the LED colors, not the image on the screen, and work with both PC and HDMI capture.

---

**To access HSL Tuning:**  
`Settings` → `Test Image` button

A **test image** will appear with the tuning control panel in the center:

<img width="900" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/test_image_anim_color.gif?raw=true">  

You can select **six colors**: three primary (Red, Green, Blue) and three complementary (Cyan, Magenta, Yellow).  
Each color has **three horizontal sliders** to adjust Hue, Saturation, and Lightness.

<p align="center">
<img align="middle" width="650" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/color_correction_dialog.jpg?raw=true">  
</p>

The **vertical slider** adjusts the **hue** of the selected color (affects the test image only).  

## Hue
Hue corresponds to what we most often think of as “color.”  
It is calculated in degrees along a color wheel: red → yellow → lime → cyan → blue → magenta → red.

<p align="center">
<img align="middle" width="450" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/hue.jpg?raw=true">  
</p>

## Saturation
Saturation determines **how pure a color is**.
- **100%** → full, pure hue
- **0%** → a neutral gray at the same lightness

<p align="center">
<img align="middle" width="450" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/saturation.jpg?raw=true">  
</p>

## Lightness / Brightness
In HSL, lightness describes the position between black and white:
- **0%** → black
- **50%** → the middle lightness, where a fully saturated hue is most vivid
- **100%** → white

Firefly's tuning sliders apply **adjustments** to captured colors rather than replacing every pixel with one absolute HSL value. Start with small corrections and compare familiar scenes.

<p align="center">
<img align="middle" width="450" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/lightness_brightness.jpg?raw=true">  
</p>

For further improvement of color accuracy, explore **white temperature and gamma correction** [here](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Temperature-and-White-Balance).

## Calibration order

First check [white balance and gamma](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Temperature-and-White-Balance). For a captured HDR signal or a dedicated calibration profile, also consider [HDR to SDR and LUT](https://github.com/sblantipodi/firefly_luciferin/wiki/HDR-to-SDR-and-LUT). Then use HSL tuning for individual color ranges.

<!-- Screenshot: current color-grading controls, including the corresponding settings in the Firefly web interface. -->
