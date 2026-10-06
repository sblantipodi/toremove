Install **Firefly Luciferin** on the PC or Raspberry Pi that captures the image, and **Glow Worm Luciferin** firmware on the controller connected to your LED strip.

For PC gaming, run Firefly directly on your gaming PC and capture its screen. For a TV, console, or TV stick, a Raspberry Pi can capture HDMI through a splitter and USB capture card, so you do not need a PC beside the TV. See [Quick start](https://github.com/sblantipodi/firefly_luciferin/wiki/Quick-start) for the connection diagrams.

## Firefly Luciferin application

Download the installer for your operating system and architecture from the [Firefly Luciferin releases](https://github.com/sblantipodi/firefly_luciferin/releases).

| System | Architecture | Installer |
| --- | --- | --- |
| Windows | x86-64 | `.exe` |
| Linux PC | x86-64 | `FireflyLuciferinLinux.deb` or `FireflyLuciferinLinux.rpm` |
| Raspberry Pi or another ARM Linux host | ARM64 | `FireflyLuciferinLinux_arm64.deb` or `FireflyLuciferinLinux_arm64.rpm` |

Choose **DEB** for Debian based distributions and **RPM** for distributions using RPM packages. ARM64 builds require a **64-bit operating system**.

<img width="450" alt="Firefly Luciferin installer" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/setup.png?raw=true">

### Windows Package Manager

You can also install Firefly with:

```powershell
winget install luciferin
```

### Linux stores

Firefly is also available on Flathub and the Snap Store. These packages bundle dependencies and can simplify installation on Linux.

- <a href="https://flathub.org/apps/org.dpsoftware.FireflyLuciferin"><img width="150" alt="Download on Flathub" src="data/img/flathub-badge-en.svg"></a>
- <a href="https://snapcraft.io/fireflyluciferin"><img width="150" alt="Download on Snap Store" src="data/img/snap-badge.svg"></a>

The Arch Linux [AUR package](https://aur.archlinux.org/packages/firefly-luciferin-git) is built from the official sources but is not an officially supported package.

For installation commands, capture options, and desktop integration, see [Linux support](https://github.com/sblantipodi/firefly_luciferin/wiki/Linux-support).

### Raspberry Pi: with or without a desktop

Firefly automatically detects how to start:

- **With a desktop:** use the dedicated desktop interface or the web interface.
- **Without a desktop:** control Firefly through the web interface from your phone or another computer.

The web interface is available in both cases. If your Raspberry Pi has limited RAM, an installation without a desktop leaves more memory available for capture. With enough RAM, a desktop also gives you access to additional customization options through the dedicated interface.

There is no separate application version to choose for these two modes. See [Remote Access](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access) to connect from your browser.

## Glow Worm Luciferin Firmware

The controller needs Glow Worm firmware to receive colors from Firefly and drive the LED strip.

The [Luciferin Web Installer](https://sblantipodi.github.io/glow_worm_luciferin) provides a guided installation over USB. Select the firmware appropriate for your setup:

- **FULL:** network features, the controller's web interface, and satellite support.
- **LIGHT:** a simpler USB setup.

When upgrading Firefly, also update your controller to the compatible Glow Worm firmware indicated in the Firefly release notes.

<!-- Release check: the current source declares minimum.firmware.version=6.0.0. Confirm the published firmware requirement before adding a fixed version here. -->

For manual flashing, download the binaries from [Glow Worm Luciferin releases](https://github.com/sblantipodi/glow_worm_luciferin/releases) and follow the [esptool guide](https://github.com/sblantipodi/firefly_luciferin/wiki/How-to-flash-Glow-Worm-Luciferin-firmware-via-esptool).

After installation, follow [Quick start](https://github.com/sblantipodi/firefly_luciferin/wiki/Quick-start) to configure capture and your LEDs, or [Remote Access](https://github.com/sblantipodi/firefly_luciferin/wiki/Remote-Access) to set up the controller's network connection.