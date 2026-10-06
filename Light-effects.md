Choose an effect in Firefly's **Misc** settings, web interface, or supported controller controls. Effects can follow captured video, react to audio, or run as standalone lighting.

<img align="center" width="450" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/effects.jpg?raw=true">

### Bias Light
Uses colors from **PC screen capture or an HDMI capture card** to make the LED lighting follow the picture. Firefly must be running on the capturing PC or Raspberry Pi.

### Music Mode
There are **three music driven effects**:

- **VU Meter:**  
  Displays audio signal levels with **green** for RMS and **red/yellow** for peaks.

- **Screen Capture + Music:**  
  A combination of bias light (screen capture) and music analysis to regulate LED brightness based on audio peaks.

- **Rainbow Music:**  
  Rainbow colors driven by the music.

Standalone effects, such as solid colors or animated rainbow effects, do not require video or audio capture. Glow Worm's own web interface can control its standalone lighting with FULL firmware.

<img width="500" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/misc_tab_color.jpg?raw=true">  

`Luciferin` is designed with simplicity in mind. Less is more.

Select an audio effect and check the selected audio input. Music effects react to audio available **on the host running Firefly**. With an HDMI source, do not assume its audio is available to Firefly simply because the video is captured; choose the appropriate recording/loopback source if your setup provides one.

---

### Audio Loopback Options

#### Native Audio Loopback
If your operating system has a working **audio loopback device**, Luciferin will use it as the default audio input.

#### Software Audio Loopback
If no loopback device is detected, Luciferin will create a **software loopback** on the default audio output.

[![Watch Music Mode Demo](https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/yt_music_mode.JPG?raw=true)](https://www.youtube.com/watch?v=ax9pNscWrT0)
