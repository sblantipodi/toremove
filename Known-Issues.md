## DRM (Netflix, Disney Plus, Amazon Prime Video)

DRM protection prevents Luciferin from capturing the screen.  
To workaround the problem you can disable `Hardware acceleration` in your browser.

Alternatively, capture the HDMI output using an **HDMI splitter and a USB capture card** to bypass the screen capture DRM problem. See [Quick start](https://github.com/sblantipodi/firefly_luciferin/wiki/Quick-start) for the wiring. The splitter must provide a signal the capture card can receive; compatibility depends on the source and HDMI protection.

## How To Disable Windows 10/11 Hardware GPU Scheduler

The new Windows 10/11 Hardware accelerated GPU Scheduler ("HAGS") is a system feature added with Windows 10 version 2004.
It is available only for specific graphics cards and requires up to date drivers.

HAGS is currently known to cause performance and capture issues with Luciferin, OBS, games, and overlay tools like Overwolf.  
It's a new and experimental feature and we currently recommend disabling it.

To disable the Hardware accelerated GPU Scheduler, change the following option:

`Settings App → System → Display → scroll down to Graphics Settings → Turn "Hardware-accelerated GPU scheduling" to Off.`

**Note:** If you have an RTX4000 series GPU or newer, you may want to leave HAGS enabled since DLSS3 requires it to work. RTX4000 series GPUs do not suffer from performance issues. For all other GPUs, it is recommended to disable HAGS.
