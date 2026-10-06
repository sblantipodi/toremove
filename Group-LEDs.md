**LED grouping** makes several neighboring LEDs share one logical color. It is useful for dense strips: fewer capture zones and transmitted values can give more uniform lighting with less processing, at the cost of some spatial detail.

Set the group size in Firefly's LED layout settings and check the result with the Test Image. Grouping applies to PC and HDMI capture.

<img align="center" width="400" src="https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/groupleds.jpg?raw=true">

Luciferin provides a dynamically generated test image to help you verify the LED positioning behind your monitor.

### No LED grouping
The following example shows the test image with **no LED grouping applied**:

![settings_screen](https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/test_image_black.gif?raw=true)

### Grouping six LEDs
This example shows the result when **six LEDs are grouped together**:

![settings_screen](https://github.com/sblantipodi/firefly_luciferin/blob/master/data/img/groupleds_ti.gif?raw=true)

LED grouping helps:

- Reduce transmitted color values: 100 LEDs grouped by 2 use 50 logical colors.
- Reduce small color variations on dense strips.
- Improve uniformity across neighboring LEDs.
- Reduce the number of capture zones to process.

Firefly distributes physical LEDs across the logical zones of each layout segment. If the segment count is not divisible by the grouping value, the effective sizes can differ from that value: in the current layout generator, 10 LEDs with grouping set to 4 form two zones of 5 LEDs. Check the generated Test Image rather than assuming an incomplete final group.

Grouping deliberately shares colors; **lossless compression** preserves the processed colors and only removes repetition from their encoding.

> For more information on how compression works, see [Lossless compression and overlay](https://github.com/sblantipodi/firefly_luciferin/wiki/Lossless-compression-and-overlay).

