These mappings describe the named boards installed on the [Luciferin Module for the Official PCB](https://github.com/sblantipodi/firefly_luciferin/wiki/Ready-to-print-PCB#luciferin-module-for-the-official-pcb). They can differ from the chip family defaults.

Match the module's wiring and silkscreen, then apply the corresponding GPIO settings in Firefly or Glow Worm. Changing GPIO settings does not remap the board's power pins.

#### TinyPICO on Luciferin Module (ESP32)
- **LED GPIO32**
- **Relay GPIO22**
- **Button GPIO0**
- **LDR GPIO33**

#### TinyS2 on Luciferin Module (ESP32-S2)
- **LED GPIO38**
- **Relay GPIO9**
- **Button GPIO0**
- **LDR GPIO3**

#### TinyS3 on Luciferin Module (ESP32-S3)
- **LED GPIO7**
- **Relay GPIO9**
- **Button GPIO0**
- **LDR GPIO6**

Here you can [learn how to change the GPIO in use](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate#how-to-change-the-gpio-in-use).
