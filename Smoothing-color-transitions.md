**Smoothing** softens abrupt LED color changes in games and videos. It works with both PC screen capture and HDMI capture. Choose the level in Firefly's **Misc** settings or its web interface.

<img align="center" width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/smoothing_frame_insertion.jpg?raw=true">

Increasing the smoothing level enhances fluidity but slightly reduces LED responsiveness.  
If you prioritize maximum responsiveness, you may want to disable smoothing.

---

## How does it work?

Luciferin uses **two techniques** to smooth transitions:

1. **Multi Frame Generation using Linear Interpolation**
2. **Exponential Moving Average (EMA)**

---

## Multi Frame Generation using Linear Interpolation

<img align="center" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/linear_interpolation_frame_insertion.jpg?raw=true">

- Reduces the capture framerate.
- Inserts interpolated frames between captured frames using **linear interpolation**.
- Smooths abrupt color changes, producing natural lighting effects.

> **Note:** Frame generation works on colors, not images, so it is lightweight compared to GPU frame generation technologies.

### Why does firmware process more frames than the capture system?

<img align="center" width="500" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/smoothing_framerate.jpg?raw=true">

- Interpolated frames are **generated in software**.
- The firmware processes more frames than Firefly Luciferin captures.
- **Benefits:**
  - **Reduced CPU & GPU load:** Generating interpolated frames is computationally cheaper than capturing and processing new frames from the GPU. This means higher smoothing levels can reduce overall system load, improving performance.
  - **Better motion consistency:** Linear interpolation helps prevent flickering or abrupt jumps in brightness, resulting in a more cinematic and immersive ambient lighting effect.
  - **Customizable experience:** Users can adjust the smoothing intensity to find the perfect balance between responsiveness and smoothness, adapting the effect to different types of content.

---

## Exponential Moving Average (EMA)

- **EMA** is a smoothing technique that weights recent frames more heavily while still considering past values.
- Reacts faster than a simple average while keeping transitions smooth.

### Advantages of EMA in Luciferin

- **Even smoother transitions:** EMA prevents sudden color jumps by softly blending recent colors with past ones.
- **Faster reaction to gradual changes:** It keeps transitions smooth without excessive delay, making it ideal for ambient lighting.
- **Reduced flickering:** Helps eliminate small, rapid fluctuations that might appear in fast moving content.
- **Works alongside frame generation:** EMA adds gradual blending to the generated transitions; stronger settings can also delay the lighting's reaction.

By combining Frame Generation and EMA, Luciferin delivers an even more natural and immersive ambient lighting effect while keeping system performance efficient.

> **Note:** EMA speed depends on the target framerate. Higher framerate = faster EMA transitions.

---

## Smoothing Levels

Luciferin offers **presets** combining frame generation with EMA:

| Smoothing Level  | Capture Framerate | Frame Generation | Target Framerate | EMA          |
|-----------------|-----------------|----------------|----------------|-------------|
| No Smoothing    | User defined    | Off            | User defined   | Off         |
| Level 1         | User defined    | Off            | 60 FPS         | Very fast   |
| Level 2         | 30 FPS          | 2x             | 60 FPS         | Fast        |
| Level 3         | 30 FPS          | 2x             | 60 FPS         | Moderate    |
| Level 4         | 15 FPS          | 4x             | 60 FPS         | Moderate    |
| Level 5         | 10 FPS          | 6x             | 60 FPS         | Slow        |
| Level 6         | 5 FPS           | 12x            | 60 FPS         | Very Slow   |
| Custom Smoothing| User defined    | User defined   | User defined   | User defined|

> Level 3 is a well balanced option for most setups.

---

## Customize Your Smoothing

Access advanced settings through the `☰` button:

<img align="center" width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/smoothing_adv.png?raw=true">

- **Exponential Moving Average (EMA):** `Off`, `Very fast`, `Fast`, `Rapid`, `Moderate`, `Slow`, `Very slow`
- **Capture Framerate:** Read only. Example: 30 FPS capture * 2x frame generation = 60 FPS target
- **Multi Frame Generation:** `Off`, `2x`, `3x`, `4x`, `6x`, `12x`, `30x`
- **Target Framerate:** `30 FPS`, `60 FPS`, `120 FPS`

## Capture, output, and live preview

The LED output worker runs independently of capture and uses floating point interpolation. Generated LED frames can therefore make lighting smoother without capturing a new video frame for every output update.

The browser's live preview is a separate view of the captured image; its frame rate should not be read as the LED output rate. Use the FPS information to compare capture and controller consumption.

<!-- Screenshot: smoothing preset and advanced controls in the desktop and web interfaces. -->
