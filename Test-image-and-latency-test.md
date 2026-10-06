The **Test Image** in Firefly's dedicated desktop interface helps you check strip orientation, LED order, capture zones, and color calibration. Open it with **Settings → Test Image**.

For an HDMI setup or a host without a desktop, use the **web live preview** to check the incoming picture. Preview confirms what the capture device sees; it does not replace every desktop layout editing tool.

<!-- Screenshot: Firefly web live preview showing the HDMI input. -->

When configuring the number of LEDs in use,

<img width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/multi_display/multimonitor_7.jpg?raw=true">

you can use the **Test Image** to verify that all LEDs are positioned correctly.  
This tool also allows you to check whether the captured image margins match your desired layout and to fine tune them as needed.

<img width="900" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/test_image_anim_color.gif?raw=true">

The **first and last LEDs** are displayed in **gray**, making it easier to verify strip orientation and order.

### Additional Test Image Features

The Test Image also provides access to advanced calibration and diagnostic tools:

1. **Editing Color Grading (Hue, Saturation and Lightness tuning)**  
   Fine tune individual colors directly from the test image.
   [Learn more](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Grading-(Hue-Saturation-and-Lightness-tuning))

2. **Latency Test**  
   This test displays colors in rapid succession to help you evaluate the latency between the image shown on your monitor and the color displayed on the LED strip.

    - Increasing the framerate helps reduce latency
    - The test can be run at **10 different speeds**
    - Useful when selecting the right [**smoothing level**](https://github.com/sblantipodi/firefly_luciferin/wiki/Smoothing-color-transitions) for your setup

---

## Custom LED Layout

Using the Test Image, you can manually define **custom LED zones** in addition to the automatic mode, which distributes LEDs evenly around the monitor based on the configured LED count.

Custom LED layouts are useful when:
- Avoiding persistent on screen overlays (e.g., minimaps or HUD elements)
- Creating specific capture areas
- Assigning dedicated zones to [satellite devices](https://github.com/sblantipodi/firefly_luciferin/wiki/Surround-lighting-with-satellites)

[<img width="900" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/test_anim.gif?raw=true">](https://youtu.be/j7IV9rQr7J8)

#### (Click the image above to watch the video on YouTube)

The custom LED layout is **profile specific**.
Each profile can be automatically activated when a specific application or videogame starts.

### How it works

- Click on the background to reveal the image behind the test image
- Drag LED zones to move them around
- Hold CTRL while dragging to disable snap to grid
- Click and drag to select multiple LED zones
- CTRL+Click an LED zone to add it to the selection
- SHIFT+Click an LED zone to remove it from the selection
- Press DELETE to remove selected LED zones
- Use CTRL+Z / CTRL+Y to undo or redo actions
- Move LED zones pixel by pixel with arrow keys, hold CTRL to move faster
- Click the + icon on an LED zone to duplicate it, and the square icon to resize it
- Select all the LEDs you want to modify, resize them to your desired size, and then press SHIFT + TAB to space them automatically
- Press TAB repeatedly on the selected zones to resize them while keeping the spacing
- When creating a new LED zone, you can assign a [custom name that satellites can use as a zone identifier](https://github.com/sblantipodi/firefly_luciferin/wiki/Surround-lighting-with-satellites)
- Click an LED number to toggle it on or off

## Live LED overlay

Start capture, then select **Overlay** in the Test Image calibration panel. The floating panel shows the processed LED palette, capture/output frame rates, compression information, and gamma while you watch your content.

<!-- Screenshot: current Test Image Overlay control and floating LED palette/FPS/compression/gamma panel. -->

The overlay requires a desktop session. For background information, see [Lossless compression and overlay](https://github.com/sblantipodi/firefly_luciferin/wiki/Lossless-compression-and-overlay).
