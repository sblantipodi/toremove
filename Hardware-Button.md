A hardware button lets you turn **Glow Worm FULL** lighting on or off directly at the controller.

## Connect the button

Use a momentary button between the configured **button GPIO** and **GND**. Glow Worm uses **INPUT_PULLUP**: the input is high when released and low when pressed.

The default pin depends on the chip and board. Check [Supported GPIO and Baud Rate](https://github.com/sblantipodi/firefly_luciferin/wiki/Supported-GPIO-and-Baud-Rate) and any prebuilt board wiring rather than assuming GPIO0 applies to every controller.

## Why a pull up is needed

A pull up holds the input at a defined high state when the button is open, preventing random readings from electrical noise. The firmware enables the microcontroller's internal pull up for this input.

<p align="center">
<img width="400" alt="Pull-up resistor and button circuit" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/pullup_res.jpg?raw=true">
</p>

If your circuit uses an external pull up, its supply must match the controller's GPIO logic voltage. The diagram explains the principle; it is not a reason to connect a 3.3 V GPIO directly to 5 V.

Configure the button GPIO through Firefly's device settings or the Glow Worm web interface, then test that a press toggles the LEDs.

<!-- Screenshot: button GPIO setting for a configured controller. -->
