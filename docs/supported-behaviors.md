# Supported Behaviors

The converter supports a wide range of ZMK behaviors and maps them to OverKeys-compatible output.

## Complete Behavior Mapping

| ZMK Behavior | Description | OverKeys Output |
|--------------|-------------|-----------------|
| `&kp A` | Key press | `A` |
| `&mt LSHIFT A` | Mod-tap | `A` |
| `&lt 1 SPACE` | Layer-tap | `SPC` |
| `&mo 1` | Momentary layer | `MO(1)` |
| `&tog 1` | Toggle layer | `TG(1)` |
| `&lt_tog 1 A` | Layer-tap toggle | `A` |
| `&hm LCTRL A` | Hold-mod | `A` |
| `&tdJ` | Tap-dance | `J` |
| `&bt BT_CLR` | Bluetooth clear | `BT CLR` |
| `&bt BT_SEL 0` | Bluetooth select | `BT 0` |
| `&out USB` | Output selection | `USB` |
| `&bootloader` | Bootloader mode | `BOOT` |
| `&sys_reset` | System reset | `RST` |
| `&trans` | Transparent | `""` (empty) |
| `&none` | None | `""` (empty) |

## Key Code Mapping

Common key codes are automatically mapped to their OverKeys equivalents:

| ZMK | OverKeys | ZMK | OverKeys |
|-----|----------|-----|----------|
| `N1`-`N9` | `1`-`9` | `F1`-`F12` | `F1`-`F12` |
| `N0` | `0` | `EXCL` | `!` |
| `AT` | `@` | `HASH` | `#` |
| `DLLR` | `$` | `PRCNT` | `%` |
| `CARET` | `^` | `AMPS` | `&` |
| `ASTRK` | `*` | `LPAR` | `(` |
| `RPAR` | `)` | `MINUS` | `-` |
| `EQUAL` | `=` | `LBKT` | `[` |
| `RBKT` | `]` | `BSLH` | `\\` |
| `GRAVE` | `` ` `` | `COMMA` | `,` |
| `DOT` | `.` | `SLASH` | `/` |
| `SEMI` | `;` | `QUOT` | `'` |
| `LCTRL` | `LCTL` | `RCTRL` | `RCTL` |
| `LSHIFT` | `LSFT` | `RSHIFT` | `RSFT` |
| `LALT` | `LALT` | `RALT` | `RALT` |
| `LGUI` | `LGUI` | `RGUI` | `RGUI` |
| `SPACE` | `SPC` | `RETURN` | `ENT` |
| `BSPC` | `BSPC` | `DEL` | `DEL` |
| `TAB` | `TAB` | `ESC` | `ESC` |
| `CAPS` | `CAPS` | `INSERT` | `INS` |
| `PG_UP` | `PGUP` | `PG_DOWN` | `PGDN` |
| `HOME` | `HOME` | `END` | `END` |
| `UP` | `UP` | `DOWN` | `DOWN` |
| `LEFT` | `LEFT` | `RIGHT` | `RGHT` |
