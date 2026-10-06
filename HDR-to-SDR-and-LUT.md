A **LUT (Lookup Table)** is a color conversion profile. It tells Firefly how to translate captured colors into the colors sent to your LEDs.

This is especially useful with **HDR content**: a TV or monitor can display a wider brightness range than an LED strip. HDR to SDR tone mapping adapts that range so the lighting keeps useful detail and colors instead of looking too dark or washed out.

LUTs can also provide a dedicated calibration for your setup or a creative color treatment. They affect the lighting output, not the picture on your TV or monitor.

## Choose a built in profile

Open the display options beside **Bind to display** in the **Mode** tab, or the corresponding display settings in the Firefly web interface, and choose a **LUT**.

Firefly includes profiles such as **HDR to SDR standard**, **high precision**, **high contrast**, and **high brightness**, as well as a black and white LUT. Start with a profile appropriate to your captured signal and compare the result on a familiar scene.

<!-- Screenshot: LUT selector showing the built-in profiles in the current desktop or web interface. -->

Select **Disabled** to compare the unmodified output. If your capture device already converts HDR to SDR, judge the captured picture first: applying a second HDR conversion may produce an unwanted result.

<!-- Image: same HDR scene with LED output before and after an appropriate HDR-to-SDR LUT; show the benefit in dark areas and highlights. -->

## Add your own .cube LUT

1. Locate Firefly's **configuration folder**:
   - **Windows:** `FireflyLuciferin` inside your Documents folder, including redirected Documents locations.
   - **Linux:** `$XDG_CONFIG_HOME/FireflyLuciferin`, normally `~/.config/FireflyLuciferin`. Sandboxed installations may use their own application configuration location.
2. Create the **cube_lut** subfolder if it does not exist.
3. Place your calibration file there with the **.cube** extension, for example `cube_lut/My calibration.cube`.
4. Reopen the LUT selector and select your file. Apply and save the setting.

Use a distinct filename: bundled LUTs take precedence over a custom file with the same name. If the file does not appear, check the configuration folder used by your installation, then reopen the settings or restart Firefly.

<!-- Screenshot: configuration folder with cube_lut/My calibration.cube and the same file selected in Firefly. -->

## LUT, gamma, or white balance?

| Setting | Use it to |
| --- | --- |
| **LUT / tone mapping** | Convert colors and brightness for a particular captured signal or calibration |
| **Gamma** | Adjust how strongly dark and mid tone colors light the LEDs |
| **White balance** | Make the lighting warmer or cooler |
| **Color grading** | Correct individual color ranges |

Change one setting at a time so you can see its effect. See [White balance and gamma](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Temperature-and-White-Balance) and [Color grading](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Grading-(Hue-Saturation-and-Lightness-tuning)).
