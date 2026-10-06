Firefly continuously sends LED colors to Glow Worm over the network or USB. **Lossless compression** reduces repeated data, helping larger strips use less bandwidth without changing their processed colors.

Compression is applied automatically when useful. You do not need to trade color quality for a smaller stream: the controller reconstructs the same LED values.

## How compression helps

Consecutive LEDs often share exactly the same color. Firefly can send that color once with a description of how many LEDs use it, instead of repeating every value.

- **Less traffic:** repeated colors take fewer bytes to transmit.
- **Larger setups:** smaller frames reduce pressure on the connection and controller.
- **Identical output:** compression does not approximate colors or discard differences.

Savings depend on the scene. A solid color frame compresses well; a frame with different colors on every LED may not. Firefly checks whether the encoded data is worthwhile and falls back to uncompressed colors when needed.

## Grouping is a separate choice

[LED grouping](https://github.com/sblantipodi/firefly_luciferin/wiki/Group-LEDs) deliberately makes several LEDs share one logical color. It reduces spatial detail and the number of values to process and send.

RLE then removes repetition from those transmitted values. Grouping and compression can work together, but neither guarantees a fixed compression ratio.

## Inspect the live output

With a desktop available:

1. Open **Settings → Test Image**.
2. Start capture if it is not already running.
3. Use the **Overlay** control in the calibration panel.

The overlay shows the processed LED palette, frame rate information, gamma, and compression diagnostics. It helps you compare settings while watching real content.

<img alt="Live LED output and compression overlay" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/ovelay.jpg?raw=true">

<!-- Screenshot: current Overlay control and the live palette/FPS/compression/gamma panel. -->

On a host without a desktop, use Firefly's web interface and live preview to inspect capture; the floating desktop overlay requires a graphical session.

For the encoding details and numerical examples, see [Run Length Encoding Algorithm](https://github.com/sblantipodi/firefly_luciferin/wiki/Run-Length-Encoding-Algorithm).
