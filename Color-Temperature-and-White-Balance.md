White balance and gamma help your LED lighting match the picture and your room. They apply to both PC screen capture and HDMI capture.

## White balance and color temperature

Color temperature describes how warm or cool the light looks: lower values are warmer and more yellow; higher values are cooler and more blue. The right setting depends on the strip and the appearance you want.

<img width="700" alt="Warm and cool color temperatures" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/Lighting-colour-temperature.jpg?raw=true">

Adjust **White Balance** in Firefly's **Misc** settings, or the corresponding control in the web interface. Start with a white image and move the slider until the LEDs look neutral beside your screen.

<img width="800" alt="White balance controls" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/whitebalance.jpg?raw=true">

The neutral setting disables the additional color temperature adjustment.

## Adaptive Gamma correction

Gamma controls how captured brightness translates into LED brightness. In Firefly, a larger gamma value makes dark and mid tone colors darker; a smaller value makes them brighter.

<img width="100" alt="Gamma curve" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/white_balance/gamma.jpg?raw=true">

**Adaptive gamma** varies that correction with the scene, helping dark content remain visible without using the same fixed curve for every image.

1. In **Misc**, choose a base **Gamma** value. The standard starting value is **2.2**.
2. Open the menu button beside Gamma.
3. Enable **automatic gamma**.
4. Choose the adjustment level: **Low**, **Medium**, or **High**. Compare a dark scene and a bright one, then save.

The corresponding gamma controls are also available in the web interface.

<!-- Screenshot: base Gamma control and automatic-gamma dialog showing Low, Medium, and High. -->

For a fixed curve, disable automatic gamma and adjust the base value manually. For HDR color conversion, use the separate [HDR to SDR and LUT](https://github.com/sblantipodi/firefly_luciferin/wiki/HDR-to-SDR-and-LUT) settings; gamma is not a replacement for tone mapping.

## Check the result

The [Test Image overlay](https://github.com/sblantipodi/firefly_luciferin/wiki/Test-image-and-latency-test) shows the processed LED colors and current gamma alongside capture and compression information.

<img alt="LED output and gamma overlay" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/ovelay.jpg?raw=true">

Firefly uses floating point calculations during color processing and interpolation to reduce intermediate rounding and preserve smooth transitions, particularly in darker colors.

<img alt="Color transitions with higher-precision processing" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/adaptive_gamma_8_32bit.gif?raw=true">

For correcting specific colors, see [Color Grading](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Grading-(Hue-Saturation-and-Lightness-tuning)).
