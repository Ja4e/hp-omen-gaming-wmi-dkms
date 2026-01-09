# ⚡ HP OMEN 16 (8E35) Linux Patch

This patch enables full hardware control for the HP OMEN 16 (Board ID `8E35`), unlocking performance limits and enabling native lighting control via `hp-wmi`.

## 🔥 Features

* **Nvidia GPU TGP Unleashed:** Removes the artificial Total Graphics Power (TGP) limit enforced by the embedded controller, allowing your GPU to draw full wattage for maximum performance.
* **4-Zone RGB Control:** Adds a sysfs interface to manually control the 4-zone keyboard backlight without needing external bloated software.

## 🌈 Keyboard Backlight Usage

You can set the keyboard color by writing a 24-character hex string to the `fourzone_color` interface.

### The Format
The string consists of four RGB Hex codes concatenated together (Zone 1 through Zone 4).

`[ZONE_1_RRGGBB][ZONE_2_RRGGBB][ZONE_3_RRGGBB][ZONE_4_RRGGBB]`

### Example Command
To set a rainbow pattern (Red, Green, Blue, Yellow):

```bash
# Zone 1: FF0000 (Red)
# Zone 2: 00FF00 (Green)
# Zone 3: 0000FF (Blue)
# Zone 4: FFFF00 (Yellow)

echo "FF000000FF000000FFFFFF00" | sudo tee /sys/devices/platform/hp-wmi/fourzone_color
