## Welcome to Luciferin

**Bring the colors on your screen into your room.** Luciferin synchronizes LED lighting with your games, movies, and shows, extending the image onto the wall behind your monitor or TV.

For PC gaming and desktop use, run Firefly directly on your Windows or Linux PC for the most responsive setup, with no extra capture hardware. For a console or TV stick, capture the HDMI source with a splitter and USB capture card. A Raspberry Pi running Firefly lets you build a compact TV setup without keeping a PC nearby. Firefly automatically detects whether a desktop is available: the web interface is always available, and the dedicated desktop interface is available when a desktop environment is present.

**New here? Start with the [Quick Start guide](https://github.com/sblantipodi/firefly_luciferin/wiki/Quick-start).** It explains the hardware, connections, and first configuration for both capture modes.

## How Luciferin works

Luciferin has two parts, designed to work together:

| Component | Runs on | What it does |
| --- | --- | --- |
| **Firefly Luciferin** | A Windows or Linux PC, or a supported Linux ARM64 system such as Raspberry Pi | Captures the video, calculates the lighting colors, and sends them to your LED controller. |
| **Glow Worm Luciferin** | A compatible microcontroller, such as an ESP32 | Receives those colors and drives the LED strip. |

Choose where the image comes from:

- **PC screen capture:** Firefly runs on the PC whose screen you want to capture.
- **HDMI capture:** a USB capture card feeds video from an external HDMI source into the PC or Raspberry Pi running Firefly.

In either setup, Firefly sends colors to Glow Worm over **WiFi, Ethernet, or USB**, depending on your controller and firmware. You can also add [satellites](https://github.com/sblantipodi/firefly_luciferin/wiki/Surround-lighting-with-satellites) to extend the lighting beyond the main strip.

## Key features

### Richer colors and smoother lighting

- **Adaptive gamma:** makes subtle colors more visible in dark scenes while preserving bright areas, with a dedicated HDR profile. [Learn more](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Temperature-and-White-Balance#adaptive-gamma-correction).
- **HDR to SDR tone mapping:** adapts HDR colors and brightness to your LEDs, with built in profiles and custom `.cube` LUTs. [LUT and calibration guide](https://github.com/sblantipodi/firefly_luciferin/wiki/HDR-to-SDR-and-LUT).
- **Smooth color transitions:** high precision, 32-bit floating point processing and frame interpolation produce finer color detail and smoother fades. [Transition settings](https://github.com/sblantipodi/firefly_luciferin/wiki/Smoothing-color-transitions).
- **Color calibration:** tune white balance, color temperature, hue, saturation, and lightness to suit your strip and room. [White balance](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Temperature-and-White-Balance) · [Color grading](https://github.com/sblantipodi/firefly_luciferin/wiki/Color-Grading-(Hue-Saturation-and-Lightness-tuning)).
- **Automatic black bar detection:** keeps lighting matched to the picture as the content's aspect ratio changes. [Aspect ratio](https://github.com/sblantipodi/firefly_luciferin/wiki/Aspect-ratio).

### Control it your way

- **Web and desktop control:** manage Firefly from your phone while sitting on the couch, or use the dedicated desktop interface when available. Glow Worm also has its own web interface for controller settings and standalone lighting. [Remote access](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access).
- **AI control through MCP:** ask a compatible AI assistant to control Luciferin using natural language. [MCP and AI agents](https://github.com/sblantipodi/firefly_luciferin/wiki/MCP-and-AI-Agents).
- **Home automation:** integrate with Home Assistant and MQTT; neither is required for a basic setup. [Home Assistant integration](https://github.com/sblantipodi/firefly_luciferin/wiki/Home-Automation-configs).
- **Music and lighting effects:** make your lights react to audio, combine screen colors with music, or choose an effect or a static color. [Light effects](https://github.com/sblantipodi/firefly_luciferin/wiki/Light-effects).
- **Profiles and everyday comfort:** save settings for different activities, adjust lighting for late night use, and turn LEDs off during inactivity. [Profiles](https://github.com/sblantipodi/firefly_luciferin/wiki/Profiles) · [Eye care and night mode](https://github.com/sblantipodi/firefly_luciferin/wiki/Eye-care-and-night-mode) · [Power saving](https://github.com/sblantipodi/firefly_luciferin/wiki/Power-saving-features).

### Responsive capture, flexible setups

- **Hardware accelerated processing:** efficient capture on Windows and Linux, automatic capture method selection, and CPU tuning help keep system load low. [Linux acceleration](https://github.com/sblantipodi/firefly_luciferin/wiki/Linux-support) · [Capture performance](https://github.com/sblantipodi/firefly_luciferin/wiki/Very-fast-capture).
- **Less data, lower latency:** lossless RLE compression and efficient LED grouping reduce transmission bandwidth, especially on large strips. [Compression](https://github.com/sblantipodi/firefly_luciferin/wiki/Lossless-compression-and-overlay) · [LED grouping](https://github.com/sblantipodi/firefly_luciferin/wiki/Group-LEDs).
- **Multi monitor and surround lighting:** light multiple displays and extend the experience to satellite lights around the room. [Multi monitor setups](https://github.com/sblantipodi/firefly_luciferin/wiki/Multi-monitor-support) · [Satellites](https://github.com/sblantipodi/firefly_luciferin/wiki/Surround-lighting-with-satellites).
- **Windows, Linux, and Raspberry Pi:** choose Windows or Linux for your PC, or Linux ARM64 for a compact HDMI capture setup. [Installation options](https://github.com/sblantipodi/firefly_luciferin/wiki/Installers-and-binaries) · [Linux support](https://github.com/sblantipodi/firefly_luciferin/wiki/Linux-support).

### Easy to start, room to customize

- **Guided firmware installation and automatic updates:** install Glow Worm from your browser and keep both the application and firmware up to date. [Web Installer](https://sblantipodi.github.io/glow_worm_luciferin/) · [Update management](https://github.com/sblantipodi/firefly_luciferin/wiki/Luciferin-update-management).
- **Visual setup tools:** check LED placement and latency with Test Image; use the live overlay to see exactly what is being sent to your LEDs. [Test Image](https://github.com/sblantipodi/firefly_luciferin/wiki/Test-image-and-latency-test) · [Live overlay](https://github.com/sblantipodi/firefly_luciferin/wiki/Lossless-compression-and-overlay).
- **Your choice of hardware:** support for RGB and RGBW strips, compatible ready made controllers, configurable firmware settings, and official PCBs for DIY builds. [Compatible hardware](https://github.com/sblantipodi/firefly_luciferin/wiki/Compatible-Hardware) · [RGB/RGBW](https://github.com/sblantipodi/firefly_luciferin/wiki/RGB-and-RGBW-support) · [Controller settings](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate) · [Official PCBs](https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB).
- **Make it your own:** choose a theme, including Modern Dark Orange, and customize your layout and color settings. [Themes](https://github.com/sblantipodi/firefly_luciferin/wiki/Themes).

## See it in action

[![Luciferin ambient lighting demonstration](https://github.com/sblantipodi/glow_worm_luciferin/blob/master/assets/img/pc_ambilight.png?raw=true)](https://www.youtube.com/watch?v=68pnR5HMCTU)

Click the image to watch the demonstration on YouTube, or browse more [videos](https://github.com/sblantipodi/firefly_luciferin/wiki/YouTube-Videos).

## Need help?

Visit the [Discord community](https://github.com/sblantipodi/firefly_luciferin/wiki/Luciferin-Discord-server) or check [known issues](https://github.com/sblantipodi/firefly_luciferin/wiki/Known-Issues).

The name *Luciferin* comes from the light emitting compounds found in organisms such as fireflies and glow worms.
