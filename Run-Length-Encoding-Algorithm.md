Firefly uses **Run Length Encoding (RLE)** to remove repeated LED values without changing the resulting colors. This page describes the encoding; for practical setup, see [Lossless compression and overlay](https://github.com/sblantipodi/firefly_luciferin/wiki/Lossless-compression-and-overlay).

<a name="step-1---leader--follower-assignment"></a>

## Step 1: Leader / Follower Assignment

Consider 20 LEDs: 3 red, 5 blue, and 12 green.

```text
Red Red Red | Blue Blue Blue Blue Blue | Green × 12
```

The first LED in each identical color run is a **leader**. The remaining LEDs are **followers**. Only the three leader colors need to be sent, together with the group sizes.

<a name="step-2---group-sizes"></a>

## Step 2: Group Sizes

| Leader color | Group size, including the leader |
| --- | --- |
| Red | 3 |
| Blue | 5 |
| Green | 12 |

The size list is `[3, 5, 12]`.

<a name="step-3---rle-encoding-of-sizes"></a>

## Step 3: RLE Encoding of Sizes

Consecutive groups with the same size are themselves compressed. The notation `count × size` describes how many successive leader colors use that group size.

For `[3, 5, 12]`, the map is `1×3, 1×5, 1×12`.

For `[2, 2, 2, 2, 3]`, it becomes `4×2, 1×3`: four successive colors each expand to two LEDs, followed by one color expanding to three LEDs.

<a name="step-4---payload-sent-to-firmware"></a>

## Step 4: Payload Sent to Firmware

The stream carries the leader colors and their expansion map. Glow Worm expands them back into the full LED sequence.

The size calculation differs between **USB serial** and **UDP**, so the same numbers must not be used interchangeably.

### Example: USB serial color data

For the 20-LED example, excluding frame headers and other protocol fields:

| Representation | Calculation | Bytes |
| --- | --- | --- |
| Uncompressed RGB colors | 20 × 3 | 60 |
| Leader RGB colors | 3 × 3 | 9 |
| Three map entries | 3 × 2 | 6 |
| Compressed colors and map | 9 + 6 | 15 |

This example saves **75% of these color and map bytes**, not necessarily 75% of the complete transmitted frame.

### UDP efficiency estimate

For deciding whether compression is worthwhile, Firefly estimates UDP costs as **9 bytes per color** and **4 bytes per map entry**. These are estimates for the text based representation, not a measurement of every packet.

For the same example, the estimates are `20 × 9 = 180` without compression and `3 × 9 + 3 × 4 = 39` with compression. Actual packet sizes also depend on the encoded values, separators, headers, and chunking.

## Byte Padding (255 Limit)

The protocol uses single byte group sizes and counts, with a maximum of **255**. Longer runs are split into representable groups. A 300-LED run can be represented as groups of 255 and 45 LEDs with the same color.

The limit includes the leader: a size-255 group contains one leader and 254 followers.

## Efficiency Check

Firefly compares the estimated cost of leader colors plus the map with the uncompressed color cost. If compression would be larger, every LED is sent as a leader.

For example, ten LEDs with ten different colors provide no repeated color savings. Adding a map would increase the cost, so Firefly uses the uncompressed representation.

## LED Grouping - `groupBy`

Grouping is configured by the user and makes several physical LEDs share a logical color. For example, 100 LEDs grouped by 5 require 20 logical colors before any additional RLE savings.

Unlike RLE, grouping changes spatial detail. See [Group LEDs](https://github.com/sblantipodi/firefly_luciferin/wiki/Group-LEDs) to choose a suitable group size.
