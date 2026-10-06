## What is the Performance Impact on your System?

Firefly is optimized to keep capture and color processing efficient. Hardware acceleration depends on the platform and capture source, with paths including **DirectX 12**, **OpenGL**, **NVIDIA CUDA**, **AMD/Intel video acceleration**, and **HIP**. Leave **Capture method** on **AUTO** to select a suitable backend.

Actual load depends on resolution, capture quality, frame rate, LED layout, and hardware. Direct screen capture on your gaming PC avoids an additional capture card and host. For HDMI sources beside a TV, an ARM64 host such as Raspberry Pi can process the USB capture input.

## Capture and controller frame rates

The default capture target is **30 FPS**; smoothing presets may use a different capture rate and generate additional LED frames. Use **FPS** in the desktop tray or the available web diagnostics to compare capture, Firefly output, and controller consumption.

<p align="center">
  <img width="450" alt="Capture and controller frame-rate information" src="https://raw.githubusercontent.com/sblantipodi/firefly_luciferin/master/data/img/info_screen.png">
</p>

A higher capture target helps only if the host, connection, and controller can keep up. Frames that cannot be consumed in time may be dropped rather than building a queue of delayed lighting updates.

- **USB serial:** use a baud rate supported by the controller and serial adapter.
- **WiFi/Ethernet:** baud rate does not control the network stream. Keep the connection stable and check controller throughput.
- **Large strips:** [grouping](https://github.com/sblantipodi/firefly_luciferin/wiki/Group-LEDs) and [lossless compression](https://github.com/sblantipodi/firefly_luciferin/wiki/Lossless-compression-and-overlay) reduce processing or transmitted data in different ways.
- **Smoothing:** an independent output worker can generate LED updates between captured frames; this is separate from browser live preview.

For controller wiring, see [Supported GPIO and Baud Rate](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate).

### ESP8266 performance.

| 100 LEDs           | FPS (RGB) | FPS (RGBW) |   
| :---               |:---------:|:----------:|   
| **WiFi UDP GPIO2** |  230 FPS  |  185 FPS   |   
| **WiFi UDP GPIO3** |  255 FPS  |  225 FPS   |   
| **WiFi UDP GPIO5** |  210 FPS  |  175 FPS   |    
| **USB GPIO2**      |  145 FPS  |  115 FPS   |    

| 300 LEDs           |   FPS (RGB)   |  FPS (RGBW)   |   
| :---               |:-------:|:------:|   
| **WiFi UDP GPIO2** | 70 FPS  | 65 FPS |   
| **WiFi UDP GPIO3** | 100 FPS | 75 FPS |   
| **WiFi UDP GPIO5** | 65 FPS  | 60 FPS |    
| **USB GPIO2**      | 45 FPS  | 40 FPS |    

| 500 LEDs           |  FPS (RGB)   |  FPS (RGBW)   |   
| :---               |:------:|:------:|   
| **WiFi UDP GPIO2** | 45 FPS | 35 FPS |   
| **WiFi UDP GPIO3** | 60 FPS | 45 FPS |   
| **WiFi UDP GPIO5** | 45 FPS | 35 FPS |   
| **USB GPIO2**      | 30 FPS | 25 FPS |    

### ESP32 performance.
GPIO in use does not affect performance on ESP32.

| 100 LEDs           | FPS (RGB) | FPS (RGBW) |   
| :---               |:---------:|:----------:|   
| **WiFi UDP**       |  300 FPS  |  235 FPS   |   
| **USB**            |  150 FPS  |  150 FPS   |    
| **Ethernet**       |  160 FPS  |  160 FPS   |    

| 300 LEDs           |   FPS (RGB)   |  FPS (RGBW)   |   
| :---               |:-------:|:------:|   
| **WiFi UDP**       | 105 FPS | 80 FPS | 
| **USB**            | 80 FPS  | 50 FPS |    
| **Ethernet**       |  100 FPS  |  78 FPS  |    

| 500 LEDs           |  FPS (RGB)   |  FPS (RGBW)   |   
| :---               |:------:|:------:|   
| **WiFi UDP**       | 65 FPS | 50 FPS |  
| **USB**            | 40 FPS  | 40 FPS  |
| **Ethernet**       |  60 FPS  |  47 FPS  |     

Note: USB tests have been done at 1.5 million baudrate on both ESP8266 and ESP32. Both microcontrollers use CH340 UART chip.
The Ethernet port guarantees better latency compared to other connection methods; however, at extremely high frame rates, it may have a higher overhead.
Performance is influenced by the connection method and the CPU performance of the microcontroller.
These benchmarks can help you understand what is best for your use case.

## The use of anti-lag technologies is recommended whenever possible
When the GPU is under heavy load, for example, when running a video game, using anti-lag technologies like `NVIDIA Reflex-Boost` or `AMD Anti-Lag` can help maximize Luciferin’s response.

## GPU hardware acceleration using Java Native Access

Windows desktop capture uses native Desktop Duplication backends, including **DX12 GPU** and **DX11 GPU**. GDI based capture is a separate compatibility path, not the same GPU capture API.

On Linux, available accelerated methods depend on X11/Wayland or USB capture and the installed drivers/media libraries. See [Linux support](https://github.com/sblantipodi/firefly_luciferin/wiki/Linux-support#wayland-support-and-hardware-acceleration).

## CPU acceleration using AVX SIMD extensions

Firefly uses the Java Vector API to process several color values in parallel. On x86 this can use available AVX vector widths; on ARM64 it can use the host's available vector support. Keep **AUTO** selected unless troubleshooting a specific machine.

<img width="400" alt="SIMD processing settings" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/simd.png?raw=true">

CPU processing time depends on capture dimensions, zones, memory, and vector support. It is one part of total lighting latency, not an end to end latency measurement.

## SIMD Benchmark

When SIMD processing is available, Firefly compares **FULL_VECTOR** and **DOUBLE_VECTOR** strategies on captured data and selects the faster strategy for the session. The vector width and number of pixels processed together depend on the host; there is no universal fixed pixel count.

### Override

For advanced diagnosis, these environment variable values override the benchmark:

| Environment variable | Effect |
| --- | --- |
| `LUCIFERIN_SIMD_STRATEGY_OVERRIDE=FULL_VECTOR` | Force the full vector strategy |
| `LUCIFERIN_SIMD_STRATEGY_OVERRIDE=DOUBLE_VECTOR` | Force the double vector strategy |
| Not set | Use automatic strategy selection |

<!-- Screenshot: current FPS/CPU information and AUTO capture selection. -->
