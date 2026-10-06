For a guided installation, use the [Web Installer](https://sblantipodi.github.io/glow_worm_luciferin/). For manual flashing, these examples use **esptool 5.x** and its hyphenated command names.

## Prepare

Install [Python](https://www.python.org/downloads/), then:

```bash
python -m pip install "esptool>=5,<6"
```

Download the matching [Glow Worm firmware](https://github.com/sblantipodi/glow_worm_luciferin/releases). Check the chip, board, FULL/LIGHT variant, and whether the binary is a **merged image** or an application image.

Connect by USB and close applications using its serial port.

## Flash

For a **merged image documented for offset 0x0**, replace the port and filename:

```text
python -m esptool --chip auto --port COM5 --baud 115200 write-flash 0x0 firmware_merged.bin
```

On Linux, replace `COM5` with the actual port, such as `/dev/ttyUSB0`.

For separate binaries or application only images, use the **offsets specified by that firmware release**. Do not assume every ESP32/ESP8266 image belongs at 0x0 or force one flash mode/frequency for all boards.

## Optional erase

Erasing clears firmware settings as well as flash contents:

```text
python -m esptool --chip auto --port COM5 erase-flash
```

Use it only when needed, then flash and reconfigure the controller.

See Espressif's [basic commands](https://docs.espressif.com/projects/esptool/en/latest/esp32/esptool/basic-commands.html) and [v5 migration guide](https://docs.espressif.com/projects/esptool/en/latest/esp32/migration-guide.html) for command syntax.
